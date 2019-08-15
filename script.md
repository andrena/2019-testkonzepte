## CoP Testen - Testkonzepte 

### Motivation
Es gibt verschiedene Arten von Tests, die sich nicht nur an der Testpyramide festmachen lassen.
Viele Aspekte sind unabhängig voneinander, z.B. kann man mit JUnit verschiedene Arten von Tests schreiben, oder Tests auf derselben Ebene der Testpyramide unterscheiden sich in vielen Aspekten/Eigenschaften


### Testarten & -technologien
TODO im Verlauf vorstellen
Test by example (Aufhänger)
Property-based (> Florian) 
Mutation Testing (> David?)
Snapshot-Testing (> Max)
parametrisierte Tests
Contract Testing?

### "Mensch vs. Maschine", Mächtigkeit (weglassen?)
TODO Achsendiagramm? Am Ende?
*manuell/punktuell 					<->		automatisiert/systematisch*
Funktion/Feature über UI prüfen				Unit- oder Integrationstest
parametrisierte Tests						Property-based Tests
Code auskommentieren						Mutation Testing (z.B. PIT)
UI-Test/visuelle Verifizierung				Snapshot-Testing

### Eigenschaften von Tests
TODO Zusammenhang mit Testpyramide*/Aufteilung dieses Abschnitts
Isolierungsgrad*:
  hoch: Unit-/Microtests, Mocking
  mittel: Komponenttests, Tests mit Context/Abhängigkeiten (Beans)
  gering: Integrations-/Systemtests
Zweck:
  Dokumentation
  Regressionsschutz
  ausführbare Akzeptanzkriterien 
Bewertungskriterium*:
  funktional (was soll passieren)
  nichtfunktional (wie soll es passieren: Performanztests (Last, Durchsatz, Latenz, Parallelität), Sicherheits/Pen-Test)
Entstehung:
  test-first/TDD: zielt auf Testbarkeit, Abdeckung
  test-last/nachgelagert: Fokus auf Design, Fortschritt
  ex post/"archäologisch": Aufbau von Verständnis, Sicherheitsnetz
  -> hilft, Tests zu beurteilen: entstanden aus Anforderungen oder nur "Gerüst" um Legacy-Code
  -> mglw. an der Beschreibung (Methodenname, Titel) oder Setup des Tests erkennbar oder am Stil (generiert)
Zielgruppe und Syntax:
  Entwickler/Tester (technisch, Code-nah)
  Anwender/Fachbereich (natürlichsprachliche Frameworks wie Cucumber, FitNesse, Robot Test)
Häufigkeit der Ausführung* (vgl. JUnit @Tag):
  ständig (Entwicklung, IDE)
  punktuelle/wiederkehrend (Integration, CI-Server)
  anlassbezogen (Deployment, Produktionsumgebung)
Fokus vs. Abdeckung*:
  auflistend: bestimmte Usecases, Grenzfälle/Äquivalenzklassen (Unit-Tests, Akzeptanztests)
  aufspannend: beliebig viele/unbestimmte Fälle (Bsp. Property-Tests)
Fixpunkt (führendes Kriterium/Wahrheit):
  Anforderung/Problemverständnis: Neu/Weiterentwicklung
  Status quo/Systemverhalten: Legacycode, Refactoring
  Indeterministisches Verhalten, z.B. bei UI-Tests: kein klarer Fixpunkt
Stabilität?
  fachliche vs. strukturelle Änderungen 
Lebenszeit:
  handgeschrieben/gepflegt
  Prototyping/Learning-Tests: Verstehen von Klassen, APIs
Erstellung ohne/mit Unterstützung:
  handgeschrieben
  handgeschrieben, aber generierter Input (Property Tests)
  generierte Testfälle (z.B. testrecorder)
Testort:
  ex situ/von außen (typisch): xUnit-Tests, Prüfung von Specs durch Frameworks
  in situ/im Code: z.B. Contract Tests (C4J), (Java) assert-Anweisungen
Validierung vs. Verifikation*
  Validierung: macht das System das Richtige? Integrativ/Systemtest
  Verifikation: arbeitet das System richtig? Isoliert/Mikrotests

### Bewertung von Tests
(Objektives Kriterium, Güte bzgl. Absicherung, nicht Wartbarkeit)
Aussagekraft:
  Code Coverage
  Mutation Testing
Wiederholbarkeit der Messung:
  Testunabhängigkeit (z.B. permutierte oder parallele Ausführung)
  geringe/stabile vs. hohe/variable Dauer der Ausführung

### Fazit
Auseinandersetzung mit Aspekten von Tests
Inspiration für eigene Projekte 

TODO FLO MAX Beispiele für Testtechnologien finden
TODO MAX Dave ansprechen zu PIT
TODO MAX Repo aufsetzen auf andrena GitHub
TODO remark.js auf andrena.github.io
TODO FLO Doodle abklären

