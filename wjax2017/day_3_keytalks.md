#Main Conference Day 2
##Java-8-Nachlese - Wie hat Java 8 die Java-Welt verändert?
###Klaus Kreft
* Feedback von Konferenzen
* großes Release so wie bei Java 2
* Streams & Funktionale Programmierung sind der Biggest Change
* var/val gibt es jetzt auch in Java
* Lambda-Expressions

Technische Gründe
* Multiprozessor Architektur sollen besser ausgenutzt werden -> Parallelität
* Bulk data durch parallele Streams
* Boilerplate Code reduzieren
* Clojures sind die Antwort darauf

Ist funktionale Programmierung jetzt besser als die Imperative?
* Performanceeinbußen
* Loops umbauen
* Bücher nur zu funktionaler Programmierung
* Mikrobenchmarks

Gegenmeinung
* Lambda's & Streams sind die Hipster-Bärte von Java und in 3 Jahren sowas von out!

Beides können!

Optionals
* lösen Uneindeutigkeit auf:
Beispiel: T findFirst() vs. Optional<T> findFirst()

Funktional vs. Imperativ
* Was besser ist, bleibt Geschmackssache

##The Streaming Transformation
###Ben Stopford
~not interesting enough~

##Exploring Java Performance Flame Graphs
###Nitsan Wakart
https://vimeo.com/233671554
* Root of all Evil: Premature Optimization (D. Knuth)
* The **problem** (with performance) is that often the **problem** is not the **problem**
* profile to find the cause of a problem! (Get requirements, measure, profile, measure)
* Brendan Gregg (Netflix) invented FlameGraphs
* looks to problems he has not produced

FlameGraphs
* visualizations of profiled software allowing the most frequent code-path to be identified quickly and accurately

<<flamegraph picture>>

* Input: Samping Profilers (Collect stacks, X samples per second, present data)
* Drei Ausprägungen:
  * Flat View: top in methods with percentage but you need context!
  * Tree View: context quickly run out of mental space -> much space because of deep stack
  * FlameGraph: big picture, birds eye view

FlameGraph
* profiler -> stack traces
* stacktraces collapsed to a string (hackable)
* collapsed stacks to SVG (super hackable)
* Y-Achse: 
  * Tiefe des Stacks
  * Top Methoden sind Blätter, Bottom sind Wurzelmethoden des Stacks
* X-Achse:
  * Anzahl der Samples
  * breitere Frames == mehr Samples == wo die "Zeit" verbraucht wird
  * Wurzeln sind breit, aufgerufene Methoden sind schmaler, Top Methoden sind Spitzen
* Farbe ist kontextabhängig
* Man schaut bei FlameGraphs nach Plateaus an der Spitze um Bottlenecks zu finden

JVisualVM-Profiler
* kein guter Profiler, da Samples nur an Safepoints erstellt werden
* Safepoint Anwendung stoppt (Threads), damit die JVM etwas tun kann
* Jeder Sample ist eine Safepoint Operation
* !Jedes Sample enthält alle Threads

JMC/Honest-Profiler
* kein Safepoint Beiwerk
* nur Java Stack
* hat Blind Spots: GC/Deopt/Runtime Stubs  

Linux Perf (perf_events)
* System profiler
* Userspace + Kernel
* Standard tool
* now works with java

##Road to Continuous Delivery
###Falko Dautel
~not interesting enough~

##Von Jurassic Park zu Microservices – Wie modernisiert man Altanwendungen?
###Sven Ruppert
* Start vor 3 Jahren
* Codebasis:
  * über 13 Jahre alt
  * keine Testabdeckung
  * Code Lords
  * ca. 15 % bald in Rente
  * über 50% seit ca. 15 Jahren in der Firma
  * nur Studenten werden rekrutiert
  * Entwickler lernen Java an diesem Projekt
* Start 
  * durch Herauslösen einer kleinen Insel
  * Vergrößern dieser Insel 
  * ein Team bilden
  * Vertrauen schaffen durch lauffähiges fertig abgenommenes Teilstück, das funktional ist!
* Veränderung der Arbeitsweise
  * von Überall zu "deiner" Zeit
  * 20% für Play and Try
  * Closed Source wurde Open Source gegenübergestellt
  * Umgebung verändern
    * Messenger statt Mails
    * Remote Meetings mit Zoom
    * Remote Pair Programming
    * Asynchron Arbeiten
    * Zu der Zeit arbeiten die am Besten zu dir passt (Arbeitszeitbeispiel unterbrochener Tagesablauf mit 6h Schlaf ;)
  * Open Source vs Closed
    * viel infrastrukturcode -> damit verdient die Firma kein Geld
    * Teilung der Code-Basis in code base und dev. environment
  * Veränderung führt zu Reaktionen
    * um die Entwickler niht zu verlieren -> Einteilung in Kategorien
    * Consultants (Play and Throw away)
    * Core Developers (collect and clean)
    * LTS Developers (keep alive)
    * Ausrichtung der Inzentivierung auf diese Gruppen
    * Consultants: amount of hours paid by the customer
    * Core Devs: rated on hours of a stable system
    * LTS: fixed income - bonus on Change Requests
    * Ebenfalls Anpassung des Entwicklungsparadigmas: Scrum (customer driven) vs. Kanban (roadmap driven)
  * Knowledge Sharing
    * verschiedene Slack-Channels die Links zu folgendem enthalten
    * Hacking Sessions
    * Articles / Blogs
    * Screencasts
    * Refactoring Sessions
  * TDD with jUnit
    * Codebase > 13 Jahre
    * wieviel Testcode ist genug?
    * Methode muss gefunden werden, um "gute" Tests zu schreiben
    * Mutations Testsing: Die Maschine findet die Ziele
    * Eine Mutation ist eine kleine Änderung, so klein, dass es schon zu einem Defekt führt
    * ist ein Addon zum normalen jUnit TDD
    * unterstützung durch Tools gegeben
    * führt zum Cleaner Code