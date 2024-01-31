# DIS 18974, OpenChain security assurance specification

### Note 0: this is the German language draft. It is pending an update to formatting to match the English original located here: [https://github.com/OpenChain-Project/Security-Assurance-Specification/tree/main/Security-Assurance-Specification/DIS-18974/en]
THE TRANSLATIONS FOR THE FIRST VERSION OF DIS-18974 DO NOT INCLUDE THE EDITORIAL ADJUSTMENTS FOUND IN "DIS-18974 POST JTC-1 PAS PROCESS EDITS.md", THE FINAL VERSION OF THE PAS SUBMISSION.

### Note 1: this document is designed to closely follow the formatting being used by JTC-1 for the JTC-1 PAS Transposition Process around the OpenChain Security Assurance Specification 1.1. 

### Note 2: the outcome of the JTC-1 PAS Transposition Process will be a new ISO/IEC standard.

### Note 3: the ISO/IEC standard will be 'ISO/IEC 18974, OpenChain security assurance specification' after the completion of a successful ISO/IEC ballot.

### Note 4: this document has some small differences in formatting with the current DIS 18974 document, but it perfectly matches the proposed requirements.

### Note 5: this document will be updated to improve the formatting alignment with the DIS 18974 over time.

### Note 6: after the ISO/IEC ballot approves DIS 18974, there will be a new document based on this document for ISO/IEC 18974.

## Einleitung
Das OpenChain Projekt strebt eine Lieferkette an, in der Open Source mit vertrauenswürdigen und konsistenten Compliance Informationen ausgeliefert wird. Als Teil dieser Mission pflegen wir OpenChain ISO/IEC 5230:2020, den internationalen Standard für die Einhaltung von Open Source Lizenzen. Ein logischer nächster Schritt zur Unterstützung dieses Bestrebens war die Entwicklung eines Leitfadens zur Identifizierung und Darstellung von grundlegenden Anforderungen, die jedes Security Assurance Programm in Bezug auf die Verwendung von Open Source Software erfüllen sollte.

OpenChain ISO/IEC 5230:2020 ist eine Spezifikation für das Prozessmanagement, die eingehende, interne und ausgehende Verfahren identifiziert, an denen ein Prozess, eine Richtlinie oder eine Schulung existieren sollte. Die Identifizierung und das laufende Tracking der in Nutzung befindlichen und deployten Software ist ein fester Bestandteil dieser Spezifikation, so dass unser Ansatz auch für Sicherheits- oder Exportkontrollen nützlich sein kann.

Die OpenChain Projektgemeinschaft hat festgestellt, dass OpenChain ISO/IEC 5230:2020 im Sicherheitsbereich angewandt wird, und hat daher beschlossen, diese Sicherheitsspezifikation zu entwickeln, um auf die Nachfrage im Markt angemessen zu reagieren. Diese Spezifikation soll die wichtigsten Anforderungen an ein qualitativ hochwertiges Sicherheitsprogramm im Zusammenhang mit der Verwendung von Open Source Software identifizieren und beschreiben. Sie konzentriert sich auf ausgewählte Teilbereiche: die Überprüfung von Open Source Software gegen öffentlich bekannte Sicherheitslücken wie CVEs, GitHub/GitLab-Schwachstellenberichte und vergleichbare Risiken.

Die OpenChain Security Assurance Specification konzentriert sich auf die "Was"- und "Warum"-Aspekte eines qualitativ hochwertigen Security Assurance Programms, anstatt sich mit dem "Wie" und "Wann" zu beschäftigen. Dies ist eine bewusste Entscheidung, um Organisationen jeder Größe und jeder Branche die Flexibilität zu geben, diese Referenzspezifikation zu verwenden. Dieser Ansatz und die identifizierten Prozesstypen basieren auf mehr als einem halben Jahrzehnt praktischer, globaler Erfahrungen in der Erstellung und Verwaltung solcher Programme. Das Ergebnis ist, dass ein Unternehmen ein Programm erstellen kann, das genau auf die Anforderungen seiner Lieferkette zugeschnitten ist, und zwar für ein einzelnes Produkt oder eine komplette Legal Entity, und diese Lösung schnell und effektiv auf den Markt bringen kann.

