## Veranstaltung Programmierung 2, UIB
### Dozent: Prof. Dr. Frank Dopatka

[zurück zur Hauptseite...](https://informatik-mannheim.github.io/iExpo-Sommer-2021/)


**Was hat unser Team dieses Semester gemacht?**

Wir haben uns im Sinne unserer Studienleistung mit der Programmierung eines Uno Spiels als Team beschäftigt.
Zusätzlich mussten wir in Eigenleistung Lehrvideos zum gegebenen Vorlesungsthemen drehen.

**Wer gehörte zu unserem Team?**

Unser Team bestand aus David Silva Goncalves, Tristan Gräble, Johannes Kramberg, Katharina Korst und Samed Mollamehmetoglu.


## Semesterspiel UNO
Die Programmierung des Uno Spiels wurde in folgende drei Teile aufgeteilt:


**Teil 1:**

Der erste Teil bestand aus dem groben Konzept der verschiedenen Klassen, in die wir nach und nach die Spiellogik implementierten. 
Dieses beinhaltete das Testgetriebene entwickeln unter der Benutzung von JUnits und die Verwendung eines eigenen Exception Handlings. 
Auch war es sehr wichtig alles detailliert mit Java Docs zu dokumentieren.
Im Laufe der Zeit hatten wir nicht nur ein grobes Konzept der Regeln, sondern ein ausführbares Spiel mit Spielern.

Hier ist ein Beispiel unseres aktuellen Package-Explores, welcher seit Beginn die gleiche Struktur aufweist, bis auf die Ki- und Gui-Komponenten, die erst im weiteren Verlauf des Semesters dazu kamen.

![Package Explorer](https://user-images.githubusercontent.com/72968168/123871821-7e92aa80-d934-11eb-8ca2-76fca07132ad.jpg)


Hier ein Beispiel unserer Spiel-CLI:

![Spiel-CLI](https://user-images.githubusercontent.com/72968168/123871826-82263180-d934-11eb-8da4-07d0edab8933.jpg)



**Teil 2:**

In diesem Abschnitt wurde ein großer Fokus auf das Implementieren von KI´s, dem Speichern/Laden und der Verwendung von Interfaces gesetzt.
Deshalb setzte sich ein Teil unseres Teams daran die Spiellogik nun auch für zwei verschiedene KI´s umzusetzen. 
Die KI bekam zwei Typen: Offensiv, sowie Defensiv.

![KI](https://user-images.githubusercontent.com/72968168/123871832-85212200-d934-11eb-9883-0343ff721000.jpg)


Der andere Teil des Teams beschäftigte sich während dessen mit dem Laden und Speichern im CSV und Serialisierten Format.
Somit nahm das ganze Spiel Gestalt an und konnte nun sogar gespeichert werden.

![speichern](https://user-images.githubusercontent.com/72968168/123871842-86eae580-d934-11eb-932c-9300d32a64b4.jpg)



**Teil 3:**

Im letzten Abschnitt durften wir nun das ganze in ein Graphical User Interface einbetten. Zudem kamen auch Themen des Multi Threading der KI hinzu. 
Also bekamen unsere KI´s beim Instanziiren noch jeweils einen eigenen Thread und konnten nun unabhängig vom Main Thread existieren.
Des weiteren brauchten wir noch die Möglichkeit jeden Spielzug nachzuvollziehen. Deshalb bekam unser Programm noch einen selbst erstellten Logger hinzu.

Hier ein Beispiel unseres Hauptmenüs:
![Uno-Hauptmenue GUI](https://user-images.githubusercontent.com/72968168/123870003-04f9bd00-d932-11eb-97c9-b0a6f705d1d6.jpg)

Hier ein Beispiel unseres Spielfelds:
![Spielfeld](https://user-images.githubusercontent.com/72968168/124031968-3dfc6500-d9f8-11eb-9e7d-cb0dfef4ff71.jpg)



## Individuelle Leistungen - Lehrvideos

Jeder von uns musste insgesammt vier Videos zu einem zugeteilten Inhalt drehen. Der Inhalt war immer Teil des Vorlesungsstoffs, den wir aufgriefen und diesen 
zusätzlich noch mit eigenen Beispielen untermalten. Dabei war es sehr wichtig "nichts nachzuplappern".
Somit musste man in Eigenleistung beweisen, den Vorlesungsstoff außerhalb des Semesterspiels zu beherrschen.



**David Silva Goncales**


**1.Video Objekt-Eigenschaften-Getter-Setter-Konstruktoren**

![Bild_1_David](https://user-images.githubusercontent.com/72968168/124028752-a8aba180-d9f4-11eb-9fc0-3531448b6156.jpg)

Dieses Video dreht sich stark um die Grundlagen der Objektorientierten Programmierung. Zuerst wird gezeigt wie Objekte mit Ihren Eigenschaften und Attributen angelegt werden können, sowie die Rolle des Konstruktors dabei. 
Des Weiteren werden die Getter und Setter Hilfsmethoden anhand des Quellcodes erklärt.


**2.Video Versionsverwaltung-zentral-verteilt-GIT. Die typischen GIT-Funktionen sind dabei ausgehend von einem leeren Eclipse-Projekt live im Video zu zeigen.**

![Bild_2_David](https://user-images.githubusercontent.com/72968168/124028770-acd7bf00-d9f4-11eb-999d-b65158a112cb.jpg)

Das zweite Video handelt von Versionsverwaltungssystemen, insbesondere um Git. Es zeigt welche Funktion es bietet, um als Team am Quellcode zu arbeiten.
In diesem Video wurde auch ein Merge Konflikt gelöst. Dieses Video finden Sie auch auf dem Youtube Kanal von Herrn Prof. Frank Dopatka  [Versionsverwaltungssysteme und GIT mit Java in Eclipse](https://www.youtube.com/watch?v=DZAdtgJMw6g&ab_channel=FrankDopatka){:target="_blank" rel="noopener"}.


**3.Video Steuerelemente und Ereignisse in Swing**

![Bild_3_David](https://user-images.githubusercontent.com/72968168/124028791-b103dc80-d9f4-11eb-8654-3cb5ec440ed3.jpg)

Im dritten Video habe ich die wichtigsten Steuerelemente der Swing-Gui vorgestellt und die Behandlung von Ereignissen dargestellt, bezogen auf das klick Event. 
Mein Beispiel in diesem Video war eine abstrakte Darstellung einer Pizza Bestellung. 


**4.Video Collections: Comparator, Iterator, Map, Properties, Wildcards**

![Bild_4_David](https://user-images.githubusercontent.com/72968168/124028807-b52ffa00-d9f4-11eb-9447-7446ba0d2a54.jpg)

In Video 4 habe ich anhand einer TreeMap die Funktionen des Compareable interface gezeigt, sowie die Funktionen eines Iterators.
Dies wurde durch ein Beispiel der Europa-Meisterschaft realsiert. Abgesondert davon bin ich auf die Wildcars und Properties
eingegangen und welche Funktion diese 2 Konzepte bieten. 



**Tristan Gräble**


**1.Video Anweisungen-Datentypen-Operatoren-Konstanten sowie UML-Aktivitätsdiagramm-Verzweigungen-if-else-switch**

![Bild 1 Tristan](https://user-images.githubusercontent.com/72968168/124028893-cf69d800-d9f4-11eb-87b3-77f0fbb9449a.jpg)

In Video 1 habe ich Primitive Datentypen und Referenztypen vorgestellt und verglichen. Zusätzlich habe ich arithmetische-, Bit- und Vergleichs Operatoren anhand Beispielen gezeigt. Desweiteren bin ich auf das Konvertieren von Datentypen im automatischen, sowie im manuellen Type-Cast eingegangen. Der zweite Teil des Videos handelte von den Grundlagen der UML mit Beispiel eines Aktivitätsdiagramm mit Verzweigungen. Auf diese Verzweigungen bin ich daraufhin gesondert in Java eingegangen, sodass ich anhand Beispielen if, else und switch zeigen konnte.


**2.Video Exception-Handling-Strukturierung**

![Bild 2 Tristan](https://user-images.githubusercontent.com/72968168/124028906-d395f580-d9f4-11eb-8692-e79e2e488ebb.jpg)

Im zweiten Video habe ich mich mit Exception-Handling und der Strukturierung größere Software Projekte befasst. Hierzu habe ich zunächst Exception selbst erklärt und dessen Vererbungshierarchie gezeigt. Im weiteren Verlauf des Videos habe ich anhand eines des Altersnachweises Try und Catch von Exceptions gezeigt. Daraufhin habe ich Java-Konstrukte zur Strukturierung von Objekten erläutert.


**3.Video Definition von Interfaces, deren Implementierung und Verwendung**

![Bild 3 Tristan](https://user-images.githubusercontent.com/72968168/124028921-d7297c80-d9f4-11eb-9101-2e19279fe8fa.jpg)

In Video drei bin ich auf Interfaces in Java eingegangen. Dazu habe ich anhand eines Modells erst das Prinzip eines Interfaces erklärt. Anschließend mit einem Beispiel einer DrachenKlasse und eines DrachenInterfaces dies in Eclipse gezeigt.


**4.Video funktionale Programmierung: Paradigmen, Funktional, Lambda, Closure**

![Bild 4 Tristan](https://user-images.githubusercontent.com/72968168/124028930-da246d00-d9f4-11eb-8b66-34a0f9e7fcd0.jpg)

In meinem letzten Video habe ich Programmier Paradigmen erklärt und bin vor allem auf die Funktionale Programmierung eingegangen. Im zweiten Teil des Videos zeige ich Schlüsselwörter der Funktionalen Programmierung, wie Function, UnaryOperator, Consumer und Supplier. Daraufhin stellte ich ein Beispiel von Lambda vor und dessen Code-Reduzierung, sowie ein Beispiel zu Closure.



**Johannes Kramberg**


**1: Wiederholung: Objekt, Eigenschaften, Getter, Setter, Konstruktoren in Java**

![Bild 1 Johannes](https://user-images.githubusercontent.com/72968168/124028949-e14b7b00-d9f4-11eb-9ae9-c5622d745117.jpg)

In diesem Video habe ich Objekte im Zusammenhang mit deren Eigenschaften gezeigt. Dies habe ich am Beispiel eines Menschen genauer erläutert.
Da jeder Mensch einen Vor- & Nachnamen besitzt konnte ich diese dem Menschenobjekt zuweisen & diese im Konstruktor, also der Geburt eines Menschen setzen.
Um das Thema abschließend zu beenden, bin ich noch auf Konstruktor-Vererbungshierarchien eingegangen und habe gezeigt wie man mit Hilfe von Getter()-Methoden auf die Eigenschaften des Objektes von außen zugreift und diesen mit Hilfe von Setter()-Methoden neue Werte zuweisen kann.


**2: fortgeschrittene Programmierung: Komplexität, O-Notation, P und NP**

![Bild 2 Johannes](https://user-images.githubusercontent.com/72968168/124029544-8b2b0780-d9f5-11eb-8127-1f1693d2de6b.jpg)

Bei diesem zweiten Video habe ich mich mit dem Thema Komplexität hauptsächlich theoretisch beschäftigt. Dabei bin ich zuerst auf die Komplexitättheorie eingegangen, worum sich diese handelt und wozu man diese benötigt.
Damit die Komplexität anhand der sogenannten O-Notation vorgestellt. Dafür verwendete ich eine Veranschaulichung mit einem Graphen um den Unterschied zwischen P(in polynomialzeit lösbare Probleme) und NP(nichtdeterministisch in polynomialzeit lösbare Probleme) hervorzubringen. Hierzu habe ich die e-Funktion in Vergleich mit einer quadratischen Funktion gesetzt.
Desweiteren bin ich noch auf Laufzeitunterschiede eingegangen und habe zum Schluss noch den Dijkstra-Algorithmus(P) und das TravellingSalesmanProblem(NP) verglichen, da diese relativ ähnlich zueinander sind, jedoch verschiedene Komplexitätsklassen annehmen. Hierbei habe ich den Dijkstra-Algorithmus auch ausführlich vorgestellt.


**3: fortgeschrittene Programmierung: Innere Klassen**

![Bild 3 Johannes](https://user-images.githubusercontent.com/72968168/124029554-8e25f800-d9f5-11eb-952a-10acc4cfe94f.jpg)

Das 3. Video war im Vergleich zu den vorherigen ein etwas kürzeres Video. Dort habe ich die 4 verschiedenen Typen von inneren Klassen vorgestellt. 
Ich habe angefangen mit statischen inneren Klassen, bin dann weiter zu Mitglieds-/Elementklassen. Weiter ging es dann mit lokalen inneren Klassen und zum Schluss bin ich noch auf anonyme innere Klassen eingegangen.
Diese verschiedenen Arten habe ich dann versucht, vereinfacht mit Beispielen darzustellen.


**4: Datenstrukturen und Collections: Graphen, Dijkstra, Färbung**

![Bild 4 Johannes](https://user-images.githubusercontent.com/72968168/124029561-9120e880-d9f5-11eb-8abf-c7d1f6c860e7.jpg)

In diesem letzten Video habe ich die Theorie hinter Graphen angesprochen und anschließend gezeigt wie man solche in Quellcode darstellt. Im Anschluss habe ich dann den bereits geschriebenen Code verwendet um davon weitere Klassen abzuleiten und damit den Dijkstra-Algorithmus zu coden. Dessen Funktionsweise habe ich parallel dazu auch noch beschrieben.
Zum Abschluss bin ich dann noch auf die Theorie der Graphenfärbung eingegangen und diese anhand eines praktischen Beispiels abgebildet.



**Katharina Korst**

**1. Video Schleifen-for-each-do-while-Arrays sowie Funktion-Methode-Rekursion-fehlerhafte-Daten**

![Bild 1 Katharina](https://user-images.githubusercontent.com/72968168/124029576-954d0600-d9f5-11eb-8076-af1683ced4a3.jpg)

In diesem Video bin ich zunächst auf die Funktionsweise der zwei Sortieralgorithmen Bubblesort und Quicksort 
anhand einer bildlichen Darstellung eingegangen. Im weiteren Verlauf habe ich beide in Eclipse programmiert 
und nebenbei die Funktionsweise erklärt.
Um das ganze besser nachvollziebar zu machen verwendete ich unsortierte Listen und wendete beide
Algorithmen darauf an.


**2. Video Bubblesort und Quicksort sind dabei jeweils ausgehend von einem leeren Eclipse-Projekt live im Video zu entwickeln**

![Bild 2 Katharina](https://user-images.githubusercontent.com/72968168/124029586-97af6000-d9f5-11eb-9354-bc527b454ef3.jpg)

In diesem Video bin ich zunächst auf die Funktionsweise der zwei Sortieralgorithmen Bubblesort und Quicksort anhand einer bildlichen Darstellung eingegangen. 
Im weiteren Verlauf habe ich beide in Eclipse programmiert und nebenbei die Funktionsweise erklärt.
Um das ganze besser nachvollziebar zu machen verwendete ich unsortierte Listen und wendete beide
Algorithmen darauf an.


**3. Eingabe, Ausgabe, Ströme und Dateien**

![Bild 3 Katharina](https://user-images.githubusercontent.com/72968168/124029593-9a11ba00-d9f5-11eb-9737-1e8253db1e02.jpg)

Im dritten Video lag mein Schwerpunkt auf der Speicherung im CSV und Serialisierten Format. Dabei bin ich zunächst auf die Grobe Funktionsweise der Input und Output Streams eingegangen.
Im zweiten Schritt habe ich dann jeweils eine Klasse zur Speicherung und Ladung für Dateien im CSV- und Serialisiertem-Format implementiert. Über dies konnte man den gesammten Stand eines Projektes Speichern und später wieder im gleichen Zustand laden.


**4. Datenstrukturen: Binärbaum, Tree, Trie**

![Bild 4 Katharina](https://user-images.githubusercontent.com/72968168/124029611-9d0caa80-d9f5-11eb-91aa-91f74099d4ac.jpg)

Im letzen Video Block bekam ich das Thema der Trees und Tries. 
Auch hier bin ich zunächst auf die Funktionsweise und Datenstruktur beider eingegangen, um dann im Nachgang einen Trie zu programmieren.
Auch habe ich diesen anhand eines groben Beispiels angewendet, wodurch das ganze besser verständlich gemacht werden sollte.



**Samed Mollamehmetoglu**

**1. Wiederholung: Methoden, Object, Override in Java**


![Bild 1 Samed](https://user-images.githubusercontent.com/72968168/124029632-a1d15e80-d9f5-11eb-9afb-31ee29061e8c.jpg)

In meinem ersten Video ging es, darum Methoden der Klasse Object korrekt zu überschreiben. 
Die clone(), equals(), hashCode() -Methode waren Hauptbestandteile dieses Videos.


**2. Teamarbeit und Testen: Kommentare, JavaDOC, guter Code, Testen, JUnit**

![Bild 2 Samed](https://user-images.githubusercontent.com/72968168/124029640-a4cc4f00-d9f5-11eb-81dd-f316d58fd056.jpg)

Im zweiten Video wurden die JavaDocs und hauptsächlich das Testen mittels JUnit-Tests behandelt. 
Und zwar welche Möglichkeiten es zum Kommentieren, als auch zum Testen gibt.


**3. Swing-GUI: Grundlagen, AWT, Komponenten, Container und Layout-Manager**

![Bild 3 Samed](https://user-images.githubusercontent.com/72968168/124029651-a85fd600-d9f5-11eb-92fe-d6507093f949.jpg)

Im dritten Video war es Zeit für eine Veränderung. In diesem Video wurde alles rund um die GUI behandelt.


**4. Datenstrukturen und Collections: Container, Collection, Generics**

![Bild 4 Samed](https://user-images.githubusercontent.com/72968168/124029665-ab5ac680-d9f5-11eb-85e4-d344dd0067cd.jpg)

Im vierten Video ging es um die vordefinierten Containerklassen. Insbesondere wurde das Interface Collection behandelt, das uns Listen und Sets zu Verfügung stellt.


**Dieses ganze Projekt hat uns viel Zeit und Nerven gekostet, dennoch sind wir sehr stolz auf unsere Leistung**

**Team PR2-B2**

---

[zurück zur Hauptseite...](https://informatik-mannheim.github.io/iExpo-Sommer-2021/)
