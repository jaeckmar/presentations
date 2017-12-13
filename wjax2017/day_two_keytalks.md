#Main Conference Day 1
##Vorrede
###Sebastian Meyen
* Neuigkeiten Java: neuer Releasezyklus nach Java 9 (Jigsaw)
* Java 18.3, Java 18.9, Java 19.3...
* Tempo reinbringen, zeitbasiert releasen (Weil wir's können)
* neue Art der ~~Software~~Produktentwicklung
  * Zitat Werner Vogels (CTO AWS)(Cessna -> 737 -> 747 -> A380)
  * MVP Spotify
  * Uber: Ansatz vorhandene Komponenten zusammenstecken (Marktwert bei ca. 60 Mrd. US$)
    * keine Fahrzeuge
    * nur Software und Marketing / Kundenservice
    * Devices und Dienste sind vorhanden
    * Messaging von Google
    * Payment von Braintree SaaS
    * Billing von Mandrill
    * Hosting AWS
    * wenn im klassischen Sinne eigenentwickelt, würden heute noch Mitarbeiter gesucht
    * heute unmöglich im klassischen Sinne so ein Tempo zu entfachen
* Wandel: Tonfilm kam - Besorgte Bürger, Musiker, Künstler
* Die Welt verändert sich
* Disruption hat es immer gegeben an vielen Stellen - nur die Einschläge sind heftiger
* Gucken sie sich den Wandel an - auch wenn die Sachen manchmal etwas schwieriger zu verstehen sind.  

##Keynote: How thinking small is changing Software Development Big Time
###Sander Hoogendoorn

##Feature Branches und Continuous Integration - ein Widerspruch ?
###Sebastian Damm u. Steffen Schluff
* Martin Fowler Artikel aus 2000: "Everyone commits to the mainline every day"
* zentraler Begriff der Mainline
* im Jahre 2000 -> technische Empfehlung im zeitlichen Kontext sehen!
* 2009 Artikel zu FeatureBranch wie es mit CI zusammenspielt
* jeden Branch durchbauen ist Continuous Building - nicht Integration (Ich darf das sagen, ich hab den Begriff CI erfunden :-)
* Warum?
    * Semantische Konflikte beim Mergen
    * Opportunistic Refactoring wird erschwert (mercilessly)
* Alternative Toggles hat auch Nachteile 
    * technical debt
    * code landet in production
* Alternative Branch by Abstraction -> Indirektionsschicht einbauen 
    * Big Ball of Mud: Wo baue ich diese Schicht ein?
    * Exit-Strategie
* Alle Probleme durch CI gelöst? 
* 2008 SCM: Controlled Integration zwei Kernprobleme
    * Mainline Instability
    * Unecessary Bug Spreading
* Kaputte Builds verhindern aus Epilog: The Future of CI (CI-Buch)
    * Two-Phase-Commit (CI ist reaktionär, deshalb erst wenn erfolgreich gebaut, wird wirklich eingecheckt)
    * Personal Builds
* "Das geht bei FeatureBranches doch von sich aus!" Antwort der FB-Community
    * FeatureBranch-Workflow mit Branch für Task - Rebase - Merge 
    * Zahlreiche Branching Anti-Patterns (Microsoft gutes Dutzend Antipattern)
        * Merge Paranoia
        * Merge Mania
        * Big Bang Merge
        * Never Ending Merge
        * Branch Mania
        * Cascading Branches
        * Mysterious Branch
        
__CI und FB sind per Definition widersprüchlich__
* Annähern durch Gemeinsamkeiten?
    * Schutz der Mainline
* CI alleine verhindert keine "bad checkins"
* Branches erzwingen Merges bei falschem Gefühl von Sicherheit

Kompromiss?
* Artikel 2011: "Using Git and feature branches effectively"
    * Sobald dezentral versioniert wird muss auch dezentral gebaut, getestet und integriert werden
    * d.h. komplette Pipeline für Branches vor Reintegration in den Master
* regelmäßig den Masterstand rebasen/mergen
* stabile Zwischenstände oft und zeitig reintegrieren (pushen)
* Pull Request
* Lebensdauer der Branches kurz halten
* Werkzeuge kennen u. Konventionen festlegen (Git, Mergen, Fast-Forward, etc.)
* CI-Tools mit Branch Detection, Automatic Pipeline Generation, Automatic Merges

Fazit
* DVCS und Branches Möglichkeit häufiger zu comitten
* Dezentrale Tests und Integration sind guter Master Schutz
* Pull Requests verbessern Kommunikation u. Code Qualität
* FB u. CI ein Weg den Master fehlerfrei zu halten ohne auf Vorteile automatisierter Testpraktiken zu verzichten 

##API-Design: Vorsicht vor der Versioning Hölle
###Arne Limburg (OPEN KNOWLEDGE)
* API/Schnittstellengestaltung bereits seit 10 Jahren
* rückt durch Microservices noch stärker in den Fokus
* Fachlichkeit entwickelt sich weiter also auch die Schnittstelle!
* nicht immer gleichzeitig Server und Client aktualisierbar
    * Schnittstellen müssen abwärtskompatibel sein !
    * Herausforderung die stärker in die Köpfe muss

Semantic Versioning
* Major Version bietet gewisses Featureset mit dem man abwärtskompatibel innerhalb dieser Version bleibt
* guter Zyklus für nächste Major Version mit der man alte Clients nicht mehr bedient?

Erster Schritt: 
* alte Clients in die Lage versetzen auf neue Version zu aktualisieren
    * bei Design der Schnittstelle den Clients mitgeben wie sie die neue Schnittstelle bedienen müssen
    * genügend Zeit
    * Idealfall Clients teilen mit wann sie die neue Schnittstelle umgesetzt haben (Consumer Driven Contracts)
    * nicht immer möglich
* Server so gestalten, dass er auch alte Clients unterstützt (aber alte Zöpfe auch mal abschneiden)
* Arnes Pattern: Zwei Major Versionen abwärts unterstützen (1 bis 2 Jahre für nächste Version) 

API: Hohes Maß an Disziplin für beide Seiten
* Tolerant Reader Pattern: 
    * Client tolerant gegenüber gewissen API-Änderungen (d.h. neue Attribute werden ignoriert)
    * Server muss dann auch beide Varianten verarbeiten können und anbieten
* Magnanimous Writer Pattern
    * Umbenennen von Attributen durch Kopieren
    * nicht das Alte entfernen

Fazit
* in der Praxis fehlen noch Konzepte die man Entwicklern an die Hand geben kann
* mit Microservices wird das aber kommen, da notwendig 