Diese Spezifikation basiert auf dem Security Assurance Reference Guide 2.0 (Release Candidate 1), der am 2022-03-28 veröffentlicht wurde. Dieses Referenzdokument durchlief einen Genehmigungsprozess im Rahmen unserer üblichen Abstimmungspraxis, um im Rahmen dieser Sicherheitsspezifikation veröffentlicht zu werden. Der Umfang dieser Referenzspezifikation kann im Laufe der Zeit auf der Grundlage des Feedbacks aus der Community erweitert werden.

In der Einleitung zu dieser Spezifikation wird zunächst ihr Zweck beschrieben. In Abschnitt 2 werden die im Dokument verwendeten Schlüsselbegriffe definiert. In Abschnitt 3 werden die Anforderungen definiert, die ein Programm erfüllen muss, um ein Mindestmaß an Sicherheit zu erreichen. Jede Anforderung besteht aus einem oder mehreren Verifikationsmaterialien (d.h. Aufzeichnungen), die zur Erfüllung der Anforderung vorliegen müssen. Die Verifikationsunterlagen müssen nicht veröffentlicht werden, jedoch kann sich eine Organisation dafür entscheiden, sie anderen zur Verfügung zu stellen, bspw. im Rahmen einer Geheimhaltungsvereinbarung (Non-Disclosure Agreement, NDA).

Diese Spezifikation ist unter der Creative Commons Attribution License 4.0 (CC-BY-4.0) lizenziert. Da es sich um eine Spezifikation handelt, ist eine Bearbeitung außerhalb des formalen Bearbeitungsprozesses nicht vorgesehen. Sie können sich gerne an der Bearbeitung dieses Dokuments über das OpenChain Projekt beteiligen. Hier erfahren Sie, wie Sie sich an unserer Arbeit beteiligen können:

