# Zusammenfassung ergebnis17: Berlin, Tiefenprüfung aller Ortsteile

Dateien: `ergebnis17/lieferung-01.json` bis `lieferung-12.json`, eine Datei je Bezirk. Jede Datei beginnt mit dem Bezirkseintrag, danach folgen die Ortsteile. Das Format entspricht `ergebnis16/test-stufe2.json`, die Tiefenwerte stehen im Feld `stufe2`. Branch: `claude/laughing-sagan-q2wyfw`.

## Umfang

- **12 Bezirkseinträge und 97 Ortsteile.** Berlin hat seit November 2020 97 Ortsteile, nicht 96: Schlachtensee (0608) wurde aus Teilen von Zehlendorf und Nikolassee gebildet. Die Statistik führt alle 97 und sie sind alle enthalten.
- **id:** `berlin-<bezirk>-<ortsteil>`, zum Beispiel `berlin-pankow-prenzlauer-berg`. Bezirke haben `berlin-bezirk-<bezirk>`.
- **name:** „Ortsteil (Bezirk)“.
- **ags:** 11000000. Dazu kommen die Felder `bezirk` und `ortsteil_nr`.
- **Einwohner:** Amt für Statistik Berlin-Brandenburg, Einwohnerregister zum 31.12.2025. Der Stand 30.06.2026 und die Entwicklung seit 31.12.2020 stehen in `stufe2`. Die Summe der Ortsteile stimmt in allen 12 Bezirken genau mit dem Bezirkswert überein.
- **Koordinate:** Schwerpunkt der Ortsteilfläche. Bei Baumschulenweg und Niederschöneweide liegt der Schwerpunkt außerhalb der Fläche, dort ist ein Punkt innerhalb gesetzt und gekennzeichnet. Die Grenzen sind die OpenStreetMap-Grenzen mit amtlichem Ortsteilschlüssel, weil gdi.berlin.de am 19.10.2026 nicht erreichbar war (HTTP 502/503).

## Ampelverteilung je Bezirk (nur Ortsteile)

| Bezirk | Datei | Ortsteile | grün | gelb | rot | unbewertet |
|---|---|---|---|---|---|---|
| Mitte | lieferung-01 | 6 | 0 | 3 | 2 | 1 |
| Friedrichshain-Kreuzberg | lieferung-02 | 2 | 0 | 1 | 1 | 0 |
| Pankow | lieferung-03 | 13 | 0 | 11 | 2 | 0 |
| Charlottenburg-Wilmersdorf | lieferung-04 | 7 | 0 | 4 | 2 | 1 |
| Spandau | lieferung-05 | 9 | 3 | 6 | 0 | 0 |
| Steglitz-Zehlendorf | lieferung-06 | 8 | 0 | 6 | 1 | 1 |
| Tempelhof-Schöneberg | lieferung-07 | 6 | 0 | 6 | 0 | 0 |
| Neukölln | lieferung-08 | 5 | 0 | 4 | 0 | 1 |
| Treptow-Köpenick | lieferung-09 | 15 | 9 | 5 | 1 | 0 |
| Marzahn-Hellersdorf | lieferung-10 | 5 | 2 | 3 | 0 | 0 |
| Lichtenberg | lieferung-11 | 10 | 0 | 9 | 0 | 1 |
| Reinickendorf | lieferung-12 | 11 | 0 | 10 | 1 | 0 |
| **Summe** | | **97** | **14** | **68** | **10** | **5** |

Die 12 Bezirkseinträge sind unbewertet. Grund: Kein Portal hat eine eindeutige Bezirksseite mit Kauf und Miete. immoportal führt keine Bezirksseiten. homeday hat für die sechs Doppelbezirke nur einen Kaufwert. Bei Mitte, Pankow, Spandau, Neukölln, Lichtenberg und Reinickendorf heißen Bezirk und Ortsteil gleich, die Seite lässt sich dort nicht dem Bezirk zuordnen. Der Bezirkseintrag listet in `stufe2` die Ampel aller seiner Ortsteile.

## Regeln

Die Regeln sind dieselben wie in ergebnis14 bis 16, gerechnet mit demselben Programmteil:

- Ausreißer werden nur unter den Portalwerten bestimmt.
- Es gilt die Zwei-Werte-Regel.
- Der Gutachterwert zählt nur ab zwei Portalwerten und bis 40 % Abweichung.
- Ohne Prognose ist die Ampel höchstens gelb.
- Grün erst ab zwei Quellen bei Kauf und bei Miete.

