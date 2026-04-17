---
titel: "Verwaltungsvorschrift des Ministeriums des Inneren, für Digitalisierung und Kommunen über IT-Standards des Landes (VwV IT-Standards)"
ebene: land
saule: regelungsrahmen
rechtsnatur: verwaltungsvorschrift
land_ars: "08"
land: Baden-Württemberg
quelle: "GABl. 2025, S. 9"
gueltig_ab: 2025-01-01
gueltig_bis: 2031-12-31
url: "https://www.landesrecht-bw.de/bsbw/document/VVBW-VVBW000043017"
url_nachfolger:
stand: "2026-03-27"
status: published
endpoints:
  - amtsschimmel
extensions:
  - Datenschutz & IT-Recht
  - Verwaltungsrecht
---

## Inhaltsverzeichnis

- 1 Ziele, Rechtsgrundlage und Geltungsbereich
- 2 Begriffsbestimmungen
- 3 Übergreifende Architekturvorgaben
- 3.1 Frühzeitige und vollständige Berücksichtigung der rechtlichen Rahmenbedingungen
- 3.2 Verwendung von Standards und einheitlichen Methoden
- 3.3 Informations- und Cybersicherheit
- 3.4 Vorgaben zum Datenschutz
- 3.5 Vorgaben zur Informationsfreiheit
- 3.6 Berücksichtigung von Referenzarchitekturen
- 3.7 Sicherstellung der Benutzungsfreundlichkeit
- 3.8 Sicherstellung der Barrierefreiheit
- 3.9 Vermeidung von Herstellerabhängigkeiten
- 3.10 Gewährleistung der Interoperabilität von Anwendungen und Diensten
- 3.11 Sicherstellung von loser Kopplung / Modularität
- 3.12 Gewährleistung einer nachhaltigen Informationstechnik
- 3.13 Reduzierung der Komplexität auf ein notwendiges Maß
- 3.14 Qualitätssicherung und automatisierte Tests
- 3.15 Verwendung von Standardbibliotheken
- 3.16 Sicherstellung der Wirtschaftlichkeit von Architekturen und korrespondierenden Vorhaben
- 3.17 Vorgehensmodelle zur Umsetzung von Anwendungssystemen
- 3.18 Architekturmanagementprozess
- 3.19 Vorgaben zur Nutzung von Cloud-Diensten
- 3.20 Vorgaben zur Gewährleistung eines sicheren und stabilen Betriebs
- 4 Vorgaben zur Geschäftsarchitektur
- 4.1 Dokumentation von Verwaltungsprozessen
- 4.2 Vorgaben zum Informationsaustausch (fachlich / semantisch)
- 5 Vorgaben zur Anwendungsarchitektur
- 5.1 Verpflichtende Nutzung von Anwendungssystemen
- 5.2 Dokumentation der Anwendungsarchitektur
- 5.3 Dokumentation der anwendungsübergreifenden Schnittstellen und zugehörigen Dienste
- 5.4 Nutzung vorgegebener Entwicklungslinien
- 5.5 Vorgaben zu grafischen Benutzungsschnittstellen
- 5.6 Nutzung von Middleware-Plattformen
- 5.7 Berücksichtigung von Virtualisierung und Automatisierung
- 5.8 Berücksichtigung betriebsrelevanter nicht-funktionaler Anforderungen
- 5.9 Festlegungen zu Austauschformaten (technisch / konkret)
- 5.10 Verwendung des Unicode-Standards
- 5.11 Fachliches Monitoring
- 6 Vorgaben zur Systemarchitektur
- 6.1 Verwendung der Hardware- und Softwarestandards für technische Infrastruktur
- 6.2 Verwendung energieeffizienter und ressourcenschonender Technologien
- 6.3 Vorgaben für das Monitoring
- 6.4 Vorgaben zur Netzwerkarchitektur
- 6.5 Vorgaben zur Nutzung von extern gehosteten Diensten und Plattformen
- 7 Technische Spezifikationen
- 7.1 Festlegungen zur Kopplung von Anwendungssystemen
- 7.2 Grundausstattung des einheitlichen BK-Arbeitsplatzes
- 7.3 Desktop-Web-Browser
- 7.4 Standardisierte Austauschformate
- 7.5 IT-Standards für Geoinformationen, Geo-Daten, Geoanwendungen und -diensten
- 7.6 Hardware- und Softwarestandards für Server und Clients
- 7.7 Netzstandards
- 8 Nutzung vorgegebener Entwicklungslinien
- 9 Standards zum Management von IT-Projekten
- 10 Übergangs- und Schlussvorschriften
- Anlage 1: Technische Spezifikationen und Entwicklungslinien
- 1 Allgemeine Vorgaben zum Technologieeinsatz
- 2 IT-Standards für Geoinformationen, Geo-Daten, Geoanwendungen und -diensten
- 3 Nutzung vorgegebener Entwicklungslinien
- Anlage 2: Architekturmanagement und IT-Projektmanagement
- 1 Architekturmanagementprozess zur Festlegung und Überwachung der Architekturvorgaben
- 2 Standards zum Management von IT-Projekten
- Anlage 3: LAN-Konzeption (zu Nummer 7.7)

### 1 Ziele, Rechtsgrundlage und Geltungsbereich

**1.1** Ziel der vorliegenden Verwaltungsvorschrift ist es, die Entwicklung der IT-Gesamtarchitektur der Landesverwaltung mithilfe allgemeiner Entscheidungshilfen sowie konkreter Vorgaben zu steuern. Architekturrelevante Fragestellungen sollen innerhalb der Landesverwaltung nach einheitlichen Kriterien transparent und nachvollziehbar beantwortet werden. Hierzu ist es notwendig, über Fragen des Technologieeinsatzes hinaus, ressortübergreifend einheitliche Steuerungsmechanismen für die Beauftragung und Umsetzung von IT-Vorhaben festzulegen. Nur so lassen sich vorhabenbezogene Architekturentscheidungen abstimmen sowie deren Einhaltung überwachen.

**1.2** Diese Verwaltungsvorschrift gilt für alle Vorhaben der Landesverwaltung, die eine Neuentwicklung von Anwendungssystemen, ein Redesign bestehender Systeme oder die Beschaffung und Integration neuer IT-Systeme vorsehen. Sie ist bei der Umsetzung von IT-Vorhaben der Landesverwaltung von allen beteiligten Rollen (Projektleitung, Systemarchitekturverantwortliche etc.) verpflichtend anzuwenden. Begründete Ausnahmen bilden bundesrechtliche oder europarechtliche Vorgaben oder Vorgaben im Rahmen einer Kooperation mit Bund, Ländern, Kommunen oder Regionalverbänden. Auf Verfahren, die in länderübergreifenden Verbünden definiert werden, ist diese Verwaltungsvorschrift nicht anwendbar.

**1.3** Darüber hinaus gilt Nr. 3.20 dieser Verwaltungsvorschrift für alle Anwendungssysteme der Landesverwaltung. Dies schließt die bereits in Produktion befindlichen Anwendungssysteme ein.

**1.4** Rechtsgrundlage für die Verwaltungsvorschrift ist § 21 Nummer 1 des E-Government-Gesetzes Baden-Württemberg (EGovG BW) in Verbindung mit § 24 Absatz 2 Variante 2 EGovG BW. Diese Verwaltungsvorschrift gilt mit Ausnahme des Rechnungshofs und der Steuerverwaltung für alle Dienststellen und Einrichtungen der unmittelbaren Landesverwaltung, einschließlich der Gerichte sowie für die rechtlich selbstständigen Einrichtungen nach § 2 Absatz 2 Nummer 4 und 5 BITBWG.

### 2 Begriffsbestimmungen

**2.1** Eine Anwendungssoftware stellt den softwaretechnischen Teil zur Unterstützung einer fachlichen Aufgabe innerhalb eines Anwendungssystems dar. Bei einer Anwendungssoftware handelt es sich um den fachlichen Programmcode und somit um eine Fachanwendung. Zusammen mit der Basissoftware bildet es das Softwaresystem.

**2.2** Ein Anwendungssystem umfasst die software- und hardwaretechnischen Komponenten zur Unterstützung eines bestimmten Aufgabengebiets und setzt sich somit aus einem Softwaresystem und einem Hardwaresystem zusammen. Im Unterschied zum Informationssystem bildet ein Anwendungssystem nicht notwendigerweise die Vollständigkeit der Interaktion des Benutzers mit dem Hard- und Softwaresystem ab. Bei einem Anwendungssystem handelt es sich um den informationstechnischen Teil eines Fachverfahrens.

**2.3** Ein verpflichtend zu nutzendes Anwendungssystem (ehemals Grundverfahren) ist ein System, welches zentral bereitgestellt wird und für das eine Nutzungsverpflichtung für alle Dienststellen und Einrichtungen des Landes im Geltungsbereich dieser Verwaltungsvorschrift festgelegt wurde.

**2.4** Die Anwendungsarchitektur beschreibt die grundlegende Organisation eines Anwendungssystems, bestehend aus Komponenten und ihren Beziehungen.

**2.5** Eine Anwendungslandschaft ist die Gesamtheit aller Anwendungssysteme innerhalb einer Organisation.

**2.6** Als elektronische Archivierung wird die datenbankgestützte, langzeitige, sichere und unveränderbare Aufbewahrung reproduzierbarer Informationsobjekte verstanden. Gemäß Landesarchivgesetz (LArchG) wird mit diesem Begriff der Transfer von archivwürdigen Informationen und Daten als Archivgut an das Landesarchiv bezeichnet. Archivgut sind Informationen, die zur Erfüllung der Aufgaben der Behörden nicht mehr erforderlich sind und die wegen ihres historischen oder rechtlichen Werts auf Dauer zu erhalten sind.

**2.7** Basissoftware ist der Teil eines Softwaresystems, der fachlich unabhängigen Programmcode beinhaltet.

**2.8** Ein Basissystem ist ein Hard- und Softwaresystem, das nicht-fachspezifische Funktionen ressortübergreifend zur Verfügung stellt.

**2.9** Das Business Continuity Management ist eine Managementmethode, die anhand eines Lebenszyklus-Modells die Fortführung der Geschäftstätigkeit unter Krisenbedingungen oder zumindest unvorhersehbar erschwerten Bedingungen absichert. Dabei handelt es sich um eine Sammlung von Maßnahmen und Prozessen, die den Fortbestand der Geschäftstätigkeit einer Organisation im Störungsfall sicherstellen und das mit der Störung verbundene Schadenspotenzial minimiert.

**2.10** Ein Dienst stellt eine technische, eigenständige Einheit dar, die logisch zusammenhängende Funktionalitäten bündelt und diese über eine wohldefinierte Schnittstelle zur Verfügung stellt. Darüber hinaus sind in einem entsprechenden Servicevertrag (Service Contract) für die Nutzung relevante Richtlinien und Rahmenparameter hinterlegt (zum Beispiel bezüglich Performanz, Verfügbarkeit etc.) Ein Dienst wird mittels eines entsprechenden Anwendungs- oder Basissystems implementiert (je nachdem ob die dort gebündelten Funktionalitäten fachspezifisch oder fachunabhängig sind).

**2.11** Eine Domäne bezeichnet im Sinne dieser Verwaltungsvorschrift ein Fachgebiet.

**2.12** Ein Fachverfahren ist ein fachspezifisches Verfahren, das in der Regel durch ein Anwendungssystem unterstützt wird.

**2.13** Die Geschäftsarchitektur beschreibt das Zusammenwirken von Geschäftsobjekten und Geschäftsprozessen zum Erreichen der Geschäftsziele.