[https://www.openchainproject.org/community](https://www.openchainproject.org/community)

# OpenChain Referenzspezifikation für die Gewährleistung der Sicherheit
## 1: Umfang
Dieses Dokument spezifiziert die Hauptanforderungen an ein hochwertiges Open Source Software Security Assurance Programm, das Vertrauen zwischen Organisationen schafft, die untereinander Softwarelösungen mit Open Source Bestandteilen austauschen.

## 2: Begriffe, Definitionen und Beispiele
Für die Zwecke dieses Dokuments gelten die folgenden Begriffe und Definitionen.

### 2.1 - Komponentendatensätze
Ein Komponentendatensatz sollte den Namen des Anbieters, den Komponentennamen, die Version der Komponente, andere eindeutige Identifikatoren, die Abhängigkeitsbeziehung, den Autor oder die Autorin der SBOM-Daten sowie den Zeitstempel beinhalten (gemäß den Mindestelementen der NTIA für SBoM).

### 2.2 - Kundenvereinbarung
Es besteht Einvernehmen darüber, dass die Prozesse, die zur Identifikation, Verfolgen oder Behebung von Sicherheitsproblemen eingesetzt werden, von den betreffenden Kunden oder ggf. Benutzerorganisationen als ausreichend und korrekt angesehen werden.


### 2.3 - CVE
Common Vulnerabilities and Exposures (CVE) ist eine öffentlich zugängliche Datenbank mit offengelegten Sicherheitsproblemen und Schwachstellen in Computersoftware. Wird auf eine CVE Bezug genommen, ist damit eine Sicherheitslücke gemeint, der in der Datenbank eine CVE-ID-Nummer zugewiesen wurde. Die CVE Datenbank wird vom US Department of Homeland Security (DHS) und der Cybersecurity and Infrastructure Security Agency (CISA) gesponsert.

### 2.4 - Dokumentierte Beweise
Hierbei handelt es sich um explizit gespeicherte Informationen, die Informationen im Zusammenhang mit den in dieser Spezifikation genannten Aktivitäten und Maßnahmen beschreiben, erklären oder aufzeichnen.

### 2.5 - Bekannte Sicherheitslücken
Sicherheitslücken, die zuvor in Open Source Softwarekomponenten entdeckt wurden und öffentlich zugänglich sind. Dazu gehören alle veröffentlichten Schwachstellen, einschließlich, aber nicht beschränkt auf CVEs, GitHub/GitLab-Schwachstellenwarnungen, Warnungen von Paketmanagern und so weiter.

### 2.6 - Neu entdeckte Sicherheitslücken
Neu entdeckte Sicherheitslücken in Open Source Softwarekomponenten, die öffentlich zugänglich sind. Dazu gehören alle veröffentlichten Sicherheitslücken, einschließlich, aber nicht beschränkt auf CVEs, GitHub/GitLab-Warnungen zu Sicherheitslücken, Warnungen von Paketmanagern und so weiter.

### 2.7 - Open Source Software
Software, die einer oder mehreren Lizenzen unterliegt, die der von der Open Source Software Initiative veröffentlichten Open Source Software Definition (siehe www.opensource.org/osd) oder der von der Free Software Foundation veröffentlichten Free Software Definition (siehe www.gnu.org/philosophy/free-sw.html) entsprechen.

### 2.8 - Programm
Die Gesamtheit der Richtlinien, Prozesse und Mitarbeitenden, die die Aktivitäten einer Organisation zur Gewährleistung der Sicherheit umfassen.

### 2.9 - Programmteilnehmende
Jeder Mitarbeitende oder Auftragnehmende einer Organisation, die/der bereitgestellte Software definiert, zu ihr beiträgt oder die Verantwortung für ihre Erstellung trägt. Anmerkung: Je nach Unternehmen kann dies Softwareentwickelnde, Release-Ingenieur:innen, Qualitätsingenieur:innen, Produktmarketing, Produktmanagement und Beschaffung umfassen (ist aber nicht darauf beschränkt).

### 2.10 - Sicherheitsgewährleistung
Die Gewissheit, dass ein System die Anforderungen an bewährte Sicherheitspraktiken erfüllt und gegen bekannte Schwachstellen widerstandsfähig ist.

### 2.11 - Sicherheitstests
Ein Verfahren zur Analyse von Software (oder anderen Komponenten), das es ermöglicht, ihre aktuelle und zukünftige Handhabung im Zusammenhang mit bekannten Schwachstellen zu verstehen.

### 2.12 - Software-Bill of Materials (SBOM)
Informationen in einem strukturierten Format wie SPDX ISO/IEC 5962:2021, die den Austausch von Informationen über ein Softwarepaket ermöglichen, die sinnvollerweise Name, Version, Herkunft, Lizenz, Copyright und bekannte Schwachstellen in einer für Dritte nützlichen Weise enthalten können.

### 2.13 - Mitgelieferte Software
Software, die eine Organisation an Dritte (z. B. andere Organisationen oder Einzelpersonen) weitergibt oder zur Verfügung stellt.

### 2.14 - Verifikationsmaterialien
Materialien, die nachweisen, dass eine bestimmte Anforderung der Spezifikation erfüllt ist.

# 3 - Anforderungen
## 3.1 - Programmgrundlagen
### 3.1.1 - Richtlinie
Es wird eine schriftliche Richtlinie erstellt, die die Gewährleistung der Sicherheit von Open Source Software in Bezug auf bereitgestellte Software regelt. Die Richtlinie wird intern kommuniziert. Die Richtlinie und ihre Kommunikationsmethode werden einem Überprüfungsprozess unterzogen, um sicherzustellen, dass sie aktuell und relevant sind.

#### Überprüfungsmaterial(ien):

- 3.1.1.1: Eine dokumentierte Politik zur Gewährleistung der Sicherheit von Open Source Software;
- 3.1.1.2: Ein dokumentiertes Verfahren, um die Programmteilnehmenden auf die Sicherheitsgewährleistungspolitik aufmerksam zu machen.
#### Begründung:
Damit soll sichergestellt werden, dass ein Verfahren existiert, um eine Open Source Software-Sicherheitsrichtlinie zu erstellen, aufzuzeichnen und den Programmteilnehmenden zu vermitteln, dass eine solche Richtlinie existiert. Obwohl hier keine Vorgaben gemacht werden, was in der Richtlinie enthalten sein sollte, können in anderen Abschnitten zusätzliche Anforderungen gestellt werden.

### 3.1.2 - Kompetenz
Die Organisation muss:

- Die Rollen und Verantwortlichkeiten identifizieren, die sich auf die Leistung und Wirksamkeit des Programms auswirken;
- Die erforderlichen Kompetenzen der Programmteilnehmenden bestimmen, die die jeweilige Rolle erfüllen;
- Sicherstellen, dass die Programmteilnehmenden über eine angemessene Ausbildung, Schulung und/oder Erfahrung verfügen;
- Gegebenenfalls sicherstellen, dass die Programmteilnehmenden Maßnahmen ergreifen, um die erforderlichen Kompetenzen zu erwerben;
- Geeignete dokumentierte Informationen zum Nachweis der Kompetenz sowie der aktuellen Teilnehmenden des Programms nachhalten.
#### Nachprüfungsmaterial(e):
- 3.1.2.1: Eine dokumentierte Liste der Rollen mit den entsprechenden Verantwortlichkeiten für die verschiedenen Programmteilnehmenden;
- 3.1.2.2: Ein Dokument, in dem die Kompetenzen für jede Rolle aufgeführt sind;
- 3.1.2.3: Liste der Teilnehmenden und ihrer Rollen;
- 3.1.2.4: Dokumentierter Nachweis der bewerteten Kompetenz für jeden Programmteilnehmenden;
- 3.1.2.5: Dokumentierte Nachweise über regelmäßige Überprüfungen und Änderungen des Prozesses;
- 3.1.2.6: Dokumentierter Nachweis, dass diese Prozesse mit unternehmensinternen Best Practices übereinstimmen und wer mit ihrer Durchführung betraut ist.
#### Begründung:
Es soll sichergestellt werden, dass die Programmteilnehmenden über ein ausreichendes Maß an Kompetenz für ihre jeweiligen Aufgaben und Verantwortlichkeiten verfügen.


### 3.1.3 - Sensibilisierung
Die Organisation stellt sicher, dass die Programmteilnehmenden über Folgendes informiert sind:

- Die Richtlinie zur Gewährleistung der Sicherheit von Open Source Software;
- Relevante Programmziele;
- Ihren Beitrag zur Wirksamkeit des Programms;
- Die Auswirkungen der Nichteinhaltung der Anforderungen des Programms.

#### Überprüfungsmaterial(ien):
- 3.1.3.1: Dokumentierter Nachweis der Kenntnisnahme der Programmteilnehmenden, insbesondere der Programmziele, ihres Beitrags innerhalb des Programms und der Auswirkungen einer Nichteinhaltung des Programms.
#### Begründung:
Es soll sichergestellt werden, dass die Programmteilnehmenden ein ausreichendes Bewusstsein für ihre jeweiligen Aufgaben und Verantwortlichkeiten innerhalb des Programms erhalten haben.

### 3.1.4 - Programmumfang
Ein Programm sollte über definierte Leitprinzipien und einen Anwendungsbereich verfügen, die mit der Risikomanagementpolitik der gesamten Organisation übereinstimmen. Es sollte klar definiert sein, ob das Programm für eine Produktlinie, eine Abteilung oder eine gesamte Organisation gilt. Es sollte auch klar sein, dass sich der Geltungsbereich im Laufe der Zeit ändern kann, und es sollten Messgrößen zur Bewertung der fortlaufenden Wirksamkeit verwendet werden.

#### Verifizierungsmaterial(e):
- 3.1.4.1: Eine schriftliche Erklärung, die den Umfang und die Grenzen des Programms klar definiert;
- 3.1.4.2: Eine Reihe von Messgrößen, die das Programm erreichen soll, um sich zu verbessern;
- 3.1.4.3: Dokumentierte Belege für jede Überprüfung, Aktualisierung oder jedes Audit zum Nachweis der kontinuierlichen Verbesserung.
#### Begründung:
Um die Flexibilität zu gewährleisten, ein Programm zu erstellen, das den Bedürfnissen einer Organisation am besten entspricht. Einige Organisationen könnten sich dafür entscheiden, ein Programm für eine bestimmte Produktlinie aufrechtzuerhalten, während andere ein Programm einführen könnten, das die gelieferte Software der gesamten Organisation regelt.

### 3.1.5 - Implementierung von Standardverfahren
Das Programm demonstriert einen soliden und robusten Umgang mit bekannten Schwachstellen und sicherer Softwareentwicklung, indem es die folgenden Verfahren definiert und implementiert:

- Methode zur Identifizierung struktureller und technischer Bedrohungen für die gelieferte Software;
- Methode zur Erkennung bekannter Schwachstellen in der gelieferten Software;
- Methode zur Weiterverfolgung der identifizierten bekannten Schwachstellen;
- Verfahren zur Mitteilung bekannter Schwachstellen an den Kundenstamm, wenn dies erforderlich ist;
- Verfahren zur Analyse der gelieferten Software auf erst kürzlich bekannt gewordene Sicherheitslücken nach der Freigabe der gelieferten Software;
- Verfahren zur kontinuierlichen und wiederholten Sicherheitsprüfung sämtlicher gelieferter Software vor deren Freigabe;
- Methode zur Überprüfung, ob identifizierte Risiken vor der Freigabe der gelieferten Software behoben wurden;
- Verfahren zur Weitergabe von Informationen über erkannte Risiken an Dritte, soweit dies erforderlich ist.

Es muss ein Verfahren für die oben aufgeführten Methoden zur Sicherheitsgewährleistung vorhanden sein.

#### Überprüfungsmaterial(ien):
- 3.1.5.1: Es existiert ein dokumentiertes Verfahren für jede der oben genannten Methoden.
#### Begründung:
Es soll sichergestellt werden, dass geeignete Verfahren zur Erkennung und Nachverfolgung bekannter Schwachstellen in der gelieferten Software vorhanden sind.

## 3.2 - Definierte und unterstützte relevante Aufgaben
### 3.2.1 - Zugriff
Aufrechterhaltung eines Prozesses zur effektiven Beantwortung externer Anfragen zu bekannten Sicherheitslücken. Angebot einer öffentlichen Möglichkeit, mit der sich Dritte über eine bekannte Sicherheitslücke in Bezug auf ein bestimmtes Softwareangebot erkundigen können.

#### Überprüfungsmaterial(ien):
- 3.2.1.1: Öffentliches Angebot einer Möglichkeit, die es Dritten ermöglicht, Anfragen zu bekannten Sicherheitslücken oder neu entdeckten Sicherheitslücken zu stellen (z. B. per E-Mail oder ein Webportal, das von den Programmteilnehmenden regelmäßig auf neue Meldungen geprüft wird);
- 3.2.1.2: Es gibt ein internes dokumentiertes Verfahren für die Beantwortung von Anfragen Dritter zu bekannten oder neu entdeckten Sicherheitslücken.
#### Begründung:
Es soll sichergestellt werden, dass es für Dritte einen angemessenen Weg gibt, sich sicher mit der Organisation bezüglich Anfragen zu Sicherheitslücken in Verbindung zu setzen, und dass die Organisation darauf vorbereitet ist, zu antworten.

### 3.2.2 - Effektive Ressourcenausstattung
Identifizierung und Bereitstellung von Ressourcen für die Programmaufgabe(n):

- Zuweisung von Verantwortlichkeiten, um die erfolgreiche Durchführung der Programmaufgaben zu gewährleisten;
- Die Programmaufgaben sind mit ausreichenden Mitteln ausgestattet;
- Ausreichend Zeit für die Durchführung der Aufgaben wurde zugewiesen;
- Angemessene Finanzmittel wurden zugewiesen;
- Es gibt ein Verfahren zur Überprüfung und Aktualisierung der Richtlinien und der unterstützenden Aufgaben;
- Technisches Fachwissen in Bezug auf bekannte Schwachstellen ist für diejenigen zugänglich, die eine solche Anleitung benötigen.

#### Überprüfungsmaterial(ien):
- 3.2.2.1: Dokument, in dem die Namen der Personen, Gruppen oder Funktionen in der/den Programmrolle(n) aufgeführt sind;
- 3.2.2.2: Die identifizierten Programmrollen wurden ordnungsgemäß besetzt und mit angemessenen Mitteln ausgestattet;
- 3.2.2.3: Identifizierung des verfügbaren Fachwissens zur Behebung der festgestellten bekannten Schwachstellen;
- 3.2.2.4: Ein dokumentiertes Verfahren, das die internen Verantwortlichkeiten für die Sicherheitsgewährleistung zuweist.
#### Begründung:
Es soll sichergestellt werden, dass i) die Programmverantwortlichkeiten wirksam unterstützt und mit Ressourcen ausgestattet werden und ii) die Richtlinien und unterstützenden Prozesse regelmäßig aktualisiert werden, um Änderungen bei den bewährten Verfahren zur Sicherheitssicherung zu berücksichtigen.

