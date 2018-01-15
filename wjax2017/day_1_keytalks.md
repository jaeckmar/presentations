#Agile Day

##Feuer plus Wasser - Das agile Pflichtenheft
###Dr. Carola Lilienthal
* Softwareentwicklung und Integration in vorhandene IT-Landschaften = Expedition ins Ungewisse
* in behördlichem Umfeld -> Pflichtenheft, Festpreis, Projektplan/Laufzeit,

Baumaßnahmen in HH
* bisher verschiedenste Softwarelösungen für Ingenieure
* kein System das alle Departments vereint
* Idee: Softwarelösung zur Planung von Bauvorhaben

1. Machbarkeitsstudie
    - **alle** Mitarbeiter in Workshops
    - **W**er macht **W**as **W**omit **W**ozu? (Gegenwart analysieren)

2. Grober Projektstrukturplan mit MVPs
    * ! PO auf Beamtenseite mit Entscheidungsmöglichkeit
    * ! Iterationen müssen abgenommen sein

3. Lebendes Backlog
    * Klärung am Anfang über das Vorgehen von Zurückstellen von Stories
    * Wichtig sind Zwischenabnahmen bei Features
 

##Agilität braucht technische Exzellenz
###David Tanzer
* Geht das (SCRUM) mit ausschließlich juniorigen Entwicklern?
* Vorstellung von 7 Antipatterns (bei Kunden gesehen)
1. Agile Theater (Behauptung Agile zu sein ist es aber nicht) 
    * Lange Entscheidungswege
    * lange LeadTime: Requirements bis Deliverables (Produktbacklog bis Produktion -> 6 Monate)

2. Feature Factory
    * agile Entwicklung nur dazu da möglichst schnell und effizient Requirements in Code umzuwandeln - sonst alles egal
    * Features bauen wie in einer Fabrik
    * Success Theater:
      * Sobald etwas ausgeliefert wurde wird gefeiert, egal ob das Feature dem Kunden was bringt oder nicht
      * Stille Post statt echter Übergaben
      * Velocity Addiction: Geschwindigkeit beibehalten führt zu keiner Zeit fürs Refactoring (1/3 neue Arbeit, 2/3 Rework, 10% Meetings)
    * Userstories sind nicht richtig geschrieben
    * zu große Lieferungen
    * POs überprüfen nicht mehr
    * Teams kennen die Auswirkungen ihrer Arbeit nicht

3. Product Backlog Bankruptcy
    * Backlog hat ein nicht mehr handlebares Ausmaß erreicht (anstatt sortierte Liste 1xPlatz 1, 1xPlatz 2, 1xPlatz 3 und einen letzten Platz!)
    * zu viele Items
    * sehr lange Lead Times
    * Schätzungen stimmen nicht
    * falsches Verständnis vom Backlog (Wunschliste)
    * PO muss auch **Nein** sagen dürfen und können
    * zu lange Deadlines
    * Team braucht eine Produkt-Vision um auch Nein sagen zu können

4. Architecture Madness
    * neue Features dauern immer länger
    * BUGs beheben dauert und produziert neue BUGs
    * es gibt wenige Leute, die den Code wirklich kennen
    * es gibt NoGo-Areas im Code
    * es gibt einen Architekt (nur der kennt sich aus)
    * Architektur und Design sind unveränderlich (haben wir schon immer so gemacht)
    * immer wieder mal schlampig gearbeitet -> schlechte Architektur/Design, daraus folgt Änderungen schwieriger (Teufelskreis)
    * IT Unternehmen kann dann den Marktdruck spüren (Entwicklung nicht mehr schnell genug)
    * ! alle sind für Architektur zuständig
    * ! regelmäßige Design-Sessions
    * ! UML-Diagramme im Sprint-Planning, stets und ständig durch Coach eingefordert
    * ! kontinuierliches Refactoring

5. Refactoring Backlog, Team Backlog
    * Dinge die das Team gern machen würde aber nicht tut, nicht tun darf

6. Burnout by a thousand babysteps
    * Daily Scrum wird zum Management Report
    * agile Zyklen werden benutzt, um weiteren Druck aufzubauen
    * Druck dann nicht mehr 1x im Jahr sondern alle 2 Wochen
    * purer Effizienzgedanke

7. Operations
    * Was haben wir mit Operations zu tun
    * Zusammenarbeit funktioniert nicht mehr richtig

SCRUM-Coaches sagen meist: "Die Probleme waren vorher schon da, Scrum zeigt sie euch bloß"

##Technologieentscheidungen in selbstorganisierten Teams
###Konstantin Diener
* Technologieentscheidungen von Entwicklern in den Teams
* kein CTO, kein Architekt!
* dennoch Streit: Jeder will mitreden, unterschiedlichste Meinungen
* Talk: Praxisbericht über sinnvolle Rahmenbedingungen für Technologieentscheidungen

<<teamentscheidungen.png>>

* Team hat alle nötigen Informationen
* fehlenden Informationen werden besorgt 
* you build it, you run it!

ABER oft:
* "einsamer Wolf"
* bring your own pet technology
* Damit kenne ich mich nicht aus
* Wir haben etwas entschieden?
* gesamte Firma hat eine Meinung
* "Schatten-CTOs"

Möglichkeiten
1. 3-Personen-Regel
    * diese müssen in der Lage und
    * Willens sein, die entsprechende Sprache/Technologie zu supporten
    * Tradeoff: Innovation vs. Wildwuchs
2. Es entscheidet wer nachts aufsteht

Teamentscheidungen
* Was entscheiden wir ?
* Nach welchen Kriterien ?
* Was sind die Optionen ?
* Wer gehört zum Team ?
* Wer sind maßgebliche Experten ?

Teamübergreifende Entscheidungen/ Kommunikation
* @Spotify
* (Squads), das gleiche Arbeitsumfeld (Tribes), die gleichen Fähigkeiten (Chapters) oder Interessen (Guilds)
* Communities of Interests (Guild)
* Communities of Practice
    * gemeinsame Standards
    * Alltagsprobleme lösen
    * Wissen verteilen
    * Innovation treiben
    1. Helping Communities
    2. Best Practice Communities
    3. Knowledge Stewardessing Communities
    4. Innovation Communities
* Teilnahme bei CoP ist freiwillig aber wertvoll
