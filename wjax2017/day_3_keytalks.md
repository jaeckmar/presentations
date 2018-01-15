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



##Road to Continuous Delivery
###Falko Dautel

##Von Jurassic Park zu Microservices – Wie modernisiert man Altanwendungen?
###Sven Ruppert