## 3.3 - Überprüfung und Genehmigung des Inhalts von Open Source Software
### 3.3.1 - Software-Bill of Materials (SBOM)
Es muss ein Verfahren zur Erstellung und Pflege einer Stückliste vorhanden sein, die jede Open Source Softwarekomponente enthält, aus der sich die gelieferte Software zusammensetzt.

#### Verifizierungsmaterial(e):
- 3.3.1.1: Ein dokumentiertes Verfahren, das sicherstellt, dass die gesamte Open Source Software, die in der gelieferten Software verwendet wird, während des gesamten Lebenszyklus der gelieferten Software kontinuierlich aufgezeichnet wird. Dazu gehört auch ein Archiv aller in der gelieferten Software verwendeten Open Source Software;
- 3.3.1.2: Aufzeichnungen über Open Source Softwarekomponenten für die gelieferte Software, die belegen, dass das dokumentierte Verfahren ordnungsgemäß eingehalten wurde.
#### Begründung:
Es soll sichergestellt werden, dass ein Verfahren zur Erstellung und Verwaltung einer Software-Materialliste existiert, die zur Erstellung der gelieferten Software verwendet wird. Eine Stückliste wird zur Unterstützung der systematischen Überprüfung jeder Komponente benötigt, um festzustellen, ob bekannte Schwachstellen vorhanden sind.

