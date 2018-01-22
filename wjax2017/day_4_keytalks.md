##Spring 5.0 und Spring Boot 2.0 ein Überblick
###Oliver Gierke
* JavaSE 8 baseline
* JDK 9 Konpatibilität durch automatische Module
* Aktualisierung der JavaEE -> 7 baseline, ServletAPI 3.1, JPA 2.1, JMS 2.0 Bean Validation 1.1
* Support ausgewählter JavaEE 8 APIs
* JDK 9 Support
  * Compact Strings (JVM)
  * G1 Gc als Default (JVM)
  * TLS protocol stack(JVM)
  * automatische Modulnamen (JIGSAW)
  * Empfehlung noch im classpath mode laufen zu lassen 
* HTTP/2 support via Servlet 4.0
* JUnit 5 support (Framework support, Dependency Injection capabilities, Meta Annotationen)
* funktionale Erweiterungen (ApplicationContext erstellen über Supplier und BeanDefinitions-Anpassungen)

<< Beispiel >>

Erweiterungen hinsichtlich Reactive Programming
* Subscription basiert
* Two pahse execution: 1. build up pipeline 2. once the data starts flowing
* Lazy execution: Nichts passiert bis Jemand subscribed
* Backpressure: Subscriber signals capability to handle amount of data

Spring WebFlux
* reaktive Antwort auf Spring MVC
* gibt ein Flux oder Mono zurück
* Servlet API vs. Spring Web Reactive API
* Servlet container vs. Netty, Undertow, Servlet 3.1

Spring Boot 2.0
* Upgrade auf J8 und Spring 5
* Infrastruktur: Jetty 9.4, Tomcat 8.5, Hibernate 5.2
* Reactive web test support
* OAuth 2.0 support -> Spring Security
* Tweak the defaults

Pruning
* Deprecations von 1.5
* CRaSH project (shell)
* Spring Loaded (Hot Swapping)


##Die Top-Hacks der letzten Monate - Schlimmer geht immer
###Christian Schneider
* This Book Reads You
  * ePub files = zip-File
  * enthält Content und XML files
  * xml mit dtd -> parsebar -> XXE Attack
  * Amazon parsed ePub Files -> Amazon schickte Craig Arendt die /etc/passwd (iTunes, Adobe Reader)
  * Lesson: Wo ist XML enthalten: *.xlsx, *.docx, *.pptx
* Look Mum, I'm on TV
  * Smart TV Settings (Sven Morgenroth)
  * Fernseher Namen vergeben: \`sleep 5\` (Linux command execution)
  * 5 Sekunden in Sleep Modus versetzt.
  * danach konnte er ihn rooten
  * Lesson: keine input-Validierung
* Parse me if you can
  * April 2017
  * Office 365 Schutz gegen maliziöse Links (Safe Link Technology)
  * Wie erkennen sie diese Links?
  * Pattern matching
  * in 5 Minuten gehackt
* Keys to the Kingdom
  * Last Pass Password Manager parsed die aktuelle URL des Browsers
  * unintelligentes Parsen: @-Zeichen nur das letzte Vorkommen
  * Domain?
    * http://example.com/@twitter.com/@foobar
    * Browser sagt: example.com
    * LastPass: twitter.com -> Passwort reingesetzt
    * fix incomplete: data-Url: data


##Java Flight Recorder - So funktioniert das Java-Profiling-Tool
###Wolfgang Weigend

##Testgetriebene Entwicklung bei funktionalem Code - Alles gleich oder alles anders?
###Johannes Link

##Visuelle Regressionstests im Web als praktikable Alternative zu E2E-Tests?!
###Frederik Martin