**2.14** Ein Informationssystem ist ein aus Hard- und Softwarekomponenten bestehendes Anwendungssystem, das für ein fachliches Aufgabengebiet die Vollständigkeit der Mensch-Technik-Interaktion zur Lösung der betrieblichen Aufgaben abbildet. Bei einem Informationssystem handelt es sich um die technische Umsetzung eines Fachverfahrens.

**2.15** Die IT-Architektur ist neben der Geschäftsarchitektur der Teil der Unternehmensarchitektur, der die fachliche Struktur der Anwendungslandschaft einschließlich der zugrundeliegenden software- und hardwaretechnischen Komponenten beschreibt.

**2.16** Eine Langzeitspeicherung bezeichnet die Aufbewahrung von Informationen über die Lebensdauer von Hard- und Software hinaus, jedoch mit einer definierten Aufbewahrungsfrist. Sie ist ein Teilaspekt einer Archivierung.

**2.17** Ein Softwaresystem setzt sich aus Anwendungssoftware und zugeordneter Basissoftware zusammen.

**2.18** Eine Softwarekomponente ist ein modularer und wiederverwendbarer Teil eines Softwaresystems, der klar definierte Schnittstellen besitzt und unabhängig von anderen Komponenten entwickelt, getestet und eingesetzt werden kann. Sie besteht aus einer Kombination von Programmcode, Daten und Ressourcen, die zusammen eine bestimmte Funktionalität bereitstellen.

**2.19** Eine Stored Procedure bezeichnet eine programmierte Abfolge fachlicher Funktionen innerhalb eines Datenbankmanagementsystems.

**2.20** Aufgabe der Unternehmensarchitektur ist es, den Einsatz der Informationstechnologie optimal auf die Aufgaben und Ziele aller Fach- und Querschnittsdomänen auszurichten. Sie bildet eine ganzheitliche Sicht auf die Geschäftsarchitektur und die zugrundeliegende IT-Architektur.

**2.21** Für IT-Projekte und IT-Vorhaben gelten die Begriffsdefinitionen der Nummern 2.3 und 2.5 VwV IT-Organisation vom 1. Januar 2025 in ihrer jeweils geltenden Fassung.

## 3 Übergreifende Architekturvorgaben

### 3.1 Frühzeitige und vollständige Berücksichtigung der rechtlichen Rahmenbedingungen

Rechtliche Rahmenbedingungen sind bereits bei der Planung von Anwendungssystemen zu berücksichtigen.

### 3.2 Verwendung von Standards und einheitlichen Methoden

Für die Entwicklung und den Betrieb von IT-Systemen sind standardisierte Vorgehensmodelle sowie einheitliche Architekturen, Middleware-Komponenten und Software-Bibliotheken zu verwenden, die wiederrum standardisierte Schnittstellen bereitstellen. Auf die Einhaltung gängiger Best-Practices ist zu achten.

### 3.3 Informations- und Cybersicherheit

Verbindliche Vorgaben zur Informations- und Cybersicherheit ergeben sich insbesondere aus dem IT-Staatsvertrag, aus dem EGovG BW, dem CSG BW und nach Inkrafttreten auch der zugehörigen Cybersicherheitsverordnung, der Sicherheitsverordnung Portalverbund sowie aus der Verwaltungsvorschrift des Innenministeriums zur Informationssicherheit. Diese Vorgaben sind ebenso wie die Regelungen zum Datenschutz und zum Geheimschutz frühzeitig bei der Planung und Konzeption von IT-Projekten zu beachten.

### 3.4 Vorgaben zum Datenschutz

Bei der Konzeption, Umsetzung und dem Betrieb ist nach dem Prinzip »Privacy by Design - Privacy by Default« zu verfahren, das heißt der Schutz und die Sicherheit personenbezogener Daten muss Standardvorgabe und oberstes Designprinzip sein. Hierfür sind die Vorgaben aus der Datenschutzgrundverordnung (DSGVO) und der Richtlinie (EU) 2016/680 (JI-Richtlinie) umzusetzen. Insbesondere die in Artikel 5 und 25 der Datenschutzgrundverordnung (DSGVO) dargelegten Grundsätze sind nachweisbar einzuhalten. Bereits in der Designphase sollte die zuständige Person für den Datenschutz und die Informationsfreiheit beratend zugezogen werden.

Gemäß Kapitel III der DSGVO sind die Betroffenenrechte und entsprechende Anforderungen (zum Beispiel proaktive Benachrichtigungen gemäß Artikel 13 und Artikel 14 DSGVO, das Auskunftsrecht gemäß Artikel 15 DSGVO sowie Berichtigungs- und Widerspruchsrecht etc.) bei Konzeption, Umsetzung und Betrieb von Anwendungssystemen zu berücksichtigen und gegebenenfalls in Form eines Auftragsverarbeitungsvertrags zu regeln.

Um der Datenschutz-Folgenabschätzung nach Art. 35 DSGVO gerecht zu werden, sind zuständige Datenschutzbeauftragte möglichst frühzeitig einzubinden.

Die Anforderungen an die Sicherheit der Verarbeitung aus Art. 32 DSGVO sind einzuhalten. Es sind technische und organisatorische Maßnahmen nach dem Stand der Technik zu treffen, um ein dem Risiko angemessenes Schutzniveau zu gewährleisten. Sensible personenbezogene Daten sind grundsätzlich verschlüsselt zu speichern, so dass auch die Systemadministration ohne weiteres keinen Zugriff auf die Klartext-Daten hat.

Für die Kommunikation per E-Mail insbesondere mit Bürgerinnen und Bürgern ist eine Form der gesicherten Kommunikation nach Internet-Standards anzubieten.

Gemäß den Architekturvorgaben zur Gewährleistung der Informationssicherheit, des Datenschutzes, des Geheimschutzes und der Informationsfreiheit sind alle geltenden rechtlichen Anforderungen zu erfüllen. Die hier aufgeführten Aspekte können nicht umfassend alle Bereiche des Datenschutzes abdecken. Anwendungsspezifische Datenschutzbetrachtungen auf Grundlage des jeweils geltenden Rechts und im Sinne des spezifischen Zweckes der Anwendung sind daher unerlässlich.

### 3.5 Vorgaben zur Informationsfreiheit

Bereits bei der Konzeption von Anwendungssystemen sind die geltenden Vorgaben zur Informationsfreiheit zu beachten (zum Beispiel Landesinformationsfreiheitsgesetz).

### 3.6 Berücksichtigung von Referenzarchitekturen

Bei der Konzeption und Entwicklung von Anwendungssystemen sind die für die Landesverwaltung festgelegten Referenzarchitekturen vorrangig zu berücksichtigen. Sofern keine für das zukünftige Anwendungssystem geeignete Referenzarchitektur vorliegt, sind nach dem jeweils aktuellen Stand der Technik für diese Klasse der Anwendungssysteme entsprechende Architektur- und Entwurfsmuster zu nutzen.

### 3.7 Sicherstellung der Benutzungsfreundlichkeit

Anforderungen an die Ergonomie von Informationssystemen, insbesondere der Norm DIN EN ISO 9241, sind bereits in der Konzeptionsphase zu berücksichtigen. Dies gilt sowohl für die Beschaffung von Individualsoftware als auch für den Erwerb von Standardsoftware.

### 3.8 Sicherstellung der Barrierefreiheit

Mediale Angebote der Landesverwaltung sind entsprechend der Maßgaben des Landes-Behindertengleichstellungsgesetzes vom 17. Dezember 2014 (GBl. S. 819) sowie der Verordnung zur Schaffung barrierefreier Informationstechnik nach dem Behindertengleichstellungsgesetz (BITV 2.0) in der jeweils geltenden Fassung barrierefrei zu gestalten.

Vor Vertragsschluss bzw. dem Einsatz von Software ist die Barrierefreiheit durch geeignete Maßnahmen (z. B. unter Verwendung der im Land eingesetzten Screenreader) durch entsprechend geschultes Personal zu testen.

### 3.9 Vermeidung von Herstellerabhängigkeiten

Der Technologieeinsatz in der Landesverwaltung ist so zu konzipieren und umzusetzen, dass Abhängigkeiten zu Herstellern und Supportanbietern minimiert werden. Soweit möglich sollen daher bei Entwicklung und Betrieb offene Standards oder Branchenstandards eingesetzt werden und enge Kopplungen an proprietäre Systeme vermieden werden. Hierzu zählen neben (umfangreichen) Anwendungssystemen bspw. herstellerspezifische Erweiterungen von Application Servern, Datenbankmanagementsysteme (insbesondere Stored Procedures), proprietäre Softwarebibliotheken etc. Bei Individualentwicklungen durch externe dienstleistende Personen oder Unternehmen ist, sofern die Landesverwaltung nicht im Besitz des Quelltexts ist, darauf hinzuwirken, dass der zugehörige Quelltext der Landesverwaltung möglichst unter einer von der OSI anerkannten Open-Source-Lizenz für die weitere Entwicklung und Nutzung zur Verfügung steht. Soweit der Einsatz herstellerspezifischer Funktionen erforderlich ist, sollten diese soweit möglich so gekapselt werden, dass ein späterer Austausch erleichtert wird. Darüber hinaus ist für Anwendungen grundsätzlich sicherzustellen, dass ein Wechsel des angebotsstellenden Unternehmens mit vertretbarem Aufwand möglich ist.

### 3.10 Gewährleistung der Interoperabilität von Anwendungen und Diensten

Anwendungen und Dienste sind derart zu konzipieren, dass ihre Kommunikation mit anderen Systemen über standardisierte Protokolle und Beschreibungssprachen erfolgen kann. Die Interoperabilität wird durch den Einsatz geeigneter Austauschformate und Serviceschnittstellen hergestellt. Es sollten jeweils anerkannte Internet-Standards verwendet werden.

### 3.11 Sicherstellung von loser Kopplung / Modularität

Synchrone Kopplungen zwischen Anwendungssystemen sind auf ein notwendiges Minimum zu reduzieren. Asynchrone technische Verfahren, die eine zeitliche Entkopplung erlauben, sind synchronen technischen Verfahren vorzuziehen. Dies ist bereits in der technischen Konzeption der Fachverfahren zu berücksichtigen. Insbesondere eine enge Kopplung von Anwendungssystemen über einen Direktzugriff auf eine gemeinsame Datenbank ist nicht erlaubt. Stattdessen sind entsprechende Aufrufe über eine separate Zugriffsschicht abzubilden.

### 3.12 Gewährleistung einer nachhaltigen Informationstechnik

Für den gesamten Lebenszyklus von IT-Systemen ist eine umweltschonende und nachhaltige Nutzung zu berücksichtigen. Dies schließt die Entwicklung, die Beschaffung energieeffizienter IT-Geräte, den ressourcenschonenden Betrieb sowie die umweltverträgliche Aussonderung ein.

### 3.13 Reduzierung der Komplexität auf ein notwendiges Maß

Die Komplexität von Anwendungssystemen selbst, als auch die Komplexität bzgl. ihrer Interaktion mit anderen Systemen ist so gering wie möglich zu halten. So sind Anwendungssysteme derart zu konzipieren und umzusetzen, dass sie auch für andere Entwickelnde verständlich und wartbar sind. Dies schließt sowohl die Dokumentation des Quelltextes als auch die Art und Weise der Programmierung ein (zum Beispiel Verschachtelungstiefe, eindeutige Schnittstellen, Typsicherheit, Kapselung, Fassadenzugriff). Abhängigkeiten zu entfernten Systemen sind soweit wie möglich gering zu halten.