### 3.3.2 - Sicherheitsgewährleistung
- Für jede Open Source Softwarekomponente in der Stückliste für die zu überprüfende Version der gelieferten Software;
- Anwendung einer Methode zur Erkennung bekannter Schwachstellen;
- Zuweisung einer Risiko-/Auswirkungsbewertung zu jeder erkannten bekannten Schwachstelle;
- Festlegung und Dokumentation der erforderlichen Abhilfemaßnahmen für jede erkannte und zugewiesene Schwachstelle, die für den Anwendungsfall der Software geeignet sind, und es wird eine Kundenvereinbarung auf oder über einem zuvor festgelegten Niveau erreicht (d.h. alle Schweregrade über 4,5 ...);
- Ergreifung notwendiger Maßnahmen abhängig von der jeweiligen Risiko-/Auswirkungsbewertung (z. B. Kunden kontaktieren, falls erforderlich, Aktualisierung der Softwarekomponente, keine weiteren Maßnahmen, ...);
- Ergreifung notwendiger Maßnahmen, wenn eine neu entdeckte Schwachstelle in zuvor vertriebener gelieferter Software vorhanden ist, je nach Risiko-/Auswirkungsgrad (z. B. Kontaktaufnahme mit dem Kunden, wenn dies gerechtfertigt ist);
- Fähigkeit, die gelieferte Software nach ihrer Freigabe auf dem Markt zu überwachen und auf bekannte oder neu entdeckte Sicherheitslücken zu reagieren.