**Gutachterwert:** Immobilienmarktbericht Berlin 2025/2026, Kauffälle 2025, Durchschnitt aller Eigentumswohnungen, S. 61. Der Bericht weist Preise je Altbezirk aus (23 Altbezirke, dazu Grunewald, Schmargendorf, Dahlem und Rummelsburg gesondert), nicht je heutigem Bezirk oder Ortsteil. Jeder Ortsteil bekommt den Wert seines Altbezirks und ist so gekennzeichnet, wie beim bayerischen Kreiswert. Köpenick ist laut Bericht durch Mikroapartments verzerrt (7.134 €/m², ohne diese 5.321 €/m²). Bei allen Köpenicker Ortsteilen fällt der Wert deshalb über die 40-%-Regel heraus.

**Prognose:** Bevölkerungsprognose für Berlin und die Bezirke 2024 bis 2040 (Drs. 19/2765), mittlere Variante, als Bezirkswert. Eine Ortsteilprognose ist nicht veröffentlicht. Eine Prognose bis 2040 mit Basis 2023 gibt es nicht, die aktuelle hat die Basis 2024.

**Mietpreisbremse und Kappung** gelten für ganz Berlin:
- Mietenbegrenzungsverordnung vom 11.11.2025 (GVBl. S. 577), gültig 01.01.2026 bis 31.12.2029.
- Kappungsgrenzenverordnung vom 14.03.2023 (GVBl. S. 122), 15 %, gültig bis 10.05.2028.

## Portalwerte und Ortsprüfung

| Quelle | gewertet | nicht gewertet | kein Wert |
|---|---|---|---|
| homeday Kauf | 94 | 2 | 1 |
| homeday Miete (nur daneben) | 96 | 0 | 1 |
| immoportal Kauf | 34 | 47 | 16 |
| immoportal Miete | 32 | 42 | 23 |
| miet-check Miete | 91 | 0 | 6 |
| miete-aktuell | 0 | 0 | 97 |

- **immoportal:** Hat Ortsteilseiten unter `/berlin/<ortsteil>`. Viele Seiten zeigen aber exakt denselben Wert wie andere Ortsteile, zum Beispiel Friedrichshain und Kreuzberg je 6.134 €/m², Prenzlauer Berg und Pankow 5.974 €/m², Tegel, Konradshöhe, Heiligensee und Märkisches Viertel 4.283 €/m². Solche Werte gelten als nicht ortsteilgenau und sind nicht gewertet, bei beiden Ortsteilen. Das ist der Hauptgrund für die vielen dünnen Datenbasen.
- **homeday:** Hat echte Ortsteilseiten. Nicht gewertet sind Werte gleich dem Berliner Gesamtwert (5.000 €/m²) und Umleitungen auf andere Seiten. Das betrifft Neukölln und Charlottenburg (Gesamtwert) sowie Schlachtensee (Umleitung auf Nikolassee). homeday rundet auf 50 € bzw. 0,1 €, gleiche Werte zwischen Ortsteilen sind dort normal.
- **miet-check:** Die Einzelseiten der Ortsteile sind defekt (0,00 €, „Berlin / Dahme-Spreewald“). Gewertet ist deshalb die Zeile der miet-check-Rangliste der Berliner Stadtteile. Voraussetzung ist, dass sich die PLZ der Zeile mit den PLZ des Ortsteils überschneiden.
- **miete-aktuell:** Hat nur einen Gesamtwert für Berlin. Nach der Regel ist er nicht als Ortsteilwert eingesetzt.
- **Datenbasis dünn:** 69 Ortsteile haben bei Kauf oder Miete nur eine Quelle, die Ampel dort ist höchstens gelb. Rot kann es trotzdem geben, wenn der Faktor über 30 liegt; das betrifft 10 Ortsteile, alle mit dünner Kaufbasis.

## Orte ohne belastbare Werte (unbewertet)

- **Gesundbrunnen** und **Fennpfuhl:** keine gewertete Miete. immoportal fehlt oder ist doppelt, und der Ortsteil fehlt in der miet-check-Rangliste.
- **Charlottenburg** und **Neukölln:** kein gewerteter Kaufwert. immoportal ist doppelt, und die homeday-Seite zeigt nur den Berliner Gesamtwert.
- **Schlachtensee:** kein Portal hat eine eigene Seite für den 2020 neu gebildeten Ortsteil; homeday leitet auf Nikolassee um.

## Wo nur der Bezirkswert genutzt ist

- **Prognose** (Senatsprognose je Bezirk). Sie ist auch Grundlage der Ampel.
- **Leerstand:** Zensus 2022, Bezirkswert. Berlin liegt bei 2,0 %, die Bezirke zwischen 1,4 und 2,4 %.
- **Neubau:** Baugenehmigungen und Fertigstellungen 2025, AfS F II 1 und F II 2.
- **Gutachterwert:** je Altbezirk, siehe oben.
- **Zweckentfremdungsverbot, Umwandlung nach § 250 BauGB, Mietpreisbremse:** gelten stadtweit.