### 3.14 Qualitätssicherung und automatisierte Tests

Zur Unterstützung der Qualitätssicherung sind automatisierte Tests wie Modul- und Regressionstests mit ausreichender Testabdeckung zu verwenden. Die Tests sollten auch die Einhaltung der Regelungen zur Code-Komplexität sowie von üblichen Best Practices überprüfen.

### 3.15 Verwendung von Standardbibliotheken

Soweit möglich, sind etablierte Standardbibliotheken und -Komponenten in einer aktuellen Version, die alle Sicherheitsmaßnahmen und Fehlerbehebungen einschließt, zu verwenden. Änderungen oder Ergänzungen an unter Open-Source-Lizenz stehenden Bibliotheken sind zu vermeiden.

### 3.16 Sicherstellung der Wirtschaftlichkeit von Architekturen und korrespondierenden Vorhaben

Architekturentscheidungen erfolgen auf der Grundlage einer transparenten Wirtschaftlichkeitsbetrachtung, die den fachlichen Nutzen der Lösung, den Lebenszyklus des IT-Systems und dessen Rolle innerhalb der gesamten Anwendungslandschaft der Landesverwaltung berücksichtigt. Sie sind immer im Gesamtkontext der Landes-IT zu treffen.

IT-Systeme sind im jeweiligen fachlichen Anwendungsbereich darüber hinaus derart zu dimensionieren, dass funktionale und nicht-funktionale Anforderungen einerseits nicht übererfüllt werden, andererseits sie jedoch eine spätere Skalierung erlauben.

### 3.17 Vorgehensmodelle zur Umsetzung von Anwendungssystemen

Für die Umsetzung von Anwendungssystemen muss ein zum Projektmanagement passendes Vorgehensmodell zur Softwareentwicklung eingesetzt werden. Hierbei ist für zugehörige Wartungsaufgaben (unter Wartungsaufgaben wird neben den Kategorien »Korrigierende Wartung«, »Anpassungswartung«, »Perfektionierende Wartung«, »Unterstützung und Betreuung« auch die Kategorie »Funktionserweiterung« verstanden) der Softwarelebenszyklus zu beachten, d. h. die für ein Anwendungssystem relevanten IT-Prozesse und die über eine initiale Bereitstellung hinaus gegebenenfalls notwendigen Softwareentwicklungsarbeiten (Fehlerbereinigung, Weiterentwicklung etc.).

Das Vorgehensmodell zur Softwareentwicklung muss insbesondere die Erstellung und Pflege eines Fachkonzepts zur Beschreibung der funktionalen und nicht-funktionalen Anforderungen aus Sicht des Auftraggebers enthalten sowie Maßnahmen zur Qualitätssicherung und Abnahme von Arbeitsergebnissen festlegen. Ferner ist das für die Softwareentwicklung verantwortliche Projekt für die erfolgreiche Übernahme in den Betrieb verantwortlich. Hierzu ist auf eine frühzeitige Einbindung des Betriebsdienstleisters zu achten.

### 3.18 Architekturmanagementprozess

Die ressortübergreifende Definition und Umsetzung der Architekturvorgaben, Referenzarchitekturen und technischen Spezifikationen sowie die Sicherstellung deren Einhaltung erfolgt innerhalb eines Architekturmanagementprozesses durch ein Architekturboard, das sich im monatlichen Turnus aus den Domänenarchitekturverantwortlichen des Landes zusammensetzt. Nähere Bestimmungen zum genauen Verfahren finden sich in Anlage 2 zu dieser Verwaltungsvorschrift.

### 3.19 Vorgaben zur Nutzung von Cloud-Diensten

Bei der Einrichtung und Bereitstellung als auch bei der Nutzung von Cloud-Diensten sind die Vorgaben der durch den IT-Rat am 4. Dezember 2020 beschlossenen Cloud-Strategie des Landes Baden-Württemberg zu beachten.

### 3.20 Vorgaben zur Gewährleistung eines sicheren und stabilen Betriebs

Anwendungssysteme einschließlich ihrer zugehörigen software- und hardwaretechnischen Bestandteile müssen bzgl. aller verwendeter Softwarekomponenten jederzeit über einen Herstellersupport verfügen. Eingesetzte Softwarekomponenten dürfen den Zustand »End-of-life« (es besteht keine Unterstützung mehr seitens des Herstellers) nicht erreicht haben. Für Anwendungssysteme, die Satz 1 und Satz 2 nicht erfüllen, ist eine Risikoanalyse unter Einbeziehung des Informationssicherheitsbeauftragten des Ressorts sowie des technischen Betreibers durchzuführen.

Über Abweichungen von Satz 1 und Satz 2 ist die für die IT-Landesarchitektur beauftragte Person zu informieren.

## 4 Vorgaben zur Geschäftsarchitektur

### 4.1 Dokumentation von Verwaltungsprozessen

Zur Dokumentation von Verwaltungsprozessen sind landeseinheitliche Modellierungssprachen und geeignete grafische Notationen zu verwenden. Eine Auflistung dieser findet sich in Anlage 1 zu dieser Verwaltungsvorschrift.

Dokumentationsbedarf besteht insbesondere

- für verwaltungsübergreifende Geschäftsprozesse
- für Prozesse, die personenbezogene Daten verarbeiten,
- für Verfahren, die eine systemtechnische Workflowsteuerung beinhalten,
- sowie für Verfahren, für die aktuell oder zukünftig eine Prozessmodellierung stattfindet oder stattfinden soll.

Bei der Modellierung ist auf einen geeigneten und allgemein verständlichen Detaillierungsgrad zu achten.

### 4.2 Vorgaben zum Informationsaustausch (fachlich / semantisch)

Für Verfahren, die Daten für andere Verfahren zur Verfügung stellen, ist eine semantische Beschreibung der Austauschdaten anzufertigen.

## 5 Vorgaben zur Anwendungsarchitektur

### 5.1 Verpflichtende Nutzung von Anwendungssystemen

Anwendungssysteme beziehungsweise Dienste für Querschnittsfunktionen, die für die ressortübergreifende Verwendung festgelegt wurden, sind verbindlich zu nutzen. Eine verbindliche Nutzung setzt die Benennung einer für das Verfahren beziehungsweise Produkt verantwortlichen Stelle voraus. Nähere Bestimmungen finden sich in Anlage 1 zu dieser Verwaltungsvorschrift.

### 5.2 Dokumentation der Anwendungsarchitektur

Für jedes Anwendungssystem ist während der Konzeptionsphase eine Dokumentation der Anwendungsarchitektur zu erstellen. Diese enthält mindestens eine Darstellung der

- entwickelten beziehungsweise verwendeten Komponenten und Module einschließlich ihrer Funktion und Verteilung auf spezifische Netzwerksegmente (DMZ etc.),
- bereitgestellten Schnittstellen und allen Schnittstellenaufrufen zu entfernten Komponenten,
- genutzten (Querschnitts-)Dienste,
- begründeten Abweichungen und Besonderheiten,
- implementierten Maßnahmen und Mechanismen zur Gewährleistung von Datenschutz und Informationssicherheit oder entsprechende Verweise auf das Sicherheitskonzept
- für das Systemverständnis und für eine Erweiterung relevanten Randbedingungen und übergreifenden Architekturaspekte.

Diese Dokumentation ist während des gesamten Lebenszyklus der Anwendung zu pflegen und bereitzustellen.

### 5.3 Dokumentation der anwendungsübergreifenden Schnittstellen und zugehörigen Dienste

Anwendungsübergreifend bereitgestellte Dienste und Schnittstellen sind hinsichtlich ihres Leistungsumfangs, ihrer Leistungsqualität sowie den für deren Nutzung relevanten Rahmenbedingungen geeignet zu dokumentieren. Hierzu sind folgende Angaben in Anlehnung an IEC 62304 erforderlich:

- Name und Zweck der Schnittstellenfunktion beziehungsweise des Dienstes,
- Name, Bedeutung und Wertebereiche von Übergabe- und Rückgabeparametern
- Verhalten des Dienstes bei Nutzung der zugehörigen Schnittstellenfunktionen (zum Beispiel hinsichtlich Fehlertoleranz, Performanz, Sicherheit, Robustheit, Zuverlässigkeit etc.)

### 5.4 Nutzung vorgegebener Entwicklungslinien

Neue Entwicklungsvorhaben der Landesverwaltung, die mit eigenem Fachpersonal durchgeführt werden, sind mittels der vorgegebenen Entwicklungslinien des Landes umzusetzen. Dies gilt ebenso für Entwicklungsvorhaben, die durch Dritte durchgeführt werden und mit entsprechenden Nutzungsrechten des Landes am Quellcode eine Weiterentwicklung ermöglichen. Abweichungen von den vorgegebenen Entwicklungslinien erfordern die Zustimmung der für die IT-Landesarchitektur beauftragten Person. Eine Auflistung der entsprechenden Entwicklungslinien einschließlich der damit verbundenen Entwicklungsstandards befindet sich in Anlage 1 zu dieser Verwaltungsvorschrift.

### 5.5 Vorgaben zu grafischen Benutzungsschnittstellen

Benutzungsschnittstellen dienen ausschließlich dem Informationsaustausch zwischen Anwendung und System und sind Client-seitig grundsätzlich plattformunabhängig zu konzipieren und umzusetzen. Entsprechend der Zuständigkeitstrennung (Separation of Concerns) sind grafische Benutzungsschnittstellen frei von fachlicher Logik zu implementieren.

### 5.6 Nutzung von Middleware-Plattformen

Beim Einsatz einer Middleware-Plattform ist die Verwendung der in Anlage 1 zu dieser Verwaltungsvorschrift vorgegebenen und dem jeweiligen Einsatzzweck entsprechenden Technologie vorzusehen. Der Begriff »Middleware-Plattformen« bezieht sich im Rahmen dieser Verwaltungsvorschrift insbesondere auf Application Server, Technologien zur Anwendungsintegration (Enterprise Application Integration - EAI) wie Bus-Systeme und Prozess-Engines (Enterprise Service Bus - ESB), Technologien zur asynchronen Kommunikation (Message Oriented Middleware - MOM) und Technologien zur verteilten Kommunikation (Object Request Broker - ORB).

### 5.7 Berücksichtigung von Virtualisierung und Automatisierung

Methoden zur Virtualisierung von Umgebungen im Sinne einer wirtschaftlichen Betreibbarkeit von Anwendungen sowie Maßnahmen zur Automatisierung des Entwicklungs- und Bereitstellungsprozesses sind bereits in der Konzeptionsphase zu berücksichtigen.

### 5.8 Berücksichtigung betriebsrelevanter nicht-funktionaler Anforderungen

Betriebsrelevante nicht-funktionale Anforderungen sind bereits während der Konzeptions- und Designphase einer Anwendung mit dem Betriebsdienstleistenden Unternehmen abzustimmen. Hierzu zählen insbesondere Anforderungen an Systemressourcen, Skalierbarkeits- und Sicherheitsaspekte etc.

### 5.9 Festlegungen zu Austauschformaten (technisch / konkret)

Zum Datenaustausch mit Basis- beziehungsweise Anwendungssystemen sind einheitliche beziehungsweise standardisierte Datei- und Datenaustauschformate zu nutzen (siehe Nummer 7.4). Sofern vorhanden, sind darüber hinaus keine proprietären, sondern offene Austauschformate und Standards einzusetzen. Als Leitlinie für solche Austauschformate gilt, dass deren Spezifikation vollständig publiziert wurde und die Publikation entweder kostenfrei oder gegen ein angemessenes Entgelt erhältlich ist sowie dass die Verwendung der Spezifikation für Herstellende und Nutzende der Software-Systeme uneingeschränkt und kostenfrei möglich ist. Herstellerspezifische Erweiterungen bestehender Standards sind, soweit möglich, zu vermeiden.

