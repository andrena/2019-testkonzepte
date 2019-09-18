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
4. Bewertung von Tests (?)
5. Fazit
]

---

background-image: url(img/starter-preliminary.png)

.left-column[
### Motivation
]

.right-column[
TODO Polish image, highlight code
]

???
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
- vgl. JUnit `@Tag`

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
- FLO: Beispiel mit jqwik
