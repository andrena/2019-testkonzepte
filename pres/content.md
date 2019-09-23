layout: false
class: center, middle

# Community of Practice Testen 
## Episode III

### Testkonzepte

---

.left-column[
]

.right-column[
## Agenda
<br/>

1. Motivation
2. Aspekte der Testpyramide
3. Weitergehende Aspekte
4. Bewertung von Tests
5. Fazit
]

???
> MAX

---

background-image: url(img/starter-preliminary-small.png)

.left-column[
### Motivation
]

.right-column[
]

???
> MAX
- verschiedene Dimensionen/Aspekte anreißen
- erster Beispiel-Test aus ASE Javaweb

---

.left-column[
### Motivation
]

.right-column[
### Fragen und Ziele
- Was charakterisiert Tests?
- Wie unterscheiden sich Tests?
- Wie sollte ich Tests betrachten?

**Ziele**
- besseres Verständnis der Testbasis eigener Projekte 
- Ideen und Ansatzpunkte zu deren Weiterentwicklung
]

???
> MAX
- typisch andrena: unterscheide Tests anhand der Testpyramide
- aber: vielleicht nicht alles

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
]

.right-column[
### Isolierungsgrad
- **hoch**
  
  Unittests/Microtests (Mocking)

- **mittel**
  
  Komponententests, Tests mit Kontext / Abhängigkeiten

- **gering**
  
  Integrations-/Systemtests  
]

???
> FLO
- Microtests als Begriff einführen
  - Begriff Unittests überladen, wird auch für integrativere Tests gebraucht
- Zeichne Testpyramide auf Flipchart (auf drei Ebenen beschränken: Microtests, Komponententests, Integrations-/Systemtests)
- zeige Bezug der Aspekte zu ihr
- Black-/White-Box (typischerweise: je "dunkler" desto stabiler gegenüber Refactorings)
- Menge des getesteten/durchlaufenen Codes pro Test

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
]

.right-column[
### Bewertungskriterium
Was wird geprüft?  
- **funktional**, "was soll passieren"

  *typisch, Eingabe/Ergebnis-basiert*

- **nichtfunktional**, "wie soll es passieren"  

  *Performanztests (Last, Durchsatz, Latenz, Parallelität), Sicherheits/Pen-Test*

- **formal**, "wie stellt es sich dar"  
  
  *UI-Tests, Approval-Tests*
]

???
> MAX
Anderes Merkmal von UI-Tests: Schnittstelle ( vs. Microtests, Systemtests)
---

.left-column[
### Motivation
### Aspekte der Test-pyramide
]

.right-column[
###Aussage
Was sagt mir der Test, wenn er gelingt oder fehlschlägt?  
- **Verifikation**: "arbeitet das System richtig?"
  
  *Blick auf Details, z.B. mit Mikrotests*

- **Validierung**: "macht das System das Richtige?  
  
  *Blick auf das Ganze, z.B. mit Akzeptanztests*
]

???
> MAX
- beides wichtig, Ying/Yang
  
---

.left-column[
### Motivation
### Aspekte der Test-pyramide
]

.right-column[
###Häufigkeit der Ausführung
Wann und wie oft laufen die Tests?  
- **ständig**  
  
  während Entwicklung, in IDE

- **punktuell/wiederkehrend**
  
  zur Integration, auf CI-Server

- **anlassbezogen** 
  
  zum Deployment, z.B auf Produktionsumgebung
]

???
> FLO
- Gründe für nicht ständige Ausführung:
  - Laufzeit
  - Kosten der Ausführung (kostenpflichtige Schnittstelle)
  - (In-)Stabilität von Schnittstellen
- Risiko, wenn nicht regelmäßig ausgeführt
  - spätes Feedback
  - Tests nicht mehr funktionsfähig
- Technische Möglichkeit zur Gruppierung: JUnit `@Tag`
- Für Eclipse: Infinitest Plugin

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
]

.right-column[
###Fokus vs. Abdeckung  

Wie erreicht man eine signifikante Aussage über den Code?  

- **auflistend**

  Testen bestimmter Usecases, Grenzfälle oder Äquivalenzklassen
  
  *"Test by example" mit Microtests, Akzeptanztests*

- **aufspannend**

  Testen wechselnder oder unbestimmter Fälle
  
  *z.B. durch Property-based Tests*

]

???
> FLO
- Beispiel mit jqwik
- Parametrisierte Tests als Zwischenform, eigentlich auflistend, aber vereinfacht Setup, sodass viele Usecases mit wenig Aufwand getestet werden können 
---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Zweck
- **Regressionsschutz**
- **Dokumentation**
- **ausführbare Akzeptanzkriterien**
- **formale, syntaktische, strukturelle Zusicherungen**
- **"Wartungszugang"**

  *z.B. Daten einspielen/exportieren*
]