#### Überprüfungsmaterial(ien):
- 3.3.2.1: Ein dokumentiertes Verfahren für die Erkennung und Behebung von bekannten Sicherheitslücken für die Open Source Softwarekomponenten der gelieferten Software;
- 3.3.2.2: Für jede Open Source Softwarekomponente wird eine Aufzeichnung über die identifizierten bekannten Sicherheitslücken und die ergriffenen Maßnahmen geführt (auch wenn keine Maßnahmen erforderlich waren).
#### Begründung:
Es soll sichergestellt werden, dass das Programm ausreichend robust ist, um mit den identifizierten bekannten Schwachstellen der Open Source Software, aus der die gelieferte Software besteht, umzugehen. Dass ein Verfahren zur Unterstützung dieser Aktivität existiert und dass das Verfahren befolgt wird.

## 3.4 - Einhaltung der Anforderungen der Leitlinie
### 3.4.1 - Vollständigkeit
Damit ein Programm als konform mit dieser Spezifikation angesehen werden kann, muss die Organisation bestätigen, dass das Programm die in diesem Dokument aufgeführten Anforderungen erfüllt.

#### Überprüfungsmaterial(e):
- 3.4.1.1: Dokumentierte Nachweise, die bestätigen, dass das in §3.1.4 spezifizierte Programm alle Anforderungen dieses Dokuments erfüllt.

