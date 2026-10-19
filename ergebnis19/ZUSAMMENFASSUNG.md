# Zusammenfassung ergebnis19: Freiburger Umland, Ausbau in Tiefe und Breite

Branch: `claude/laughing-sagan-q2wyfw`. Die drei Teile stehen in getrennten Dateien.

Regeln wie ergebnis14 bis 16:
- Ausreißer werden nur unter den Portalwerten bestimmt.
- Es gilt die Zwei-Werte-Regel.
- Der Gutachterwert zählt erst ab zwei Portalwerten und bis 40 % Abweichung.
- Ohne Prognose ist die Ampel höchstens gelb.
- Strenge Ortsprüfung.

Mietpreisbremse: MietBegrenzVO BW vom 16.12.2025 (GBl. 2025 Nr. 144), Abgleich über den Gemeindeschlüssel.

Prognose:
- GENESIS-Online BW brach am 19.10.2026 bei jedem Abruf mit Server-Timeout ab.
- Wie für ergebnis20 freigegeben, ist deshalb Bertelsmann Wegweiser Kommune 2020 bis 2040 als Ersatzquelle genutzt; das ist je Ort vermerkt.
- Wegweiser führt nur Gemeinden ab 5.000 Einwohnern. Kleinere Gemeinden haben keine Prognose und sind daher höchstens gelb.

## Teil 1: 25 fehlende Gemeinden (`teil1-01.json`)

Die Liste im Auftrag enthält 25 Schlüssel, nicht 29. Ehrenkirchen, Schallstadt, Ebringen und Pfaffenweiler sind wie gewünscht nicht erneut bewertet; sie stehen in ergebnis16, inzwischen mit Nachlieferung der BW-Prognose. Keine der 25 Gemeinden kam in früheren Lieferungen vor.

| Landkreis | Orte | Ampel |
|---|---|---|
| Breisgau-Hochschwarzwald | 6 | gelb 5, unbewertet 1 |
| Ortenaukreis | 8 | grün 5, gelb 3 |
| Lörrach | 5 | gelb 5 |
| Emmendingen | 5 | gelb 4, unbewertet 1 |
| Waldshut | 1 | gelb 1 |
| **Summe** | **25** | **gelb 18, grün 5, unbewertet 2** |

### Ohne belastbare Werte (unbewertet)

Müllheim im Markgräflerland, Rheinhausen im Breisgau. Grund: keine gewertete Miete. Der Wert ist leer gelassen, nichts ist aus Nachbarorten eingesetzt.

### Ohne Prognose

18 Gemeinden unter 5.000 Einwohnern haben keine Prognose: Bad Bellingen, Stegen, Rheinhausen im Breisgau, Freiamt, Meißenheim, Riegel am Kaiserstuhl, Biberach, Sasbach am Kaiserstuhl, Malterdingen, Gottenheim, Eisenbach (Hochschwarzwald), Hofstetten, Wittnau, Malsburg-Marzell, Wutach, Häg-Ehrsberg, Utzenfeld, Wembach. Ein Wiederholungsabruf bei GENESIS läuft. Gelingt er, liefere ich diese Gemeinden nach.

### Mietpreisbremse

- Fast alle Gemeinden aus Breisgau-Hochschwarzwald, Emmendingen und Lörrach stehen auf der BW-Liste, auch sehr kleine wie Utzenfeld und Wembach. Das ist am Verordnungstext geprüft.
- Nicht gelistet sind Müllheim, Biberach und Hofstetten.

## Teil 2: Stadtteile von Freiburg (`teil2-freiburg-01.json`)

Freiburg hat 28 amtliche Stadtteile mit 42 Stadtbezirken (Geodaten der Stadt). Angelegt sind die 21 Stadtteile, die bei immoportal oder homeday eine eigene, stadtteilgenaue Seite haben.