### 5.10 Verwendung des Unicode-Standards

Der Standard »Lateinische Zeichen in UNICODE/DIN SPEC 91379« (String.Latin+ 1.2) ist in der Landesverwaltung für alle IT-Verfahren, die dem Bund-Länder übergreifenden Datenaustausch oder dem Datenaustausch mit Bürgern und Wirtschaft dienen, zu verwenden. Dieser Standard wird im Auftrag des IT-Planungsrats entwickelt. Die Unicode-Zeichen sind mit UTF-8 zu kodieren. Die Nutzung von Zeichensätzen, die keine vollständige Abbildung von String.Latin+ erlauben, ist ausgeschlossen. Für IT-Lösungen, die eine andere Kodierung erfordern, ist im Einzelfall auch über UTF-8 hinaus der Einsatz von UTF-16 beziehungsweise UTF-32 zulässig.

### 5.11 Fachliches Monitoring

Für wesentliche Funktionen eines Anwendungssystems beziehungsweise eines Dienstes ist ein fachliches Monitoring vorzusehen, das die Herleitung von Kennzahlen in Relation zu den vorhandenen Systemkennzahlen des Systemmonitorings (siehe Nummer 6.3) ermöglicht. Zudem sind für ein fachliches Monitoring verschiedene Logging-Level umzusetzen und zu dokumentieren, die eine Analyse des Laufzeitverhaltens im Betrieb vereinfachen.

## 6 Vorgaben zur Systemarchitektur

### 6.1 Verwendung der Hardware- und Softwarestandards für technische Infrastruktur

Die Standards für Systemarchitekturen und für die technische Infrastruktur sind einzuhalten (siehe Nummer 7.6). In begründeten Fällen kann bei Spezialhardware hiervon abgewichen werden. Solche Abweichungen sind nur nach Zustimmung durch die IT-Landesarchitektin beziehungsweise den IT-Landesarchitekten zulässig.

### 6.2 Verwendung energieeffizienter und ressourcenschonender Technologien

Bei den eingesetzten IT-Systemen ist über den gesamten Lebenszyklus hinweg - Beschaffung, Nutzung und Weiterverwertung - auf Energieeffizienz und Ressourcenschonung zu achten. Die Regelungen der VwV-Beschaffung sind bei Ausschreibungen zu beachten.

### 6.3 Vorgaben für das Monitoring

Serversysteme sind mit einem einheitlichen Systemmonitoring auszustatten, welches Kennzahlen einzelner Komponenten (zum Beispiel CPU, Speicher, Disk, Netz) zur Laufzeit erfasst und bereitstellt. Darauf aufbauend ist bereits beim Design von Anwendungen und Diensten die Bereitstellung von Kennzahlen zur Laufzeit im Sinne einer Überprüfung und Gewährleistung vorgegebener nicht-funktionaler Anforderungen zu berücksichtigen. Für jede Anwendung, die innerhalb der Landesverwaltung entwickelt wird, muss ein angemessenes Monitoringkonzept unter Berücksichtigung der Anforderungen des Betriebs erstellt werden. Dieses sollte die Verwendung standardisierter Schnittstellen und sicherer Übertragungswege darstellen, so dass Monitoring-Daten durch standardisierte Werkzeuge verarbeitet werden können.

### 6.4 Vorgaben zur Netzwerkarchitektur

Die Netzwerkarchitektur ist so zu planen und umzusetzen, dass der Schutz von Informationen in Netzwerken und den unterstützenden informationsverarbeitenden Einrichtungen nach dem jeweils aktuellen Stand der Technik sichergestellt ist. Hierbei sind auch Schutzmaßnahmen erforderlich, die den Schutzbedarf der Netzwerkarchitektur innerhalb des Landesverwaltungsnetzes berücksichtigen. Die Sicherheit von übertragener Information, sowohl innerhalb des Landesverwaltungsnetzes als auch mit jeglicher externen Stelle, ist durch geeignete Maßnahmen zu gewährleisten. Bis zu den Außengrenzen der Verwaltungssysteme sind technische Maßnahmen zu ergreifen. Darüber hinaus ist die Sicherheit übertragener Information mittels geeigneter Verträge beziehungsweise Bindungen bei den beteiligten externen Stellen einzufordern.

Zwischen den Subnetzen sind die Kommunikationsprotokolle festzulegen, die zur Kommunikation benutzt werden können und auf den Firewall-Systemen freizuschalten sind. Die damit verbundenen Risiken, sind von den Verantwortlichen der beteiligten Subnetze zu tragen.

Die Domäne *.bwl.de ist die Domäne des Landesverwaltungsnetzes (LVN). Das bedeutet, dass E-Mails mit der Absenderdomäne *.bwl.de nicht aus anderen Netzen in das Landesverwaltungsnetz gesendet werden dürfen und somit verworfen werden. Web-Server mit der Domäne *.bwl.de dürfen nur innerhalb des Landesverwaltungsnetzes verwendet werden. Mailserver sind unter Beachtung der geltenden Vorgaben zur Informationssicherheit zu konfigurieren. Methoden wie die serverseitige Prüfung des Vorliegens einer Sende-Autorisierung für eine Domäne müssen genutzt werden.

An das LVN angeschlossene lokale Netze der Dienststellen dürfen ausschließlich über den Internet-Zugang der BITBW mit dem Internet verbunden werden. Für die Einwahl in die lokalen Netze der Landesverwaltung ist ein VPN-Zugang der BITBW zu nutzen.

### 6.5 Vorgaben zur Nutzung von extern gehosteten Diensten und Plattformen

Der Einsatz von Diensten und Plattformen die privatwirtschaftlich zur Verfügung gestellt werden, erfordert die Information der für die Informationssicherheit der Landesverwaltung sowie der für die IT-Landesarchitektur zuständigen Person.

## 7 Technische Spezifikationen

### Vorbemerkung

Nachfolgende Festlegungen und Spezifikationen sind einzuhalten.

### 7.1 Festlegungen zur Kopplung von Anwendungssystemen

Anwendungssysteme beziehungsweise Basissysteme werden mit Hilfe standardisierter und universell einsetzbarer Kommunikationsprotokolle miteinander gekoppelt. Der Einsatz programmiersprachenspezifischer Protokolle wie zum Beispiel RMI ist nicht zulässig (eine Ausnahme bildet der systemspezifische Remote Function Call (RFC) im SAP-Umfeld). Für die synchrone Kommunikation können folgende Protokolle verwendet werden:

- HTTPs
- RFC
- SOAP über HTTPs
- REST über HTTPs
- gRPC (nicht für Eigenentwicklungen)

Die Kommunikation von Anwendungssystemen muss gemäß den jeweils geltenden rechtlichen und notwendigen sicherheitstechnischen Anforderungen abgesichert werden. Dabei ist eine Transportverschlüsselung nach BSI TR-02102-2 zu verwenden.

### 7.2 Grundausstattung des einheitlichen BK-Arbeitsplatzes

Die Definition des einheitlichen BK-Arbeitsplatzes in seiner Grundausstattung orientiert sich am Pflichtenheft für die Einführung eines Standardarbeitsplatzes für die Landesverwaltung. In dieses Dokument wurden die Ziele und Anforderungen der Ressorts sowie der BITBW an die Grundausstattung aufgenommen und einschließlich der technischen Umsetzung dokumentiert.

### 7.3 Desktop-Web-Browser

Standard für Desktop-Web-Browser innerhalb der Landesverwaltung sind Produkte auf Basis der Chromium-Engine. Die Bereitstellung eines Browsers mit alternativer Engine ist möglich. Für sämtliche webbasierten Anwendungen der Landesverwaltung ist sicherzustellen, dass diese unter Verwendung des Standards für Desktop-Web-Browser korrekt dargestellt und mit vollständigem Funktionsumfang genutzt werden können. Dies betrifft sowohl Eigenentwicklungen der Landesverwaltung als auch Software von Drittanbietern.

Es ist darauf hinzuwirken, dass Anwendungen der Landesverwaltung, die über das Internet für Dritte zugänglich sind, mittels der am stärksten verbreitetsten Browser, die die gängigen Sicherheitsstandards einhalten, ohne Einschränkungen genutzt werden können.

### 7.4 Standardisierte Austauschformate

Als Datenaustauschformate für die behördenübergreifende Kommunikation sind bevorzugt zertifizierte XöV-Standards zu verwenden. Eine Übersicht und weiterführende Informationen zu den XöV-Standards finden sich u. a. unter www.xrepository.de (herausgegeben von der für die XöV-Standards verantwortlichen Koordinierungsstelle für IT-Standards - KoSIT).

### 7.5 IT-Standards für Geoinformationen, Geo-Daten, Geoanwendungen und -diensten

Vorgaben zu Geoinformationen, Geo-Daten und Austauschformaten, Geoanwendungen und -diensten finden sich in Anlage 1 zu dieser Verwaltungsvorschrift.

### 7.6 Hardware- und Softwarestandards für Server und Clients

Grundlage der auf die funktionalen und nicht-funktionalen Anforderungen der Ressorts ausgerichteten Hardware- und Softwarestandards für Server und Clients ist das zur Erbringung der entsprechenden Leistungen gemäß BITBW IT-Servicekatalog definierte und mit der Stelle für IT-Koordination im Innenministerium abgestimmte Hardware- & Software Portfolio.

### 7.7 Netzstandards

Es gelten die Vorgaben der »LAN-Konzeption der Landesverwaltung Baden-Württemberg einschließlich Hochschulbereich« gemäß Anlage 3.

### 8 Nutzung vorgegebener Entwicklungslinien

Soweit vorhanden, sind für landeseigene Entwicklungsvorhaben, die nicht innerhalb länderübergreifender Kooperationen stattfinden, standardisierte Entwicklungslinien zu nutzen. Näheres zu den Entwicklungslinien findet sich Anlage 1 zu dieser Verwaltungsvorschrift.

### 9 Standards zum Management von IT-Projekten

Die Vorgaben zur Bewertung von IT-Vorhaben und IT-Projekten sowie für deren Planung, Beantragung und Durchführung gemäß Anlage 2 zu dieser Verwaltungsvorschrift sind einzuhalten.

### 10 Übergangs- und Schlussvorschriften

**10.1** Auf am 1. Januar 2019 bereits produktive Systeme ist diese Verwaltungsvorschrift nicht anwendbar, es sei denn, die Systeme erfahren wesentliche Änderungen oder verletzen Nr. 3.20. Ob eine wesentliche Änderung vorliegt, entscheidet die IT-Landesarchitektin oder der IT-Landesarchitekt unter Berücksichtigung von Wirtschaftlichkeitsaspekten im Benehmen mit dem Architekturboard sowie der oder dem Vorhabenverantwortlichen und der jeweiligen Systemarchitektin oder dem jeweiligen Systemarchitekten.

**10.2** Diese Verwaltungsvorschrift tritt mit Wirkung vom 1. Januar 2025 in Kraft. Sie tritt am 31. Dezember 2031 außer Kraft. Gleichzeitig mit dem Inkrafttreten tritt die VwV IT-Standards vom 10. Dezember 2021 (GABl. 2022, S. 306) außer Kraft.

## Anlage 1: Technische Spezifikationen und Entwicklungslinien (zu Nummer 4.1, 5.1, 5.4, 5.6, 7.5, 8)

