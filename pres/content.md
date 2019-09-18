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
TODO Polish image, highlight code
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
- aber: Fuß der Pyramide != Unittests (Microtests) 

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
]

.right-column[
### Isolierungsgrad
- **hoch**
  
  Unittests (Microtests), Mocking  

- **mittel**
  
  Komponententests, Tests mit Context / Abhängigkeiten (Beans)  

- **gering**
  
  Integrations-/Systemtests  
]

???
> FLO
- Zeichne Testpyramide auf Flipchart
- zeige Bezug der Aspekte zu ihr

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
TODO Schnittstelle von Tests (UI vs. Microtests)
---

.left-column[
### Motivation
### Aspekte der Test-pyramide
]

.right-column[
###Aussage
Was sagt mir der Test, wenn er gelingt oder fehlschlägt?  
- **Verifikation**: "arbeitet das System richtig?"
  
  *Isoliert, z.B. Mikrotests*

- **Validierung**: "macht das System das Richtige?  
  
  *Integrativ, z.B. Systemtests*
]

???
> MAX

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
- vgl. JUnit `@Tag`
- Risiko, wenn nicht regelmäßig ausgeführt

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
]

.right-column[
###Fokus vs. Abdeckung  

Wie erreicht man eine signifikante Aussage über den Code?  

- **auflistend**: Testen bestimmter Usecases, Grenzfälle oder Äquivalenzklassen
  
  *"Test by example" mit Microtests, Akzeptanztests*

- **aufspannend**: Testen wechselnder oder unbestimmter Fälle
  
  *z.B. durch Property-Tests*

]

???
> FLO
- Beispiel mit jqwik

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
TODO Ordentlich formatieren, siehe voriger Abschnitt
###Zweck:
- Dokumentation
- Regressionsschutz
- ausführbare Akzeptanzkriterien  
- formale, syntaktische, strukturelle Zusicherungen
- "Wartungszugang": z.B. Daten einspielen, exportieren
]

???
> FLO
z.B. prüfe ob alle JUnit Tests benannt sind nach *Test

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Zielgruppe und Syntax:
- Entwickler/Tester (technisch, Code-nah)
- Anwender/Fachbereich (natürlichsprachliche Frameworks wie Cucumber, FitNesse, Robot Test)
]

???
> FLO

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Entstehung:	
- test-first/TDD: zielt auf Testbarkeit, Abdeckung
- test-last/nachgelagert: Fokus auf Design, Fortschritt
- ex post/"archäologisch": Aufbau von Verständnis, Sicherheitsnetz
-> hilft, Tests zu beurteilen: entstanden aus Anforderungen oder nur "Gerüst" um Legacy-Code
-> mglw. an der Beschreibung (Methodenname, Titel) oder Setup des Tests erkennbar oder am Stil (generiert)
]

???
> MAX
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
  
  *bei Legacycode, Refactoring*

- **undefinierter Fixpunkt**, wenn beides gilt
  
  *z.B. wenn UI-Tests fehlschlagen: Anwendung reparieren oder Test anpassen?*
]

???
MAX
- Wo liegt die Wahrheit?
- Grundlegend: Was passe ich an im Falle eines roten Tests?

---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Lebenszeit:
- handgeschrieben/gepflegt
- Prototyping/Learning-Tests: Verstehen von Klassen, APIs
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
###Erstellung ohne/mit Unterstützung:
- handgeschrieben
- handgeschrieben, aber generierter Input (Property Tests)
- generierte Testfälle (z.B. testrecorder)
]

???
> FLO
---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Testort:
- ex situ/von außen (typisch): xUnit-Tests, Prüfung von Specs durch Frameworks
- in situ/im Code: z.B. Contract Tests (C4J), (Java) assert-Anweisungen
]

???
> FLO
---

.left-column[
### Motivation
### Aspekte der Test-pyramide
### Weitergehende Aspekte
]

.right-column[
###Zusammenfassung
TODO MAX Ergänzen, tabellarisch?

Aspekte der Testpyramide 					      |	Weitergehende Aspekte 
--------------------------------- | -------------------------
Isolierungsgrad		|	 tt
Bewertungskriterium        			|	  ee
Aussage						  |   
Häufigkeit der Ausführung		|	  
Fokus vs. Abdeckung | 
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
TODO DAVE
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
TODO MAX
]

???
> MAX