Nicht angelegt, weil es keine eigene stadtteilgenaue Portalseite gibt: Herdern, Brühl, Waltershofen, Mundenhof, St. Georgen, Opfingen, Munzingen.
- Herdern und Brühl haben bei immoportal denselben Wert (5.597 €/m²), also ist der Ortsbezug unklar.
- St. Georgen: Die immoportal-Seite zeigt denselben Wert wie Haslach, und ihr Seitentitel nennt den Stadtteil nicht.
- Waltershofen, Opfingen und Munzingen: Es gibt keine immoportal-Seite, und homeday zeigt nur den Stadtwert (5.100 €/m²).
- Mundenhof (48 Einwohner) wurde an den Portalen nicht abgefragt.

| Stadtteil | Einwohner 31.12.2024 | Kauf | Miete | Ampel | soziale Erhaltungssatzungen |
|---|---|---|---|---|---|
| Altstadt | 7770 | 5986 | 14.36 | rot | 1 |
| Neuburg | 5567 | 6032 | 14.61 | rot | 0 |
| Zähringen | 9441 | 5147 | 15.41 | gelb | 0 |
| Hochdorf | 5308 | 4900 | 14.03 | gelb | 0 |
| Waldsee | 5973 | 5021 | 13.9 | rot | 0 |
| Littenweiler | 8452 | 5009 | 13.96 | gelb | 0 |
| Ebnet | 3010 | 5700 | k. A. | unbewertet | 0 |
| Kappel | 2771 | 4900 | k. A. | unbewertet | 0 |
| Oberau | 6754 | 5459 | 14.38 | rot | 0 |
| Wiehre | 24702 | 5497 | 14.28 | rot | 0 |
| Günterstal | 2165 | 5750 | 14.69 | rot | 0 |
| Stühlinger | 15811 | 5350 | 13.52 | rot | 1 |
| Mooswald | 9513 | 4650 | 14.91 | gelb | 0 |
| Betzenhausen | 15535 | 4250 | 14.33 | gelb | 0 |
| Landwasser | 7264 | 4636 | 15.86 | gelb | 0 |
| Lehen | 2536 | 4650 | 14.75 | gelb | 0 |
| Haslach | 22300 | 4700 | 13.65 | gelb | 2 |
| Tiengen | 3715 | 4381 | 13.8 | gelb | 0 |
| Weingarten | 11765 | 4490 | 13.3 | gelb | 0 |
| Rieselfeld | 9354 | 5643 | 14.0 | rot | 0 |
| Vauban | 5146 | 5463 | 13.35 | rot | 0 |

Ampel Teil 2: gelb 10, rot 9, unbewertet 2.

### Werte und Regeln

- **Portale:**
  - immoportal und homeday je Stadtteilseite.
  - Gleiche Werte wie der Stadtwert, und bei immoportal wie ein anderer Stadtteil, gelten als nicht stadtteilgenau.
  - miet-check über die Freiburger Stadtteil-Rangliste. Nicht gewertet sind Zeilen mit demselben Wert und derselben PLZ-Liste wie ein anderer Stadtteil; das betrifft Littenweiler, Ebnet, Kappel, Rieselfeld.
  - miete-aktuell hat keine Stadtteilseiten.
- **Gutachterwert:**
  - Immobilienmarktbericht 2025, Wiederverkauf Eigentumswohnungen 4.987 €/m², nur als Stadtwert und ohne Tuniberg-Ortschaften und Hochdorf. Er ist wie ein Kreiswert gekennzeichnet und zählt nach der 2-Portalwerte- und 40-%-Regel.
  - Für Hochdorf und Tiengen ist er nicht angesetzt.
  - Stadtteilwerte und Kauffälle stehen nur im kostenpflichtigen Bericht.
- **Prognose:** Für die Ampel gilt der Stadtwert (Wegweiser +3,2 %). In `stufe2` steht zusätzlich die städtische Vorausrechnung je Stadtbezirk von 2024 bis 2034, aus dem Stadtbezirksatlas 2025.
- **Einwohner:**
  - Stadtbezirksatlas 2025, Stichtag 31.12.2024; Vergleich 31.12.2019 aus dem Statistischen Jahrbuch 2024.
  - Werte zum 31.12.2025 je Stadtteil sind nicht veröffentlicht.
  - Rieselfeld wird 2024 nur gemeinsam mit Mundenhof ausgewiesen, deshalb steht dort der Wert vom 31.12.2023.