???
> FLO
- Regressionsschutz: bei Umbau/Refactoring
- Dokumentation: wie benutzt man eine Klasse/Komponente
- Akzeptanzkriterien: was soll fachlich passieren
- Zusicherungen: keine fachliche Prüfung, z.B. prüfe ob alle JUnit Tests benannt sind nach *Test, Zugriff zwischen Komponenten prüfen (ArchUnit), Zyklenprüfung
- Wartungszugang: z.B. Cdi-Context aufsetzen mit Framework um Rest-Service aufzurufen

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Zielgruppe und Syntax
- **Entwickler/Tester**

  technisch, Code-nah

- **Anwender/Fachbereich**

  natürlichsprachliche Frameworks wie Cucumber, FitNesse, Robot Test
]

???
> FLO
- Entwickler: Tests in gleicher Sprache wie produktiver Code
- Tester: z.B. Selenium IDE (Browser Plugin zum Aufzeichen und Abspielen von Selenium Tests)
- Tester manchmal auch eher zweiter Kategorie zuzuordnen
- Anwender/Fachbereich
  - keine tieferen technischen Kenntnisse nötig, wenn Glue Code von Entwicklern aufgesetzt wird
  - Fokus auf fachliche Konstellationen und nicht auf technisches Grundgerüst

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Entstehung
Wie kam es zum Test?

- **test-first**, zielt auf Testbarkeit, Abdeckung
  
  *z.B. mit TDD*

- **test-last**, Fokus auf Design, Fortschritt

  *Code schreiben, im Anschluss testen*

- **ex post**, Aufbau von Verständnis, Sicherheitsnetz
  
  *"archäologisches" Vorgehen*
]

???
> MAX
- Frage: wer hat schon Erfahrung mit *ex post*?
- mglw. an der Beschreibung (Methodenname, Titel) oder Setup des Tests erkennbar oder am Stil (generiert)
- hilft, Tests zu beurteilen: entstanden aus Anforderungen oder nur "Gerüst" um Legacy-Code
- Beispiel: Example von https://github.com/maxbechtold/golden-master als Snapshot-Test

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Fixpunkt 

Wie schreibe/betrachte ich die Tests? Was ist die Prämisse?

- **Fixpunkt Tests**, es gelten Anforderungen

  *z.B. Neu-/Weiterentwicklung*

- **Fixpunkt Code**, es gilt der Status quo, das Systemverhalten
  
  *bei Legacy-Code, Refactoring*

- **undefinierter Fixpunkt**, wenn beides gilt
  
  *z.B. wenn UI-Tests fehlschlagen: Anwendung reparieren oder Test anpassen?*
]

???
MAX
- Frage: Was mache ich im Falle eines roten Tests?
- Wo liegt die Wahrheit?

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Lebenszeit
Wie lange überdauern Tests?

- **eher lang**: handgeschriebene Tests, erfordert Pflegen
  
  *z.B. Integrationstests, Microtests*

- **eher kurz**: automatisiert erstellt, leicht neu generiert

  *z.B. Snapshot-Tests, gelten nur für aktuellen Stand der Codebasis*

- **gar nicht**, Tests gelangen meist nicht mal ins Repo

  *z.B. Tests zum Prototyping oder Learning-Tests: Verstehen von Klassen, APIs*
]

???
MAX
---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Erstellung
ohne/mit Tool Unterstützung:

- **handgeschrieben**

- **handgeschrieben, aber generierter Input**

  *Property-based Tests*
- **aufgezeichnete Testfälle**

  *z.B. Testrecorder*
]

???
> FLO
- Standardfall: handgeschrieben
- Testrecorder von Stefan
- ggf. generierte Testfälle erwähnen
---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Testort
- **ex situ/von außen**

  getrennt vom Code

  *xUnit-Tests, Prüfung von Specs durch Frameworks*

- **in situ/im Code**

  *z.B. Contract Tests (C4J), (Java) assert Anweisungen*
]

???
> FLO
- "von außen" ist typisch, dabei werden Tests nicht durchlaufen, wenn Anwendung läuft 
---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Zusammenfassung

Aspekte der Testpyramide  |	Weitergehende Aspekte 
--------------------------------- | -------------------------
Isolierungsgrad		|	Zweck
Bewertungskriterium        			|	  Zielgruppe und Syntax
Aussage						  |   Entstehung
Häufigkeit der Ausführung		|	  Fixpunkt
Fokus vs. Abdeckung     |  Lebenszeit
                     |  Erstellung
                     |  Testort
]

???
> FLO

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
### Bewertung von Tests
]

.right-column[

]

???
> DAVE


---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
### Bewertung von Tests
### Fazit
]

.right-column[
### Abschließend

- wenig Neues, sondern Einordnen von Bekanntem
- Anreiz um Property, Mutation oder Snapshot-Testing auszuprobieren?
]

???
> MAX