#### Begründung:
Wenn eine Organisation erklärt, dass sie über ein konformes Programm verfügt, soll sichergestellt werden, dass das Programm alle Anforderungen dieses Dokuments erfüllt hat. Die bloße Erfüllung einer Teilmenge dieser Anforderungen wird nicht als ausreichend angesehen.

### 3.4.2 - Dauer
Ein Programm, das mit dieser Version der Spezifikation konform ist, hat einen Überprüfungszeitraum wie folgt: 18 Monate nach der ersten Zertifizierung, 24 Monate nach der zweiten Zertifizierung und 36 Monate nach der dritten Zertifizierung. Danach ist alle 36 Monate einer Überprüfung notwendig.

#### Überprüfungsmaterial(ien):
- 3.4.2.1: Ein Dokument, das bestätigt, dass das Programm alle Anforderungen dieser Spezifikation erfüllt, und zwar innerhalb der letzten 18 Monate nach Erhalt der Konformitätsvalidierung.
#### Begründung:
Es ist für ein Programm unerlässlich, die Anforderungen der Spezifikation auf dem neuesten Stand zu halten, wenn eine Organisation ihre Konformität über einen längeren Zeitraum hinweg nachweisen möchte. Diese Anforderung stellt sicher, dass die unterstützenden Prozesse und Kontrollen des Programms nicht an Aktualität verlieren, wenn eine Organisation die Konformität des Programms im Laufe der Zeit weiterhin nachweist.