### 1 Allgemeine Vorgaben zum Technologieeinsatz (zu Nr. 4.1, 5.1, 5.6 VwV IT-Standards)

**1.1 Grafische Notationen zur Prozessmodellierung sowie Systeme zur technischen Prozessunterstützung**

Für die Modellierung geschäftsbezogener Prozesse (hierunter fallen nicht die Prozesse einer IT-Organisation) sind folgende Notationen zugelassen:

- Business Process Modeling Notation (ab BPMN Version 2.0)

Eingesetzte Modellierungswerkzeuge müssen für die weitere Verwendung der Modelle den BPMN 2.0-Standard zur Speicherung und zum Austausch umsetzen.

- Ereignisgesteuerte Prozessketten (EPK)

Vorrangig ist BPMN einzusetzen, insbesondere in der Zusammenarbeit zwischen Fachbereichen und IT sowie bei Modellen, die um operative Aspekte ergänzt werden. EPK kann als Alternative gegebenenfalls zur Dokumentation von Top-Level-Prozessen verwendet werden. Als Prozess-Engine, mit dessen Hilfe BPMN-Modelle zur Laufzeit ausgeführt werden, sind folgende Produkte zu verwenden:

- jBPM
- Activiti
- Camunda Community Edition
- ActiveVOS (in Abstimmung mit dem IT-Landesarchitekten)

**1.2 Festlegungen zur verpflichtenden Nutzung von Anwendungssystemen und Diensten**

Grundsätzlich ist für jedes IT-Projekt beziehungsweise IT-Vorhaben zu prüfen, ob im Falle des Einsatzes eines fachspezifischen Anwendungssystems dessen fachliche Anforderungen durch die Nutzung und gegebenenfalls Erweiterung eines bereits innerhalb der Landesverwaltung vorhandenen fachspezifischen Anwendungssystems weitgehend abgedeckt werden.

Für die nachfolgend in Fachdomänen gruppierten Anwendungsfälle werden verpflichtend zu nutzende fachspezifische Anwendungssysteme bereitgestellt.

**1.2.1 Domäne Personal:**

- Beamtenversorgung / Personalabrechnung: DAISY
- Beihilfeabrechnung: BABSY
- Personalverwaltung: EPVS
- Führungsinformation Personal: FISP
- Zeitwirtschaft: SAP HRM
- Fortbildungsplanung und -organisation: LFB Online
- Basissystem und die Module "Lernen", "Bildungs-", "Kommunikations-" und "Kompetenzmanagement": Bildung 21
- Dienstreisen: Drive-BW

**1.2.2 Domäne Organisation:**

- IT-Planung und -Steuerung: VORIS
- Organisationsmanagement und SAP-Berechtigungsverwaltung: SAP OM
- Stammdatenverwaltung (im SAP-Kontext): SAP MDG
- Landesintranet: BW-Portal
- Erfassung und Bearbeitung des in den Häusern der Landesverwaltung Baden-Württemberg anfallenden Schriftguts: PDV E-Akte

**1.2.3 Domäne Finanzen:**

- Kameralistisches Haushaltsmanagement: SAP PSM
- Finanzbuchhaltung / Kaufmännisches Rechnungswesen: SAP FI
- Anlagenbuchhaltung: SAP FI-AA
- Kosten- und Leistungsrechnung: SAP CO
- Immobilien- und Liegenschaftsverwaltung: SAP RE/FX
- Darlehensverwaltung (im SAP-Kontext): SAP CML
- FöBIS - Bearbeitung von Förderprogrammen: SAP-GM
- Rechnungsverarbeitung: SAP VIM

**1.2.4 Domäne Einkauf:**

- Materialwirtschaft: SAP MM

**1.2.5 Domäne Vertrieb:**

- Internet Verkauf: SAP CRM
- Produktion und Vertrieb: SAP SD
- Kundenservice (im SAP-Kontext): SAP CS
- Portal zu Verwaltungsdienstleistungen: service-bw

**1.2.6 Weitere:**

- Informationssicherheit: HiScout GRC-Suite

**1.3 Empfehlungen zur Nutzung von Anwendungssystemen**

- Shopsysteme: Webshop der Landesverwaltung

**1.4 Vorgehen zur Festlegung von verpflichtend zu nutzenden Anwendungssystemen**

Die Überprüfung eines für eine Anwendungskategorie bereits zur verpflichtenden Nutzung festgelegten Anwendungssystems sowie die Neuaufnahme eines Anwendungssystems als verpflichtend für eine Anwendungskategorie zu nutzen wird auf Initiative innerhalb oder außerhalb des Architekturboards vorgeschlagen und vom Architekturboard genehmigt. Bei einer möglichen Neuaufnahme eines Anwendungssystems werden bereits definierte verpflichtend zu nutzende Anwendungssysteme der entsprechenden Anwendungskategorie hinsichtlich einer möglichen Ablösung in die Überprüfung einbezogen.

Mit der Überprüfung bzw. Neufestlegung verpflichtend zu nutzender Anwendungssysteme ist in der Regel eine Anforderungsdefinition, Kriterienfestlegung, Marktuntersuchung und Toolauswahl durch den Initiator einer Neubewertung durchzuführen. Das Ergebnis der Überprüfung wird dem Architekturboard vorgelegt und dort bewertet. Führt die Überprüfung zu einer veränderten Festlegung der verpflichtend zu nutzenden Anwendungssysteme einer Anwendungskategorie, so ist diese mit Beschluss der VwV IT-Standards durch den IT-Rat verbindlich.

Grundsätzlich müssen Systeme, für die für eine Anwendungskategorie als verbindlich zu nutzen festgelegt wurden, wesentliche Architektur- und Qualitätsanforderungen erfüllt sein. Diese beziehen sich insbesondere auf Vorgaben zur Kopplung mit anderen Systemen, auf Aspekte der Anwendungsbetreuung, der Wartung und des Betriebs, auf allgemeine nicht-funktionale Anforderungen sowie auf Anforderungen hinsichtlich der TCO (Total Cost of Ownership).

Für Anwendungssysteme, für die im Zuge einer Neubewertung die Nutzungsverpflichtung aufgehoben wird, besteht Bestandsschutz im Sinne Nr. 1.2 VwV IT-Standards.

**1.5 Festlegungen zur Nutzung von Datenbanken und Middleware**

Beim Einsatz von Datenbanken beziehungsweise Middleware-Produkten ist darauf zu achten, dass herstellerspezifische Erweiterungen sowie produktnahe Implementierungen vermieden werden. So ist insbesondere die Verwendung von Stored Procedures in Neuentwicklungen der Landesverwaltung nicht zulässig.

Abweichungen von Systemen, die als bevorzugt einzusetzen gekennzeichnet sind, sind gegenüber der IT-Landesarchitektin oder dem IT-Landesarchitekten zu begründen.

- DBMS (SQL): Als kommerzielle Systeme sind ausschließlich Oracle DB und Microsoft SQL Server sowie im Bereich von SAP-basierten Anwendungen und Data-Warehouse-Anwendungen die SAP-Datenbank-Plattform HANA zulässig. Bei quelloffenen Systemen sind MariaDB und PostgreSQL bevorzugt einzusetzen.
- DBMS (noSQL): Es bestehen keine grundsätzlichen Einschränkungen bzgl. der Verwendung von noSQL-Datenbankmanagementsystemen, wenn zur Sicherstellung der Datenkonsistenz in der jeweiligen Anwendungssoftware besondere Schritte unternommen werden. eXistDB, MongoDB und CouchDB sind bevorzugt einzusetzen.
- Application Server: Grundsätzlich dürfen nur Produkte eingesetzt werden, die den JakartaEE-Standard unterstützen. Proprietäre Produkte dürfen nur mit Zustimmung des IT-Landesarchitekten eingesetzt werden. Hierunter fallen nicht quelloffene Produkte, für die ein Support-Vertrag abgeschlossen wird. Bevorzugt einzusetzen sind JBoss EAP (Enterprise Application Platform) beziehungsweise Wildfly. Beim Einsatz von Wildfly ist zu berücksichtigen, dass keine Security-Patches zur Verfügung gestellt werden.
- Leichtgewichtige Application Server: Zulässig sind Java Servlet Container Jetty und Tomcat
- Web Server: Bevorzugt einzusetzen sind Apache HTTP Server und nginx
- Messaging Middleware / Enterprise Integration (ESB, EAI, MOM, ORB): Bevorzugt einzusetzen sind Apache ActiveMQ, Apache Camel und Apache Axis, Apache Kafka

### 2 IT-Standards für Geoinformationen, Geo-Daten, Geoanwendungen und -diensten (zu Nr. 7.5 VwV IT-Standards)

**2.1 IT-Standards für Geoinformationen**

Geoinformationen sind Informationen mit direktem oder indirektem Bezug zu einem bestimmten Standort oder geografischen Gebiet. Die Inhalte bzw. die Sachverhalte dieser Geoinformationen werden in Geodaten dargestellt. Im Rahmen des E-Governments nehmen Geoinformationen eine Basisfunktion für vielfältige raumbezogene Fachverfahren der öffentlichen Verwaltung ein.

Geobasisinformationen sind die Informationen der Landesvermessung und des Liegenschaftskatasters, die in den Geoinformationssystemen des amtlichen Vermessungswesens vorgehalten und bereitgestellt werden.

Die Geobasisdaten sind Daten des amtlichen Vermessungswesens, welche die Landschaft, die Liegenschaften und den einheitlichen geodätischen Raumbezug anwendungsneutral nachweisen und beschreiben. Sie sind Grundlage für Fachanwendungen mit Raumbezug und fachneutrale Kernkomponenten der Geodateninfrastruktur Baden-Württemberg (GDI-BW). Geofachdaten sind auf der Grundlage der Geobasisdaten zu erfassen und zu führen (§ 2 Absatz 2 Vermessungsgesetz Baden-Württemberg (VermG) vom 1. Juli 2004 in der geltenden Fassung, § 5 Absatz 3 Landesgeodatenzugangsgesetz (LGeoZG) vom 17. Dezember 2009 in Umsetzung der INSPIRE-Richtlinie der EU vom 14. März 2007 (Infrastructure for Spatial Inforamtion in the European Community)). Um die Interoperabilität der Geodaten verschiedener Herkunft zu gewährleisten, bedarf es fachübergreifender IT-Standards in folgenden Bereichen:

- Georeferenzierung von Daten
- Datenmodelle und Austauschformate
- Metadaten
- Geodatendienste
- Geoanwendungen

Der Rahmen für fachübergreifende IT-Standards von Geodaten wird stufenweise in der europäischen Geodateninfrastruktur (INSPIRE), der nationalen Geodateninfrastruktur Deutschland (GDI-DE) und der Geodateninfrastruktur Baden-Württemberg (GDI-BW) definiert. Dabei sind die IT-Komponenten auf Basis einer Serviceorientierten Architektur (SOA) über standardisierte Geodatendienste (3-Ebenen-Architektur) zu verbinden.

Die in der Architektur der GDI-DE (www.geoportal.de) nach Verbindlichkeit klassifizierten IT-Standards sind nach Maßgabe der Gesamtkonzeption GDI-BW (www.geoportal-bw.de) von den öffentlichen und privaten Stellen in Baden-Württemberg zu berücksichtigen; diese Standards haben zur Gewährleistung der bundesweiten Interoperabilität grundsätzlich Vorrang vor der Entwicklung landesspezifischer Standards.

Darüber hinaus legen die Ressorts bei Bedarf weitere, zur Erledigung ihrer Fachaufgaben notwendige, fachdomänenspezifische Regelungen für die Bereiche Geodaten, Geodienste und Geo-Anwendungen fest.

