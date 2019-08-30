layout: false
.left-column[
## Beyond Java
]
.right-column[
### .NET-Portierung

- fokussiert auf Metriken

- Unterstützung bis Visual Studio 2013

- https://github.com/usus/Usus.NET

### Und Android?

- Usus analysiert auch native Apps in Java

- Tipp: Android-unabhängige Module durch .green[Clean Architecture]

- Erfordert Eclipse (kein Android Studio/IntelliJ-Support)
]

---

layout: false
.left-column[
## Contribute!
]
.right-column[
> *"ask not what your country can do for you — ask .green[what you can do] for your country"*

### Aller Anfang ist schwer

Plug-Ins haben eine gewöhnungsbedürftige Struktur

- "breiter und flacher" als eigenständige Applikationen

- kein `main(String... args)`, stattdessen XML-Konfiguration

- Plug-In ist Singleton, viele Klassen/Methoden `static`
]
--
.right-column[
Voraussetzungen

- Java 6+, RCP/PDE-Kenntnisse sind hilfreich

- https://github.com/usus/usus-plugins/wiki/DevelopmentRequirements
]

---

layout: false
.left-column[
## Contribute!
]
.right-column[
### Tipps

Einstiegspunkte anschauen
- Metriken ergänzen: https://github.com/usus/usus-plugins/commit/33fd75

- Erweiterungen der Class/Package Graph Views: https://github.com/usus/usus-plugins/pull/47 (oder [#53](https://github.com/usus/usus-plugins/pull/479))

Bei Issues/Feature Requests einsteigen
- https://github.com/usus/usus-plugins/issues?q=is:issue+is:open+-label:Bug/Regression
]

---
layout: false
.left-column[
## Fragen/Kritik
]

--
.right-column[

<br>
<br>
<br>
.center[ [![](https://marketplace.eclipse.org/sites/all/themes/solstice/public/images/marketplace/btn-install.png)](http://marketplace.eclipse.org/marketplace-client-intro?mpc_install=1089 "Drag to your running Eclipse* workspace. *Requires Eclipse Marketplace Client") ]

.center[ [![](https://marketplace.eclipse.org/sites/default/files/usus-marketplace.png)](http://projectusus.org) ]

<br>
<br>

.center[ [maxbechtold.github.io/slides](https://maxbechtold.github.io/slides) ]
]