- **Koordinate:** Schwerpunkt des amtlichen Stadtteilpolygons. Bei Günterstal liegt er außerhalb, dort ist ein Punkt innerhalb gesetzt.
- **Mietspiegel:**
  - Freiburg 2025/2026, qualifiziert, gültig bis 31.12.2026, Durchschnitt 10,81 €/m².
  - Die Wohnlage wird nach Straße und Hausnummer vergeben. Je Stadtteil ist daher der Adressanteil der Lageklassen angegeben, berechnet aus der Lageklassenkarte des Gutachterausschusses.
- **Erhaltungssatzungen:**
  - Fünf soziale Erhaltungssatzungen sind in Kraft: südöstliche Altstadt, St. Georgen Imberyweg, Stühlinger, Haslach (zwei).
  - Zwei sind im Verfahren: Wiehre Quäkerstraße, Brühl/Zähringen.
  - In Erhaltungsgebieten gilt der Umwandlungsvorbehalt nach Landesverordnung bis 18.11.2028.
- **Zweckentfremdungssatzung** vom 28.11.2023, in Kraft seit 01.02.2024 für fünf Jahre, ganzes Stadtgebiet.
- **ÖPNV:** Stadtbahnhaltestellen und Bahnhöfe je Stadtteil aus dem VAG- und DELFI-GTFS.
- **Hochschulen:** Universität (Neuburg), PH (Littenweiler), Musikhochschule (Oberau), Katholische Hochschule (Herdern) und Evangelische Hochschule (Weingarten), jeweils mit Studierendenzahl.
- **Arbeitgeber:** Universitätsklinikum mit mehr als 15.000 Beschäftigten, Adresse im Stadtteil Mooswald.
- **Mietpreisbremse:** gilt für Freiburg (BW-Liste).
- **Zusatzeinschätzung:** Milieuschutz ist getrennt von der Ampel ausgewiesen.

## Teil 3: Ortschaften der Umlandstädte (`teil3-ortsteile-01.json`)

Geprüft sind Emmendingen, Lörrach, Offenburg, Lahr, Müllheim, Waldkirch, Bad Krozingen, Staufen, Denzlingen, Breisach, Titisee-Neustadt, Kenzingen und Gundelfingen, je mit ihren Ortschaften.

Eine eigene, ortsgenaue Portalseite haben nur:
- Brombach und Haagen (Lörrach), über immoportal.
- Niederweiler (Müllheim), über homeday.

Alle anderen Ortschaften haben entweder keine Seite, oder homeday zeigt den Wert der Stadt bzw. leitet auf sie um. Deshalb sind sie nicht angelegt.

| Ortsteil | Einwohner | Ampel |
|---|---|---|
| Brombach (Lörrach) | 7033 | gelb |
| Haagen (Lörrach) | 4511 | unbewertet |
| Niederweiler (Müllheim im Markgräflerland) | 1420 | unbewertet |

Einwohner:
- Brombach und Haagen: Stadt Lörrach, Stand 31.12.2025.
- Niederweiler: Meldeamt Müllheim, Stand 31.12.2023.

Koordinaten sind Schwerpunkte der OSM-Ortsteilgrenzen.

Haagen und Niederweiler sind unbewertet, weil es keine ortsgenaue Miete gibt. Brombach ist gelb, weil es nur eine Kaufquelle hat.

## Quellenlücken

- GENESIS-Online BW war nicht abrufbar.
- Der Freiburger Gutachterbericht mit Stadtteilwerten ist kostenpflichtig.
- Für Stadtteile gibt es keine Einwohnerzahlen zum 31.12.2025.
- Die PLZ-Grenzen stammen aus OpenStreetMap.