**2.2 Georeferenzierung, Koordinatenreferenzsysteme**

Zur Gewährleistung der Interoperabilität von Geodaten verschiedener Herkunft bedarf es der Festlegung einheitlicher raumbezogener Referenzsysteme (Georeferenzierung nach ISO 19111, 19112).

In Baden-Württemberg sind anzuwenden:

- a) Nationales geodätisches Koordinatenreferenzsystem (3D, 2D - Lage): Das Europäische Terrestrische Referenzsystem 1989 (ETRS89) in der Realisierung 2016, in der 2D-Abbildung mit der Universalen Transversalen Mercatorprojektion (UTM).
- b) Nationales Höhenreferenzsystem: Das Deutsche Haupthöhennetz 2016 (DHHN2016) als amtliches Höhenreferenzsystem.
- c) INSPIRE-Referenzsysteme: Für Geodaten, die in nach Maßgabe des Landesgeodatenzugangsgesetzes (LGeoZG) im Rahmen von INSPIRE bereitzustellen sind, sind anzuwenden:
  - als geodätisches Koordinatenreferenzsystem: ETRS89, in der 2D-Abbildung mit Geographischen Koordinaten (Länge, Breite), Zonenweise Transversale Mercatorprojektion, Lambert-Flächentreue Azimutalprojektion, Lambertsche Schnittkegelprojektion
  - als Höhenreferenzsystem: Das Europäische Höhenreferenzsystem (European Vertical Reference System, EVRS) in der Realisierung 2007, ellipsoidischen Höhen bezogen auf ETRS89 (GRS80).

Soweit die Geodaten nicht bereits in den geforderten INSPIRE-Referenzsystemen erfasst und geführt werden, sind bei der Bereitstellung der Geodaten im Rahmen INSPIRE jeweils Koordinatentransformationen auszuführen.

Für die Transformation von GK-Koordinaten nach ETRS89/UTM ist bei (Fach-)Daten die auf ALKIS-Daten basieren, die Transformationsdatei BWTA2017 zu verwenden. Bei (Fach-)Daten die auf ATKIS-Daten basieren, ist die Transformationsdatei Beta2007 zu verwenden.

Referenzsystem geographischer Identifikatoren: Verwendung der Geobasisdaten als Gazetteer-Quelle (Ortsverzeichnis) mit geographischen Identifikatoren zur Herstellung des direkten Raumbezugs bei indirekt georeferenzierten Geofachdaten (Geokodierung)

**2.3 Geodaten, Austausch- und Bereitstellungsformate**

Zur Gewährleistung der Interoperabilität von Geodaten verschiedener Herkunft bedarf es der Festlegung einheitlicher Datenmodelle und Austauschformate. Die Architektur der GDI-DE benennt im Einzelnen die nach ihrer Verbindlichkeit klassifizierten IT-Standards für Datenmodelle und Austauschformate.

Insbesondere sind in Baden-Württemberg anzuwenden:

INSPIRE

- Die von INSPIRE vorgegebenen INSPIRE-Datenmodelle sind bei der Bereitstellung von unter das Landesgeodatenzugangsgesetz (LGeoZG) fallenden Geodaten verpflichtend anzuwenden.

Geobasisdaten des Liegenschaftskatasters und der Landesvermessung