## Tiefenwerte in `stufe2`

- **Einwohner:** Stand 31.12.2025 und 30.06.2026, Entwicklung 31.12.2020 bis 31.12.2025.
- **Mietspiegel:**
  - Aktuell ist der Berliner Mietspiegel 2026 (Stichtag 01.09.2025, Mittelwert 7,71 €/m², qualifiziert). Er ersetzt den Mietspiegel 2024 (7,21 €/m²); beide sind verlinkt.
  - Eine mittlere Wohnlage je Ortsteil ist nicht abgeleitet. Die Wohnlage wird je Adresse vergeben, und die adressgenaue Wohnlagenkarte war nicht erreichbar.
- **Gutachter:** Altbezirkswert mit Kauffällen und Spanne 2025, dazu die Kauffälle je Bezirk. Link: https://www.berlin.de/gutachterausschuss/_assets/amarktinformationen/amarktanalyse/04-03-010-2500.pdf
- **Erhaltungsgebiete (Milieuschutz):**
  - 82 soziale Erhaltungsgebiete laut Straßenliste SenStadt vom 21.02.2026. Die Polygone waren nicht abrufbar.
  - Die Adressen der Straßenliste sind über die Lage der Straßen (OpenStreetMap) den Ortsteilen zugeordnet; 99,7 % der Adressen ließen sich zuordnen.
  - Ein Gebiet steht bei einem Ortsteil, wenn mindestens 10 % seiner Adressen dort liegen.
  - Ergebnis: 33 Ortsteile haben mindestens ein Gebiet. Je Gebiet sind Schlüssel, Name, Anteil und Adressen angegeben.
- **Vorkaufsrecht:** Seit BVerwG 4 C 1.20 nur in Sonderfällen. Der Bundesgesetzentwurf BT-Drs. 21/6588 war bis 19.10.2026 nicht verabschiedet.
- **Umwandlung:**
  - § 250 BauGB stadtweit, 01.01.2026 bis 31.12.2030.
  - In Erhaltungsgebieten zusätzlich die UmwandV 2025 (§ 172 BauGB) für Gebäude bis fünf Wohnungen.
- **Zweckentfremdungsverbot:** Gesetz 2013, Verordnung 2014, ganzes Stadtgebiet, unbefristet.
- **Sozialstruktur:** Monitoring Soziale Stadtentwicklung 2025 (Stand 31.12.2024). Statusklassen der Planungsräume mit Schwerpunkt im Ortsteil, als Anzahl und als Einwohneranteil. Schlachtensee und Malchow haben keinen Planungsraum-Schwerpunkt.
- **ÖPNV:** U- und S-Bahnhöfe im Ortsteil laut VBB-GTFS vom 15.10.2026.
  - 36 Ortsteile haben U-Bahn, 61 haben S-Bahn, 29 haben keinen Schnellbahnhof.
  - Die U6 nördlich Kurt-Schumacher-Platz fährt laut Fahrplan derzeit nur als Ersatzverkehr; die fünf Bahnhöfe stehen trotzdem in der Liste und sind gekennzeichnet.
- **Hochschulen:**
  - Hauptsitz und Studierende im Wintersemester 2024/25 (AfS B III 1), zugeordnet über die Adresse. Das betrifft 13 Ortsteile.
  - SRH, UE, IU und FOM haben ihren Hauptsitz außerhalb Berlins und sind nicht zugeordnet.
- **Arbeitgeber:** Nur Wikipedia-Sätze mit Firma und Beschäftigtenzahl am Ort.
  - Gefunden: Wedding mit dem Jüdischen Krankenhaus (rund 840) und dem BVG-Betriebshof Müllerstraße (437 Fahrdienst), Schmargendorf mit dem Cornelsen Verlag (rund 650).
  - Sonst ist das Feld leer, mit Grund.
- **Zusatzeinschätzung:** Milieuschutz (Aufteilungs- und Umwandlungsvorbehalt) und Sozialstruktur stehen als Text getrennt von der Ampel. Sie fließen nicht in die Ampel ein.

## Quellenlücken

- gdi.berlin.de war nicht erreichbar, deshalb fehlen: amtliche ALKIS-Grenzen (ersetzt durch OpenStreetMap), Polygone der Erhaltungsgebiete (ersetzt durch die Straßenliste) und Wohnlagenkarte.
- Kein amtlicher Gutachterpreis je heutigem Bezirk oder Ortsteil, nur je Altbezirk.
- Keine Ortsteilprognose, kein Leerstand je Ortsteil.
- immoportal liefert in vielen Ortsteilen keinen ortsteilgenauen Wert. miete-aktuell hat keine Ortsteilseiten.
