## CoP Testen - Testkonzepte 

### Motivation
Es gibt verschiedene Aspekte von Tests, die sich nicht nur an der Testpyramide festmachen lassen.  
Viele dieser Aspekte sind unabhängig voneinander. So kann man z.B. mit JUnit verschiedene Arten von Tests schreiben, oder Tests auf derselben Ebene der Testpyramide unterscheiden sich bzgl. ihrer Aspekten/Eigenschaften.

### Testarten & -technologien
*TODO im Verlauf vorstellen*
- Test by example (> MAX z.B. erstes JUnit Example aus ASE Javaweb)
- Property-based (> Florian) 
- Mutation Testing (> David?)
- Snapshot-Testing (> Max)
- parametrisierte Tests (> ?)

### "Mensch vs. Maschine", Mächtigkeit (weglassen?)
*TODO Achsendiagramm? Am Ende? Wie sinnvoll ist so eine harte Gegenüberstellung überhaupt?*  

manuell/punktuell 					      |	automatisiert/systematisch 
--------------------------------- | -------------------------
Funktion/Feature über UI prüfen		|	 Unit- oder Integrationstest 
parametrisierte Tests        			|	 Property-based Tests 
Code auskommentieren						  |  Mutation Testing (z.B. PIT) 
UI-Test/visuelle Verifizierung		|	 Snapshot-Testing 

### Eigenschaften von Tests
*Einige Aspekte lassen sich in der Testpyramide verorten*

Isolierungsgrad*:
- hoch: Unit-/Microtests, Mocking
- mittel: Komponenttests, Tests mit Context/Abhängigkeiten (Beans)
- gering: Integrations-/Systemtests

Bewertungskriterium*:
- funktional (was soll passieren)
- nichtfunktional (wie soll es passieren: Performanztests (Last, Durchsatz, Latenz, Parallelität), Sicherheits/Pen-Test)
- formal (wie stellt es sich dar: UI Tests)

Verifikation vs. Validierung*
- Verifikation: arbeitet das System richtig? Isoliert/Mikrotests
- Validierung: macht das System das Richtige? Integrativ/Systemtest

Häufigkeit der Ausführung* (vgl. JUnit @Tag):
- ständig (Entwicklung, IDE)
- punktuelle/wiederkehrend (Integration, CI-Server)
- anlassbezogen (Deployment, Produktionsumgebung)

Fokus vs. Abdeckung*:  
*Beispiel: jqwik Test*
- auflistend: bestimmte Usecases, Grenzfälle/Äquivalenzklassen (Unit-Tests, Akzeptanztests)
- aufspannend: beliebig viele/unbestimmte Fälle (Bsp. Property-Tests)

*Die folgenden Aspekte sind orthogonal zur Testpyramide*

Zweck:
- Dokumentation
- Regressionsschutz
- ausführbare Akzeptanzkriterien  
- "Wartungszugang": z.B. Daten einspielen, exportieren

Zielgruppe und Syntax:
- Entwickler/Tester (technisch, Code-nah)
- Anwender/Fachbereich (natürlichsprachliche Frameworks wie Cucumber, FitNesse, Robot Test)

Entstehung:	
- test-first/TDD: zielt auf Testbarkeit, Abdeckung
- test-last/nachgelagert: Fokus auf Design, Fortschritt
- ex post/"archäologisch": Aufbau von Verständnis, Sicherheitsnetz
-> hilft, Tests zu beurteilen: entstanden aus Anforderungen oder nur "Gerüst" um Legacy-Code
-> mglw. an der Beschreibung (Methodenname, Titel) oder Setup des Tests erkennbar oder am Stil (generiert)

Fixpunkt (führendes Kriterium/Wahrheit):  
*Beispiel: Example von https://github.com/maxbechtold/golden-master als Snapshot-Test*

"wie schreibe/betrachte ich meine Tests"

- Anforderung/Problemverständnis: Neu/Weiterentwicklung
- Status quo/Systemverhalten: Legacycode, Refactoring
- fehlt manchmal, z.B. wenn UI-Tests fehlschlagen: Anwendung reparieren oder Test anpassen?

Stabilität? (TODO unklar)
- fachliche vs. strukturelle Änderungen 

Lebenszeit:
- handgeschrieben/gepflegt
- Prototyping/Learning-Tests: Verstehen von Klassen, APIs

Erstellung ohne/mit Unterstützung:
- handgeschrieben
- handgeschrieben, aber generierter Input (Property Tests)
- generierte Testfälle (z.B. testrecorder)

Testort:
- ex situ/von außen (typisch): xUnit-Tests, Prüfung von Specs durch Frameworks
- in situ/im Code: z.B. Contract Tests (C4J), (Java) assert-Anweisungen

### Bewertung von Tests
*(Objektives Kriterium, Güte bzgl. Absicherung, nicht Wartbarkeit)*

Aussagekraft:
- Code Coverage
- Mutation Testing

Wiederholbarkeit der Messung:
- Testunabhängigkeit (z.B. permutierte oder parallele Ausführung)
- geringe/stabile vs. hohe/variable Dauer der Ausführung

### Fazit
- Auseinandersetzung mit Aspekten von Tests
- Inspiration für eigene Projekte 

### TODOs
- *TODO FLO MAX Beispiele für Testtechnologien finden*
- *TODO MAX Dave ansprechen zu PIT*