- Bei der Bereitstellung von Geobasisdaten des Liegenschaftskatasters und der Landesvermessung sind grundsätzlich die Empfehlungen der Arbeitsgemeinschaft der Vermessungsverwaltungen der Länder der Bundesrepublik Deutschland (AdV; http://www.adv-online.de/AdV-Produkte/Standards-und-Produktblaetter/) sowie die "Dokumentation zur Modellierung der Geoinformationen des amtlichen Vermessungswesens" (GeoInfoDok, Das AFIS-ALKIS-ATKIS-Datenmodell ist zu beachten.

Austausch- und Bereitstellungsformate

- Als Austauschformat ist im Rahmen von INSPIRE insbesondere die Geography Markup Language (GML) anzuwenden, weitere Austauschformate sind festgelegt.
- Die Austausch- und Bereitstellungsformate werden von der AdV zur bundesweit einheitlichen Anwendung beschlossen.
- Als Austauschformat für Geobasisdaten ist die auf Grundlage der Geography Markup Language (GML) basierende bundesweit einheitliche "Normbasierte Austauschschnittstelle" (NAS) anzuwenden. Weitere (inhaltlich reduzierte) Austauschformate für Geobasisdaten werden nach Bedarf angeboten.
- Als weiteres Austauschformat für die unabhängige und nutzerorientierte Bereitstellung von Geobasisdaten wird das GeoPackage (GPKG) des Open Geospatial Consortiums (OGC) als quelloffenes Format eingesetzt, um Geodaten zu speichern, zu verwalten und auszutauschen.
- Sofern die Geodaten zu den hochwertigen Datensätzen nach Datennutzungsgesetz zählen, ist deren Nutzung in maschinenlesbarem Format über geeignete Anwendungsprogrammierschnittstellen und, falls technisch erforderlich, als Massen-Download zu ermöglichen; die Anwendungsprogrammierschnittstellen werden über standardisierte Geodatendienste (Nr. 2.6) realisiert.

**2.4 Metadaten zu Geodaten, Geodatendiensten und Geoanwendungen**

Metadaten enthalten beschreibende Informationen über die Eigenschaften von Geodaten und Geodatendiensten. Zur Gewährleistung der Interoperabilität von Metadaten verschiedener Herkunft und ihrer Zusammenführung im Metadatenkatalog GDI-BW bedarf es der Festlegung einheitlicher Datenmodelle und Austauschformate. Die Architektur der GDI-DE benennt im Einzelnen die nach ihrer Verbindlichkeit klassifizierten IT-Standards für Datenmodelle und Austauschformate. In Baden-Württemberg sind anzuwenden:

Das Datenmodell für Metadaten zu Geodaten und Geodatendiensten richtet sich nach der ISO 19115, 19119 in der Ausprägung des Metadatenprofils GDI-BW in der geltenden Fassung (www.geoportal-bw.de) und hinsichtlich des Austauchformats nach ISO 19139.

Für die Geodaten und Geodatendienste nach dem Landesgeodatenzugangsgesetz sind Metadaten zu erfassen.

**2.5 Überführung von Metadaten der Geodateninfrastruktur in Open Data-Portale**

Der IT-Planungsrat hat DCAT-AP.de als formalen Metadatenstandard für allgemeine, offene Verwaltungsdaten festgelegt. Das bedeutet, dass die Informationen über Geo-Ressourcen, die unter Open Data fallen und mit entsprechenden Lizenz- bzw. Nutzungsbedingungen versehen sind, ebenfalls in Strukturen gem. DCAT-AP.de zu dokumentieren sind. Zur Vermeidung von Doppelerfassung bei Metadaten werden die ISO-basierten Metadaten im Metadatenprofil der GDI-BW gemäß einem abgestimmten Mapping vollautomatisch in die Struktur von DCAT-AP.de überführt. Dies erfolgt, wenn in den Metadaten der Geodateninfrastruktur folgende Bedingungen erfüllt sind:

1. In den Schlüsselwörtern muss der Begriff "opendata" hinterlegt sein
2. Angaben zur Lizenz müssen hinterlegt sein
3. In den Metadaten muss eine Verlinkung zum Datensatz existieren, entweder durch Daten-Dienste-Kopplung durch direkten Link zum Download des Datensatzes

**2.6 Geodatendienste**

Zur Gewährleistung der Interoperabilität von Geodaten (und Metadaten) verschiedener Herkunft bedarf es der Festlegung einheitlicher Geodatendienste, die Geodaten (und Metadaten) übermitteln und verarbeiten. Die Architektur der GDI-DE benennt im Einzelnen die nach ihrer Verbindlichkeit klassifizierten IT-Standards für Geodatendienste und deren Spezifikation.

Insbesondere sind in Baden-Württemberg anzuwenden:

- Suchdienste: Catalogue Service for Web (CSW)
- Darstellungsdienste: Web Map Service (WMS), Web Map Tiling Service (WMTS)
- Downloaddienste: Web Feature Service (WFS), Web Feature Service - Transactional (WFS-T), Web Coverage Service (WCS), ATOM-Feed
- OGC API-Features, VectorTiles
- Weitere Geodatendienste (gemäß Architektur der GDI-DE), insbesondere Prozessierungsdienste
- Geoanwendungen

Geodaten und Geodatendienste der öffentlichen Verwaltung sind nach Maßgabe von § 10 Abs. 1 LGeoZG zentral über das Geoportal Baden-Württemberg (www.geoportal-bw.de) (den berechtigten Nutzern) zugänglich zu machen.

Metadaten zu Geodaten und Geodatendiensten der öffentlichen Verwaltung sind im Metadatenkatalog GDI-BW als zentraler Landesknoten zu führen; der Metadatenkatalog GDI-BW bildet die Grundlage für das Geoportal BW und die nationalen (und europäischen) Metadatenkataloge von GDI-DE und INSPIRE.

Eine Vielzahl dezentraler Geoanwendungen (Citrix-, Desktop-, Weblösungen) mit teilweise mobilen Komponenten ist in den Fachverfahren im Einsatz. Beim Redesign von Geoanwendungen sollen Geodaten über die standardisierten Geodatendienste eingebunden werden, so dass redundante Datenhaltung und aufwändige Aktualisierungsmechanismen auf das erforderliche Maß reduziert werden können, sofern dies keine Performance- oder Kapazitätseinbußen für andere Verfahren nach sich zieht.

Auch Geoanwendungen sind mit Metadaten zu beschreiben.

### 3 Nutzung vorgegebener Entwicklungslinien (zu Nr. 5.1, 5.4, 8 VwV IT-Standards)

Die nachfolgend aufgeführten Entwicklungslinien gelten für landeseigene Entwicklungsvorhaben, die keine speziellen Anforderungen an die Programmiersprache stellen und die nicht innerhalb länderübergreifender Kooperationen stattfinden. Ausgangspunkt einer Entwicklungslinie ist die für eine bestimmte Anwendungsklasse vorgesehene Programmiersprache, die zusammen mit einer CI-/CD-Umgebung den Technologieeinsatz der Build- und Deployment-Kette definiert.

**3.1 Anwendungsklassen und Programmiersprachen**

Anwendungsentwicklungen mit der Programmiersprache Java sollten grundsätzlich eine freie Java-Implementierung basierend auf den Open Source Code des Open Java Development Kit (OpenJDK) verwenden. Grundsätzlich müssen hierfür LTS (Long Term Support)-Versionen verwendet werden. Vorrangig ist hier die freie Java-Implementierung Azul Zulu einzusetzen.

**3.1.1 Anwendungsklasse: Portal / Web-Site**

Einsatzgebiet: Zugang zu Informationen und (IT-) Dienstleistungen für Mitarbeitende, Bürgerinnen und Bürger und Wirtschaft

Bemerkung: Portale beziehungsweise eingesetzte Portal-Standardprodukte können die Grundlage für weiterführende Web-Anwendungen sein, welche die durch ein Portal zur Verfügung gestellten Dienste und/oder Frameworks nutzen.

Programmiersprachen:

- Für diese Anwendungsklasse sollte keine weiterreichende Softwareentwicklung im eigentlichen Sinne durchgeführt werden. Zum Einsatz kommen gegebenenfalls produktabhängige (Script-)Sprachen zur erweiterten Konfiguration oder Anpassung.
- Als Produkte zur Umsetzung von Web-Sites / Portalen sind zu nutzen: Liferay, Pirobase, TYPO3, Plone. Die Systeme Microsoft SharePoint, WordPress sowie OpenCMS werden aus Investitionsschutzgründen akzeptiert.
- Weitergehende Entwicklungen sind als Anwendungsklasse "Web-Anwendung" zu sehen - siehe entsprechende Anwendungsklasse.

**3.1.2 Anwendungsklasse: Web-Anwendung**

Einsatzgebiet: IT-Anwendung für Mitarbeitende sowie Bürgerinnen und Bürger und Wirtschaft, zugreifbar über einen Web-Browser

Bemerkung: Technologisch können die meisten UI-basierten IT-Anwendungen als Web-Anwendungen umgesetzt werden. Dies bietet einen Vorteil hinsichtlich eines einheitlichen und effizienten Entwicklungsvorgehen und Betriebs. Dazu zählen auch moderne "progressive Web Apps" die zahlreiche Merkmale von nativen (Mobil-/Desktop-)Anwendungen besitzen (inklusive Offline-Fähigkeiten).

Programmiersprachen: Als Programmiersprachen sind zu nutzen: Java, Groovy, JavaScript, TypeScript, PHP, Python

Frameworks: Als Frameworks sind bevorzugt zu nutzen: Spring Boot, React und Angular

**3.1.3 Anwendungsklasse: Desktop-Anwendung**

Einsatzgebiet: Auf Endgeräten installierte IT-Anwendung (Standalone- oder Client-Komponente)

Bemerkung: Neue oder maßgeblich technologisch aktualisierte Desktop-Anwendungen sollten als Web-Anwendung realisiert werden. Desktop-Anwendungen sind somit plattformunabhängig zu entwickeln, so dass sie nicht an die Nutzung eines bestimmten Betriebssystems gebunden sind.

Programmiersprachen: Als Programmiersprachen sind zu nutzen: Java, C#

**3.1.4 Anwendungsklasse: Server-seitige Anwendung**

Einsatzgebiet: Server-basierte Anwendung

Bemerkung: Backend-Logik, die über zentrale Server-Komponenten bereitgestellt wird

Programmiersprachen:

- Java
- Groovy
- Python
- JavaScript

Nicht strategisch, jedoch für größere Redesigns mittelfristig noch zulässig sind Cobol und Natural.

**3.1.5 Anwendungsklasse: Batch-Anwendung**

Einsatzgebiet: Stapelverarbeitung

Bemerkung: Nicht-interaktive Anwendung zur Massendatenverarbeitung, die zu fest vorgegebenen Zeitpunkten läuft.

Programmiersprachen: Java, Cobol, Python

**3.1.6 Anwendungsklasse: Mobil-Anwendung**

Einsatzgebiet: Spezialisierte Anwendungen für den mobilen Einsatz (Smartphone, Tablet)

Bemerkung: Hierbei ist zu prüfen, ob die Funktionalität notwendigerweise als native oder aber auch durch eine entsprechende Web-, Hybrid- oder "progressive Web Anwendung" umgesetzt werden kann.

Programmiersprachen:

- Vorzugweise als Web-Anwendung zu realisieren.
- Bei begründeter Notwendigkeit einer nativen Mobil-Anwendung und Freigabe durch das Architekturmanagement kommen die entsprechenden Programmiersprachen wie beispielsweise Kotlin der relevanten Mobil-Plattformen zum Einsatz.

Frameworks: Bevorzugte Frameworks sind Ionic und React-Native

**3.1.7 Anwendungsklasse: Data Warehouse (Anwendung)**

Einsatzgebiet: Analyse von Datenbeständen

Bemerkung: Analyse von Daten aus verteilten und unterschiedlich strukturierten Datenbeständen beziehungsweise zur Separation spezifischer Daten, die für das operative Geschäft oder Entscheidungen benötigt werden. Für diese Anwendungsklasse werden i. d. R. entsprechende DWH-Softwareprodukte eingesetzt.

Programmiersprachen: Eine "Entwicklung" findet gegebenenfalls im Rahmen der Umsetzung des ETL-Prozesses (Extract-Transform-Load) statt. Hierzu kommen DWH-spezifische Produkte oder Entwicklungswerkzeuge beziehungsweise zugehörige Programmiersprachen zum Einsatz.

**3.2 Entwicklungslinien**

Zur Durchführung und Automatisierung des Entwicklungsprozesses sowie zur Optimierung der Entwicklungsaufgaben sind folgende standardisierte Entwicklungslinien und Werkzeuge verwendbar. Für Programmiersprachen, für die keine Entwicklungslinie definiert ist, werden gegebenenfalls zukünftig standardisierte Entwicklungslinien definiert.

**3.2.1 Entwicklungslinien Java SE, JakartaEE, Javascript, Typescript:**

IDE:

- Eclipse
- IntelliJ IDEA
- WebStorm für Javascript
- Visual Studio Code

CASE-Tools:

- Enterprise Architect
- PlantUML
- Magic Draw
- Archi

Versionskontrolle:

- Subversion
- Git

Continuous Integration:

- Jenkins
- GitLab

Build-Management:

- Maven
- Gradle
- WebPack
- gulp.js

Build-/Component-Repository:

- Nexus Repository

Konfigurations-Management:

- Ansible
- Chef
- Puppet
- Helm
- Kustomize

Code Metrics:

- SonarQube
- JSLint (und Derivate wie zum Beispiel JSHint) für Javascript

Testautomation:

- JMeter
- JUnit
- TestNG
- QF-Test
- Selenium
- SoapUI
- Axe
- Mokito
- Jest
- Gatling

Monitoring / Reporting:

- Elasticsearch, Logstash und Kibana (ELK-Stack)
- Grafana Tools

Supply Chain Management:

- Dependency Track

Vorgangsmanagement:

- Jira

REST-APIs:

- bevorzugt mit Java auf Spring Boot zu realisieren
- alternativ mit Javascript auf NodeJS
- OpenAPI (Swagger)
- Red Hat Quarkus

Abweichungen von den beschriebenen Entwicklungslinien sind, sofern nicht explizit anders benannt, gegenüber der IT-Landesarchitektin oder dem IT-Landesarchitekten zu begründen. Mittelfristig ist eine Konsolidierung auf die genannten Produkte vorgesehen.

**3.2.2 Low-Code-Entwicklungsplattformen**

Für die Entwicklung produktiver Anwendungssysteme sind Low-Code-Plattformen grundsätzlich zulässig. Hierbei ist insbesondere auf eine der geplanten Lebensdauer der Anwendung entsprechende Wartbarkeit sowie auf die Vermeidung von Herstellerabhängigkeiten zu achten. Low-Code-Entwicklungsplattformen, die keinen herstellerunabhängig compilierbaren bzw. interpretierbaren Quellcode produzieren, dürfen ausschließlich in Abstimmung mit der für die IT-Landesarchitektur beauftragten Person eingesetzt werden.

**3.2.3 No-Code-Entwicklungsplattformen**

Für No-Code-Plattformen, mit Erweiterungsmöglichkeiten hinsichtlich Low-Code, gilt Nummer 3.2.2. Die Verwendung von reinen No-Code-Plattformen für zentral gehostete Client-Server-Anwendungen ist nicht erlaubt. Hingegen sind Entwicklungen für nicht zentral gehostete Client-Server-Anwendungen gestattet.

**3.2.4 Container-Plattformen**

Für die Entwicklung und das Deployment von neuen Fachanwendungen der Anwendungsklassen nach Nummer 3.1.1 und 3.1.2 müssen Container-Technologien bzw. -Plattformen eingesetzt werden. Dabei sind für die Containerschicht der Industriestandard Docker bzw. OCI-kompatible (Open Container-Initiative) Technologien zu verwenden. Die Orchestrierung erfolgt über den Industriestandard Kubernetes.

## Anlage 2: Architekturmanagement und IT-Projektmanagement (zu Nummer 3.18, 9)

### 1 Architekturmanagementprozess zur Festlegung und Überwachung der Architekturvorgaben (zu Nr. 3.18 VwV IT-Standards)

**1.1 Architekturboard**

Das Architekturboard initiiert und führt folgende Aktivitäten durch:

**1.1.1 Erstellung und Fortschreibung der Architekturvorgaben, Referenzarchitekturen und IT-Standards, verpflichtend zu nutzenden Anwendungssysteme und Basissysteme**

Im Rahmen der Architekturboard-Sitzungen wird die Erstellung und stetige Fortschreibung der Architekturvorgaben, Referenzarchitekturen, verpflichtend zu nutzenden Anwendungssysteme und Basissysteme und zugehörigen IT-Standards abgestimmt.

**1.1.2 Sicherstellung und Überprüfung der Einhaltung der Architekturvorgaben**

Zwingende Voraussetzung für das Erreichen der strategischen IT-Ziele ist die konsequente landesweite Umsetzung der Architekturvorgaben sowie die Sicherstellung deren Einhaltung. Hierzu erforderliche Maßnahmen müssen daher folgende Handlungsfelder berücksichtigen:

- Erkennung von Abweichungen von den Architekturvorgaben und IT-Standards,
- Regelung gegebenenfalls notwendiger Ausnahmen beziehungsweise Initiierung einer entsprechenden Architekturanpassung und somit
- Herstellung einer Planungssicherheit für Projekte und Fachverfahren sowie
- Identifikation von Änderungs- oder Erweiterungsbedarfen der bestehenden Architekturvorgaben und IT-Standards

**1.1.3 Umsetzungsberatung der Architekturvorgaben in IT-Vorhaben**

Transparenz über die Architekturvorgaben und die damit verbundene Intension ist eine wesentliche Voraussetzung für die Akzeptanz und somit auch für deren Anwendung bei der Realisierung neuer IT-Vorhaben. Während der Planung und Umsetzung neuer IT-Vorhaben lassen sich gegebenenfalls aufgrund technischer Randbedingungen bspw. durch länderübergreifende Kooperationsvorhaben oder aufgrund anderer Faktoren einzelne Vorgaben nicht konsequent umsetzen. In diesen Fällen ist eine detaillierte Betrachtung und Entscheidung durch das Architekturboard in Zusammenarbeit mit der für das Vorhaben verantwortlichen Person und der jeweiligen für die Systemarchitektur zuständigen Person erforderlich.

**1.2 Am Architekturmanagementprozess beteiligte Rollen und deren Aufgaben**

**1.2.1 Die oder der Landesbeauftragte für Informationstechnologie (CIO)**

Die oder der CIO liefert im Rahmen der IT-Strategie die Grundlagen für die Erstellung und Fortschreibung der IT-Standards sowie der Architekturvorgaben. Die IT-Standards und Architekturvorgaben sind stets auf die strategischen Ziele der Landesverwaltung auszurichten. Zur Wahrnehmung der strategischen und operativen Aufgaben zur Planung und Steuerung der Landes-IT setzt die oder der CIO unter anderem das Architekturboard ein.

**1.2.2 Die IT-Landesarchitektin oder der IT-Landesarchitekt**

Die IT-Landesarchitektin oder der IT-Landesarchitekt plant und steuert die IT-Architektur der Landesverwaltung. Sie oder er initiiert und koordiniert die ressortübergreifende Entwicklung und Fortschreibung der Architekturvorgaben sowie die Einrichtung einer einheitlichen IT-Governance. Durch die für die IT-Landesarchitektur zuständige Person werden die IT-strategischen Punkte der oder des CIO in die Beratungsarbeit des Architekturboards eingebracht und in den Entwürfen entsprechend berücksichtigt. Sie etabliert geeignete Prozesse zur Sicherstellung der landesübergreifenden Architektur-Compliance. Als Vertreterin des Architekturboards informiert sie regelmäßig die oder den CIO sowie den AK-IT über den Stand der Umsetzung der VwV IT-Standards. Die für die IT-Landesarchitektur zuständige Person trifft im Benehmen mit dem Architekturboard als Vertreterin der oder des CIO übergreifende Architekturentscheidungen, falls zum Beispiel eine etwaige Ausnahmeregelung der IT-Strategie des Landes zuwiderlaufen würde.

**1.2.3 Die Domänenarchitektin oder der Domänenarchitekt (für fachliche Domänen beziehungsweise technische Domänen)**

In der ihr oder ihm zugeordneten fachlichen- oder technischen Domäne setzt die Domänenarchitektin oder der Domänenarchitekt die VwV IT-Standards um. Sie oder er ist verpflichtet, die kontinuierliche Einhaltung der entsprechenden Architekturvorgaben und IT-Standards sicherzustellen.

Bei Abweichungen und Sonderfällen, für die eine umfassende Anwendung der VwV IT-Standards nicht möglich (oder unverhältnismäßig aufwendig) sein sollte, muss dies der IT-Landesarchitektin oder dem IT-Landesarchitekten vorgetragen werden, um eine Lösung oder Ausnahmeregelung (für einzelne spezifische Vorgaben oder IT-Standards) zu erwirken.

Die Rolle der Domänenarchitektin oder des Domänenarchitekten ist dem für die entsprechende Domäne verantwortlichen Entwicklungsbereich der Ressorts zugeordnet, beziehungsweise bei technischen Domänen können diese auch der BITBW (oder der zuständigen IT dienstleistenden Organisation) zugeordnet sein. Die Domänenarchitektin oder der Domänenarchitekt vertritt die jeweilige Domäne im Architekturboard. Sie oder er ist von den Ressorts zu benennen.

**1.2.4 Die Systemarchitektin oder der Systemarchitekt**

Die Systemarchitektin oder der Systemarchitekt erstellt den softwaretechnischen Entwurf eines Anwendungssystems für konkrete IT-Vorhaben beziehungsweise IT-Projekte einschließlich dessen Abbildung auf eine den zugehörigen funktionalen und nicht-funktionalen Anforderungen angepasste virtuelle beziehungsweise physikalische Umgebung. Sie oder er berät die an der Entwicklung und Durchführung des Vorhabens beteiligten Rollen im Hinblick auf die Umsetzung des Entwurfs bezüglich der Aufwands- und Zeitplanung sowie bezüglich verschiedener Lösungsmöglichkeiten. Sie oder er ist dazu verpflichtet, die Einhaltung der landesweit gültigen Architekturvorgaben und IT-Standards bei der Wahrnehmung ihrer beziehungsweise seiner Aufgaben sicherzustellen und informiert die Domänenarchitektin oder den Domänenarchitekten über Abweichungen und Sonderfälle, für die eine umfassende Anwendung der VwV IT-Standards nicht möglich oder unverhältnismäßig aufwendig sein sollte.

Im Rahmen ihrer oder seiner Aufgaben hinsichtlich Systementwurf und -entwicklung trifft die Systemarchitektin oder der Systemarchitekt Maßnahmen, die die Einhaltung der notwendigen Vorgaben zur Herstellung der Informationssicherheit sicherstellen. Darüber hinaus wirkt sie oder er an der Entwicklung sicherheitsrelevanter Vorgaben mit.

**1.2.5 Die Infrastrukturarchitektin oder der Infrastrukturarchitekt**

Aufgabe der Infrastrukturarchitektin oder des Infrastrukturarchitekten ist die Bereitstellung zentraler IT-Komponenten für den Betrieb von Anwendungssystemen. Hierzu zählen unter anderem Netzinfrastrukturen unter Berücksichtigung der jeweiligen Sicherheitsanforderungen, Hochverfügbarkeitslösungen und Virtualisierungslösungen sowie IT-Basisdienste wie Backup & Recovery, Telefonie, E-Mail und Internet.

**1.2.6 Die Facharchitektin oder der Facharchitekt**

Die Facharchitektin oder der Facharchitekt übernimmt für eine oder mehrere Fachverfahren die Planung und Weiterentwicklung der fachlichen Architektur. Dies schließt die Präzisierung von Kundenanforderungen an die Anwendungsarchitektur ein. Die fachliche Architektur bildet das Bindeglied zwischen Fachbereich und IT. Die Rolle der Facharchitektin oder des Facharchitekten wird im Allgemeinen innerhalb der Fachorganisation der Ressorts wahrgenommen.

**1.2.7 Die Fachkoordinatorin oder der Fachkoordinator**

Die Fachkoordinatorin oder der Fachkoordinator steuert im Zusammenwirken mit den Facharchitekten die Planung und Durchführung der den Geschäftsprozessen zugehörigen fachlichen Bebauung und übernimmt damit einhergehend wesentliche Aufgaben des Anforderungs- und Projektportfoliomanagements. Sie oder er bildet die Schnittstelle zwischen internen Anforderungen der Fachbereiche und der IT. Der Rolle der Fachkoordinatorin oder des Fachkoordinators liegt organisatorisch innerhalb der Fachorganisation der Ressorts.

**1.2.8 Die oder der Produktverantwortliche / die oder der Verfahrensverantwortliche**

Die oder der Produktverantwortliche ist für die Umsetzung anforderungsgerechter Lösungen verantwortlich und berät die Fachbereiche hinsichtlich der Optimierung von Verfahren durch geeigneten Technologieeinsatz. Zu ihren oder seinen Aufgaben zählen unter anderem die Erstellung von Konzepten und Vorgehensweisen für die Weiterentwicklung von Anwendungen einschließlich der Koordination und Durchführung von Maßnahmen zur Qualitätssicherung. Die oder der Produktverantwortliche nimmt ihre oder seine Aufgaben innerhalb der IT-Organisation wahr und bildet die Schnittstelle zur beauftragenden Stelle (Fachbereiche).

### 2 Standards zum Management von IT-Projekten (zu Nr. 9 VwV IT-Standards)

**2.1 Standards zur Bewertung von IT-Vorhaben beziehungsweise IT-Projekten**

IT-Vorhaben und ihre zugehörigen IT-Projekte sind im Hinblick auf ihre Bedeutung für die Landesverwaltung zu bewerten und priorisieren. Die Bewertung erfolgt anhand der Achsen "Strategische Bedeutung", "Realisierungsmöglichkeit", "Dringlichkeit" und "Wirtschaftlichkeit" auf Basis einer Quantifizierung der nachfolgenden Merkmale.

Strategische Bedeutung - Unterstützung der Ziele der Landesverwaltung:

- Unterstützung Landesstrategien: Das Vorhaben / Projekt ist strategisch bedeutsam, da es die Umsetzung eines explizit formulierten Landesziels ermöglicht.
- Unterstützung IT-Strategie: Die Umsetzung eines Vorhabens kann auch dann strategisch bedeutsam sein, wenn sie den in der IT-Strategie formulierten Zielen (und somit auch den Landeszielen) dient.
- Eröffnung neuer Handlungsräume: Die Umsetzung ist deshalb strategisch bedeutsam, weil sie der Landesverwaltung neue Handlungsräume eröffnet.
- Bereitstellung von Daten für die Steuerung der Landesverwaltung: Die Umsetzung ist strategisch bedeutsam, weil dadurch für die Steuerung innerhalb der Landesverwaltung wesentliche Informationen und Werkzeuge bereitgestellt werden.

Realisierungsmöglichkeit:

- Verfügbarkeit der benötigten Ressourcen für den angestrebten Zeitraum: Ein Vorhaben ist dann leicht umsetzbar, wenn internes Personal für den angepeilten Zeitraum zur Verfügung gestellt werden kann. Dafür ist gegebenenfalls eine Neupriorisierung beziehungsweise eine Zurückstufung anderer Vorhaben nötig.
- Realisierungsmöglichkeit (Erfolgswahrscheinlichkeit, Risiko, Komplexität): Leicht umsetzbar bedeutet, dass erprobte und berechenbare technische Lösungskonzepte zur Verfügung stehen. Schwer umsetzbar bedeutet, dass technisches Neuland betreten wird oder dass ein sehr hoher Aufwand nötig ist. Auch die organisatorische Komplexität eines Vorhabens kann den Erfolg gefährden.

Dringlichkeit:

- Einhaltung Verwaltungsvorschriften, Gesetze: Die Umsetzung ist dringlich, weil Gesetze, Verwaltungsvorschriften oder die Ordnungsgemäßheit von Verfahren nicht mehr eingehalten werden können und Sanktionen drohen beziehungsweise sich daraus andere Nachteile ergeben.
- Drohender Funktionsverlust, Fehler: Eine wichtige Funktion fehlt oder das bisherige System kann sie nicht mehr gewährleisten.

Wirtschaftlichkeit:

- Aufwand des Fachverfahrens vor Durchführung des IT-Vorhabens: Der Aufwand setzt sich aus Personalkosten und sonstigen Kosten (externe Personalkosten, Sachkosten) zusammen.
- Entwicklungs-/Umsetzungsaufwand: Der Aufwand setzt sich aus Personalkosten und sonstigen Kosten (externe Personalkosten, Sachkosten) zusammen.
- Aufwand des Fachverfahrens nach Durchführung des IT-Vorhabens: Der Aufwand setzt sich aus Personalkosten und sonstigen Kosten (externe Personalkosten, Sachkosten) zusammen.

Bei der Bewertung der Wirtschaftlichkeit sind die Vorgaben der LHO - aktuell von § 7 VV-LHO vom 10. Dezember 2009 (GABl. 2009, S. 441), zuletzt geändert durch Verwaltungsvorschrift vom 1. Januar 2015 (GABl. 2015, S. 3) - zu beachten. Für die Planung, Beantragung und Durchführung von IT-Projekten ist der Projektmanagement-Leitfaden zu berücksichtigen.

**2.1.1 Projektbeantragung**

Folgende Angaben sollte die Projektbeschreibung enthalten:

- Problemstellung / Aktuelles Situation (IST)
- Ziele des Projektes (SOLL)
- Lösungsansatz und mögliche Alternativen
- Bezug zu anderen Vorhaben / Projekten
- Grobplanung der Arbeitsschritte beziehungsweise bei umfangreichen Projekten Vorgehensweise und Arbeitsplan (inkl. Projektstruktur, Rollen, Zeitplan, Arbeitspakete, Meilensteine)
- Ressourcenübersicht / Kosten
- Notwendigkeit des Projektes
- Wirtschaftlicher Nutzen
- Vertraglich-rechtliche Bindungen
- Risiken

**2.1.2 Projektdurchführung**

Während der Projektdurchführung sind regelmäßig - mindestens quartalsweise - Projektberichte zu erstellen. Diese sollten Aussagen zu folgenden Punkten enthalten:

- Einschätzung bzgl. Einhaltung der Projektziele (Termin, Budget, Arbeitsergebnisse)
- Aktueller Ausgabenstatus
- Inhaltliche Bewertung des Projektstands für den Berichtszeitraum
- Fortschreibung der Risikobewertung
- Darstellung der Entscheidungsbedarfe
- SOLL-IST-Vergleich des Aufwands
- Meilenstein-Trend-Analyse

### Anlage 3: LAN-Konzeption (zu Nummer 7.7)

[PDF](https://www.landesrecht-bw.de/jportal/docs/anlage/vvbw/pdf/VVBW-MID-20241223-01-SF-A003.pdf)
