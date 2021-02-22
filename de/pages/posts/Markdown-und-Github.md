---
title: "Markdown und Github"
date: 2021-02-19

tags:
  - "Theorie"
  - "Labor"


categories:
  - "BET"
  - "WINF"

# menu: main
#typora-root-url: ../../static/
---

### Überblick

Übung zur Stärkung des Grundverständnisses und zur praktischen Anwendung von

- Markdown samt einem Editor (Typora)
- Git (genauer Github)
- Pandoc (Optional)

zur Nutzung für die Erstellung technischer Dokumentationen.



### Bedingungen, Vorbereitung

#### Links zum Softwaredownload

[Github Desktop](https://desktop.github.com)

[Git](https://git-scm.com/downloads)

[Typora Markdown Editor](https://typora.io#windows)

[Pandoc](https://pandoc.org/installing)

#### Übung Markdown

<!-- Erklärung warum Markdown, Vorteile, Nachteile, Unterschied zu html Beispiele für Markdown (Wikimedia, CMS Systeme, Wordpress, viele Bloggingsysteme, Technische Dokus, Latex (Uni), usw. -->

<!-- Markdowneditor im Internet zeigen (z.B. ) - dann mit Notepad einen kleinen Text erfassen und in einen Markdown Editor laden , dann Pandoc grundsätzlich erklären -->



<!-- Editor zeigen 
- Notepad
- https://dillinger.io oder besser https://stackedit.io/
- Typora 




Pandoc zeigen

- Bsp Notepad export zu PDF und     Word
- Convert Word zu Markdown

pandoc myTexFile.tex -f latex -t html -s -o myHtmlFile.html--bibliography myTexBiblio.bib

The options:
- -f specifies the source     format, LaTeX
- -t specifies the target     format (HTML)
- -s tells pandoc to produce a     'standalone' HTML file
- -o specifies the output     filename
- --bibliography gives pandoc     the .bib file for the citations in myTexFile.tex
Aus <https://www.danwjoyce.com/data-blog/2018/2/20/latex-to-html-via-pandoc>

Flowchart in Markdown
```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
```
-->
<!--
```Sequenzdiagramm
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob->Alice: I am good thanks!
```
-->
<!--
Internal Links in Markdown
Anker setzen
<a name="flowchart"></a> Flowchart
Absprungpunkt:
<a href="#flowchart">Link to Flowchart</a>
Oder
[link](#flowchart)

-->

- Installieren Sie einen Markdown Editior (z.B. Typora)

- Erstellen Sie mit Markdown ein einfaches Übungsdokument mit mind. folgenden Inhalten

  - Normalen Text
  - Text mit einem Absatz
  - Fett gedruckten/angezeigten Text
  - Überschriften (in 3 verschiedenen Größen)
  - Aufzählungen
  - horizontale Linie
  - einen Link zu www.litec.ac.at
  - ein Bild (irgend eine Grafik)
  - Text als "Zitat"
- Übungstext als PDF ausgeben

#### Theorie Git - Github

Git ist ein Versionsverwaltungssystem (VCS - Version Control System). Eine Versionsverwaltung ist ein System, das zur Erfassung von Änderungen an Dokumenten oder Dateien verwendet wird. 

- Alle Versionen werden in einem Archiv mit Zeitstempel und Benutzerkennung gesichert und können später wiederhergestellt werden. 
- Versionsverwaltungssysteme werden typischerweise in der Softwareentwicklung eingesetzt, um Quelltexte zu verwalten.
- Versionsverwaltung kommt auch bei Büroanwendungen, Content-Management-Systemen, modernen CAD Systemen, etc. zum Einsatz.

Git ist ein verteiltes Versionsverwaltungssystem, das 2005 von Linux-Schöpfer Linus Thorvalds entwickelt und unter der freien GNU-GPLv2-Lizenz veröffentlicht wurde. Die Besonderheit des Tools besteht darin, dass zwar ein **zentrales Repository** für jedes Projekt existiert, alle beteiligten Nutzer sich aber eine **lokale Arbeitskopie** dieses Verzeichnisses auf das eigene Arbeitsgerät herunterladen. Jede dieser Kopien stellt ein vollständiges Backup des Repositorys dar, weshalb eine durchgehende Netzwerkverbindung für den grundlegenden Arbeitsprozess nicht erforderlich ist. Zudem dienen die Kopien als Absicherung, falls das Haupt-Verzeichnis ausfallen sollte oder beschädigt ist. Vorgenommene **Änderungen** können jederzeit **mit allen anderen Projektteilnehmern ausgetauscht** und – sofern relevant – in das Repository aufgenommen werden.

##### Funktionsweise

<img src="assets/Markdown-und-Github.assets/image-20210220065855983.png" alt="image-20210220065855983" style="zoom:80%;" />

<!-- 
> Was ist "Versionsverwaltung", und warum sollten Sie sich dafür interessieren? Versionsverwaltung ist ein System, welches die Änderungen an einer oder einer Reihe von Dateien über die Zeit hinweg protokolliert, sodass man später auf eine bestimmte Version zurückgreifen kann. Tatsächlich kann in der Praxis nahezu jede Art von Datei per Versionsverwaltung nachverfolgt werden.

> Lokale Versionsverwaltung
>
> Viele Menschen betreiben Versionsverwaltung, indem sie einfach all ihre Dateien in ein separates Verzeichnis kopieren (die Schlaueren darunter verwenden ein Verzeichnis mit Zeitstempel im Namen). Diese Vorgehensweise ist sehr weit verbreitet und wird gern verwendet, weil sie so einfach ist. Aber sie ist eben auch unglaublich fehleranfällig. Man arbeitet sehr leicht im falschen Verzeichnis, bearbeitet damit die falschen Dateien oder überschreibt Dateien, die man eigentlich nicht überschreiben wollte.
>
> Aus diesem Grund, haben Programmierer bereits vor langer Zeit, lokale Versionsverwaltungssysteme entwickelt, die alle Änderungen an allen relevanten Dateien in einer Datenbank verwalten.
>
> Zentrale Versionsverwaltung
>
> Ein weiteres großes Problem, mit dem sich viele Leute dann konfrontiert sahen, bestand in der Zusammenarbeit mit anderen Entwicklern auf anderen Systemen. Um dieses Problem zu lösen, wurden zentralisierte Versionsverwaltungssysteme entwickelt (engl. Centralized Version Control System, CVCS). Diese Systeme, wozu beispielsweise CVS, Subversion und Perforce gehören, basieren auf einem zentralen Server, der alle versionierten Dateien verwaltet. Die Clients können die Dateien von diesem zentralen Ort abholen und auf ihren PC übertragen. Den Vorgang des Abholens nennt man Auschecken (engl. to check out). Diese Art von System war über viele Jahre hinweg der Standard für Versionsverwaltungssysteme.
>
> Dieser Ansatz hat viele Vorteile, besonders gegenüber lokalen Versionsverwaltungssystemen. Zum Beispiel weiß jeder mehr oder weniger genau darüber Bescheid, was andere, an einem Projekt Beteiligte gerade tun. Administratoren haben die Möglichkeit, detailliert festzulegen, wer was tun kann. Und es ist sehr viel einfacher, ein CVCS zu administrieren als lokale Datenbanken auf jedem einzelnen Anwenderrechner zu verwalten.
>
> Allerdings hat dieser Aufbau auch einige erhebliche Nachteile. Der offensichtlichste Nachteil, ist das Risiko eines Systemausfalls, bei Ausfall einer einzelnen Komponente, nämlich dann wenn der zentralisierte Server ausfällt. Wenn dieser Server nur für eine Stunde nicht verfügbar ist, dann kann in dieser einen Stunde niemand in irgendeiner Form mit anderen zusammenarbeiten oder Dateien, an denen gerade gearbeitet wird, versioniert abspeichern. Wenn die auf dem zentralen Server eingesetzte Festplatte beschädigt wird und keine Sicherheitskopien erstellt wurden, dann sind all diese Daten unwiederbringlich verloren – die komplette Historie des Projektes, abgesehen natürlich von dem jeweiligen Zustand, den Mitarbeiter gerade zufällig auf ihrem Rechner noch vorliegen haben. Lokale Versionskontrollsysteme haben natürlich dasselbe Problem: Wenn man die Historie eines Projektes an einer einzigen, zentralen Stelle verwaltet, riskiert man, sie vollständig zu verlieren, wenn irgendetwas an dieser zentralen Stelle ernsthaft schief läuft.
>
> Verteilte Versionsverwaltung
>
> Und an dieser Stelle kommen verteilte Versionsverwaltungssysteme (engl. Distributed Version Control System, DVCS) ins Spiel. In einem DVCS (wie z.B. Git, Mercurial, Bazaar oder Darcs) erhalten Anwender nicht einfach nur den jeweils letzten Zustand des Projektes von einem Server: Sie erhalten stattdessen eine vollständige Kopie des Repositorys. Auf diese Weise kann, wenn ein Server beschädigt wird, jedes beliebige Repository von jedem beliebigen Anwenderrechner zurückkopiert werden und der Server so wiederhergestellt werden. Jede Kopie, ein sogenannter Klon (engl. clone), ist ein vollständiges Backup der gesamten Projektdaten.

-->
<br><br>
Delta Sync versus Snapshot Sync
<br>



<img src="assets/Markdown-und-Github.assets/image-20210220073945857.png" alt="image-20210220073945857" style="zoom:67%;" />

<!--
> Der Hauptunterschied zwischen Git und anderen Versionsverwaltungssystemen (insbesondere auch Subversion und vergleichbare Systeme) besteht in der Art und Weise wie Git die Daten betrachtet. Die meisten anderen Systeme speichern Information, als eine fortlaufende Liste von Änderungen an Dateien (es werden die Unterschiede gesammelt und gespeichert). Diese Systeme (CVS, Subversion, Perforce, Bazaar usw.) betrachten die Informationen, die sie verwalten, als eine Menge von Dateien und die Änderungen, die über die Zeit hinweg an einzelnen Dateien vorgenommen werden.
>
> Git arbeitet nicht auf diese Art und Weise. Stattdessen betrachtet Git seine Daten eher als eine Reihe von Snapshots eines Mini-Dateisystems. Jedes Mal, wenn Sie committen, das heißt den gegenwärtigen Status Ihres Projekts als eine Version in Git speichern, sichert Git den Zustand sämtlicher Dateien in diesem Moment und macht sozusagen ein Schnappschuss (engl. Snapshot) von all Ihren Daten. Zusätzlich speichert Git eine Referenz auf diesen Snapshot. Um dies möglichst effizient und schnell tun zu können, kopiert Git unveränderte Dateien nicht, sondern legt lediglich eine Verknüpfung zu der vorherigen Version der Datei an. 

-->

##### DVCS am Beispiel Git

Git definiert drei Hauptzustände, in denen sich eine Datei befinden kann: 

- Committet (engl. committed), 
- geändert (engl. modified) und 
- für Commit vorgemerkt (engl. staged). 

Committet bedeutet, dass die Daten sicher in der lokalen Datenbank gespeichert sind. Geändert bedeutet, dass eine Datei geändert, aber noch nicht in die lokale Datenbank eingecheckt wurde. Für Commit vorgemerkt bedeutet, dass eine geänderte Datei in ihrem gegenwärtigen Zustand für den nächsten Commit vorgemerkt ist.



<img src="assets/Markdown-und-Github.assets/image-20210220074400879.png" alt="image-20210220074400879" style="zoom:50%;" />

Das Git Verzeichnis ist der Ort, an dem Git Metadaten und die lokale Datenbank für ein Projekt sichert. Dies ist der wichtigste Teil von Git, und dieser Teil wird kopiert, wenn man ein Repository von einem anderen Rechner klont.

Das Arbeitsverzeichnis ist ein einzelnes Abbild einer spezifischen Version des Projektes. Die dort enthaltenen Dateien werden aus der komprimierten Datenbank geholt und auf der Festplatte in einer Form gespeichert, sodass man sie nutzen oder bearbeiten kann.

Die Staging Area ist einfach eine Datei, normalerweise befindet sich diese im Git Verzeichnis, in der vorgemerkt wird, welche Änderungen der nächste Commit umfassen soll. Manchmal wird dieser Ort auch als “Index” bezeichnet, aber der Begriff Staging-Area ist der gängigere.

<!--

> Git stellt Integrität sicher
>
> Von allen zu speichernden Daten berechnet Git Prüfsummen (engl. checksum) und speichert diese als Referenz zusammen mit den Daten ab. Das macht es unmöglich, dass sich Inhalte von Dateien oder Verzeichnissen ändern, ohne dass Git das mitbekommt. Git basiert auf dieser Funktionalität und sie ist ein integraler Teil der Git Philosophie. Man kann Informationen deshalb z.B. nicht während der Übermittlung verlieren oder unwissentlich beschädigte Dateien verwenden, ohne dass Git in der Lage wäre, dies festzustellen.
>
> Der Mechanismus, den Git verwendet, um diese Prüfsummen zu erstellen, heißt SHA-1 Hash. Eine solche Prüfsumme ist eine 40 Zeichen lange Zeichenkette, die aus hexadezimalen Zeichen (0-9 und a-f) besteht und wird von Git aus den Inhalten einer Datei oder Verzeichnisstruktur berechnet. Ein SHA-1 Hash sieht wie folgt aus:
>
> 24b9da6552252987aa493b52f8696cd6d3b00373
>
> Dieses Hashes begegnen einem überall bei der Arbeit, weil sie so ausgiebig von Git genutzt werden. Git speichert sogar alle Informationen in der Datenbank auf Basis dieser Hashes. Statt eine Datei über den Dateinamen zu referenzieren, verwendet Git den Hash dafür.
>
> Die drei Zustände
>
> Jetzt heißt es aufgepasst. Es folgt die wichtigste Information, die man sich merken muss, wenn man Git erlernen und dabei Fallstricke vermeiden will. Git definiert drei Hauptzustände, in denen sich eine Datei befinden kann: Committet (engl. committed), geändert (engl. modified) und für Commit vorgemerkt (engl. staged). Committet bedeutet, dass die Daten sicher in der lokalen Datenbank gespeichert sind. Geändert bedeutet, dass eine Datei geändert, aber noch nicht in die lokale Datenbank eingecheckt wurde. Für Commit vorgemerkt bedeutet, dass eine geänderte Datei in ihrem gegenwärtigen Zustand für den nächsten Commit vorgemerkt ist.
>
> <<<<<<< HEAD Das führt uns zu den drei Hauptbereichen eines Git Projektes: das Git Verzeichnis, das Arbeitsverzeichnis und die sogenannte Staging-Area.
>
> Das Git Verzeichnis ist der Ort, an dem Git Metadaten und die lokale Datenbank für ein Projekt sichert. Dies ist der wichtigste Teil von Git, und dieser Teil wird kopiert, wenn man ein Repository von einem anderen Rechner klont.
>
> <<<<<<< HEAD Das Arbeitsverzeichnis ist ein einzelnes Abbild einer spezifischen Version des Projektes. Die dort enthaltenen Dateien werden aus der komprimierten Datenbank geholt und auf der Festplatte in einer Form gespeichert, sodass man sie nutzen oder bearbeiten kann.
>
> Die Staging Area ist einfach eine Datei, normalerweise befindet sich diese im Git Verzeichnis, in der vorgemerkt wird, welche Änderungen der nächste Commit umfassen soll. Manchmal wird dieser Ort auch als “Index” bezeichnet, aber der Begriff Staging-Area ist der gängigere.
>
> Die grundlegenden Arbeitsschritte beim Einchecken sind in etwa folgende: 
>
> Man ändert die zu bearbeitenden Dateien im Arbeitsverzeichnis 2. Man merkt die Dateien für einen Commit vor, fügt also einen Schnappschuss der Dateien der Staging-Area hinzu 3. Man führt einen Commit aus, wodurch der in der Staging-Area vorgemerkte Schnappschuss dauerhaft im Git Verzeichnis gespeichert wird
>
> Wenn eine bestimmte Version einer Datei im Git Verzeichnis liegt, gilt sie als committet, oder anders ausgedrückt, sie gilt als eingecheckt (engl. committed). Wenn sie geändert und in die Staging-Area hinzugefügt wurde, gilt sie als für den Commit vorgemerkt (engl. staged). Und wenn sie geändert, aber noch nicht zur Staging-Area hinzugefügt wurde, gilt sie als geändert (engl. modified). Im Kapitel [[_git_basics_chapter\]](https://git-scm.com/book/de/v2/ch00/_git_basics_chapter) werden diese drei Zustände noch näher erläutert und wie man diese sinnvoll einsetzen kann oder alternativ, wie man den Zwischenschritt der Staging-Area überspringen kann.

-->
Git - Github

<img src="assets/Markdown-und-Github.assets/image-20210220075027099.png" alt="image-20210220075027099" style="zoom:50%;" />
<br><br>

<!--

> Nur Tafel
>
> 1) nur your Comuter zeichnen:
>
> Github Desktop zeigen,
>
> Lokal neues Repository anlegen
>
> Textdatei und andere Datein in Arbeitsverzeichnis kopieren
>
> History zeigen
>
> Committen
>
> Datei lokal zeigen
>
> Revert commit zeigen (alter stand wieder da)

-->
Git Begriffe (branch und merge)

<img src="assets/Markdown-und-Github.assets/image-20210220075219471.png" alt="image-20210220075219471" style="zoom:50%;" />
<br><br>


<!--

>Auf Tafel machen
>
>Unterchied branch – fork (fork ist ein clone, der nicht wieder gemerged werden kann)
>
>Wenn mehrere Leute an einer Sache arbeiten oder man etwas probieren möchte, bieten sich branches an.
>
>Lokal: neuen branch machen – textdatei ändern
>
>Branch vergleichen
>
>Branch mergen

-->
Git und Zusammenarbeit

<img src="assets/Markdown-und-Github.assets/image-20210220075401967.png" alt="image-20210220075401967" style="zoom:50%;" />
<br><br>


<!--

> Nur Tafel
>
> 1) gesamte skizze zeichnen
>
> Anmelden bei github ([omue@litec.ac.at/Litec123](mailto:omue@litec.ac.at/Litec123))
>
> Repository pushen
>
> Anonym Github das gepushte Repository zeigen!

-->

#### Übung Git - Github

<!-- Git erklären, Github erklären und Zugang im Web zeigen; -->

<!-- Erklären, was wir mit der Übung GIT erreichen wollen -->

- Github Desktop installieren
<!-- prüfen ob damit auch Git lokal installiert wird. Wenn nein, Git downloaden und installieren. Jedenfalls erklären, dass GIT auch ohne Desktop jederzeit vollumfänglich funktioniert. -->
- Repository anlegen und Übungen mit Repository
  - Übungsdatei (x.md) in Git verwaltetes Verzeichnis kopieren
  - Commits
  - Änderungen an x.md
  - mehrere Dateien aufnehmen
  - History nachvollziehen
  - Branch anlegen und üben
  - Merge anlegen und üben
- Repository löschen

```

```