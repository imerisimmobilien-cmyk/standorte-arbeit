# Zusammenfassung ergebnis21: Nacharbeit nach der lokalen Stichprobe

Branch: `claude/laughing-sagan-q2wyfw`, kein Pull Request. ergebnis21 enthält nur Patches, also nur geänderte oder neue Einträge im bisherigen Format. Jeder Eintrag hat zusätzlich das Feld `nachtrag21` mit den Werten vorher und den neuen Quellen.

Die Regeln sind unverändert:
- Ausreißer werden nur unter den Portalwerten bestimmt.
- Es gilt die Zwei-Werte-Regel.
- Ohne Prognose ist die Ampel höchstens gelb.
- Strenge Ortsprüfung.

| Datei | Inhalt |
|---|---|
| `patch-ergebnis18-teil1-01.json` | 116 Brandenburger Gemeinden aus ergebnis18 Teil 1 |
| `patch-ergebnis18-teil2-ortsteile-01.json` | 28 Potsdamer Stadtteile: 13 aktualisiert, 15 neu angelegt |
| `patch-ergebnis17-berlin-01.json` | 90 Berliner Ortsteile mit geänderten Werten und die 12 Bezirkseinträge (Ampelliste der Ortsteile aktualisiert) |

## 1. Seiten mit Adresszusatz (ergebnis18)

### Ursachen

1. **miet-check:** Für viele kleine Orte gibt es die Seite, auch mit Zusatz wie `rosenau_bei_wusterwitz`, `golzow_oderbruch` oder `sonnenberg_bei_gransee`. Sie hat aber ein zweites Seitenlayout („Der durchschnittliche Mietpreis liegt 2026 bei 8,23 € pro m²“), das mein Muster nicht las. Die Seite wurde also gefunden, aber als „kein Wert“ verworfen. Das Muster ist jetzt erweitert.
2. **miete-aktuell:** Gleichnamige Orte stehen unter einem Pfad mit Zusatz, zum Beispiel `Ziethen-b.-Eberswalde/Ziethen`, `Mittenwalde-b.-Templin/Mittenwalde`, `Ihlow-b.-Jueterbog/Ihlow`, `Rueckersdorf-b.-Doberlug-Kirchhain/Rueckersdorf`. Mein Abruf hatte nur den Ortsnamen ohne Zusatz genutzt.

### Vorgehen

- Für alle 242 Orte aus ergebnis18 Teil 1 wurden zu jeder fehlenden Quelle Kandidaten mit und ohne Zusatz gesucht:
  - miet-check: Ortsverzeichnis.
  - immoportal: Ortsverzeichnis.
  - miete-aktuell: A-Z-Verzeichnis mit 14.176 Orten.
- Jeder Kandidat lief durch die strenge Ortsprüfung, 231 Kandidaten bei 138 Orten. Gewertet ist nur, was über die PLZ, über den Landkreis oder über Nachbarorte des Landkreises bestätigt ist.
- Nicht übernommen:
  - Wahrenbrück (Ortsteilseite von Uebigau-Wahrenbrück, nur die ersten drei PLZ-Stellen passen).
  - 93 Kandidaten ohne lesbaren Wert, mit falscher PLZ oder ohne eindeutige Bestätigung des Ortes.
- homeday hat kein Ortsverzeichnis. Seiten mit Zusatz ließen sich dort nicht gezielt suchen.

### Ergebnis

- 116 Orte erhalten zusätzliche Quellen und sind mit der unveränderten Pipeline neu gerechnet.
- Ampelwechsel: 23 (gelb zu grün 9, unbewertet zu gelb 7, grün zu gelb 3, rot zu gelb 3, unbewertet zu rot 1). Bei 93 Orten ändern sich nur Kauf oder Miete.
- **Ziethen (12060296)** ist jetzt grün:
  - Vorher gab es nur die Ersatzquelle ohne-makler.net.
  - Neu sind miete-aktuell Kauf und Miete über `Ziethen-b.-Eberswalde` (PLZ exakt) sowie miet-check.
  - Kauf 2.290 €/m², Miete 9,52 €/m², Rendite 5,0 %.
- **Rosenau (12069537)** bleibt grün. Neu ist miet-check `rosenau_bei_wusterwitz` mit 8,23 €/m² (PLZ exakt); die Miete liegt jetzt bei 8,32 €/m².
- **Weitere frühere Lieferungen:** Das miet-check-Layout betrifft wahrscheinlich auch Orte in älteren Lieferungen, nämlich kleine Orte ohne miet-check-Wert. Dort habe ich nicht nachgearbeitet. Das kann bei Bedarf als eigener Patch folgen.

### Ampelwechsel ergebnis18 Teil 1

| Ort | Ampel vorher | Ampel jetzt | Kauf vorher | Kauf jetzt | Miete vorher | Miete jetzt | neue Quellen |
|---|---|---|---|---|---|---|---|
| Mühlenfließ | unbewertet | gelb | 2.400 | 2.400 |  | 10,83 | miet-check Miete |
| Sonnenberg | grün | gelb | 2.861 | 2.861 | 10,32 | 10,05 | miet-check Miete |
| Rabenstein/Fläming | unbewertet | gelb | 1.150 | 1.150 |  | 10,50 | miet-check Miete |
| Drahnsdorf | grün | gelb | 2.138 | 2.138 | 7,64 | 6,79 | miet-check Miete |
| Falkenhagen (Mark) | gelb | grün | 1.672 | 1.672 | 6,59 | 7,28 | miet-check Miete |
| Liepe | gelb | grün | 2.165 | 2.165 | 7,64 | 7,80 | miet-check Miete |
| Niederfinow | gelb | grün | 2.163 | 2.163 | 7,64 | 7,80 | miet-check Miete |
| Parsteinsee | gelb | grün | 2.164 | 2.164 | 7,64 | 7,80 | miet-check Miete |
| Buckautal | grün | gelb | 2.362 | 2.362 | 8,42 | 7,68 | miet-check Miete |
| Fichtenhöhe | gelb | grün | 1.672 | 1.672 | 6,59 | 7,31 | miet-check Miete |
| Ziethen | gelb | grün | 2.349 | 2.290 | 9,68 | 9,52 | miet-check Miete, miete-aktuell Kauf, miete-aktuell Miete |
| Gollenberg | gelb | grün | 1.700 | 1.979 | 6,18 | 7,06 | miet-check Miete, miete-aktuell Kauf, miete-aktuell Miete |
| Brüssow | gelb | grün | 1.715 | 1.715 | 5,60 | 6,42 | miet-check Miete |
| Rückersdorf | unbewertet | gelb |  | 1.979 |  | 6,89 | miet-check Miete, miete-aktuell Kauf, miete-aktuell Miete |
| Märkisch Linden | unbewertet | gelb | 2.100 | 2.100 |  | 8,30 | miet-check Miete |
| Dreetz | gelb | grün | 2.165 | 2.165 | 7,48 | 7,75 | miet-check Miete |
| Pinnow | rot | gelb | 2.584 | 2.407 | 7,16 | 7,79 | miet-check Miete, miete-aktuell Kauf, miete-aktuell Miete |
| Hermsdorf | unbewertet | gelb |  | 1.799 |  | 5,13 | miet-check Miete, miete-aktuell Kauf, miete-aktuell Miete |
| Lanz | rot | gelb | 2.015 | 2.015 | 5,45 | 7,03 | miet-check Miete |
| Schönfeld | unbewertet | gelb |  | 2.268 |  | 7,52 | miet-check Miete, miete-aktuell Kauf, miete-aktuell Miete |
| Rüthnick | rot | gelb | 2.406 | 2.406 | 6,64 | 7,55 | miet-check Miete |
| Lenzerwische | unbewertet | rot | 3.950 | 3.950 |  | 7,87 | miet-check Miete |
| Mittenwalde | unbewertet | gelb |  | 2.480 |  | 9,06 | miet-check Miete, miete-aktuell Kauf, miete-aktuell Miete |

### Ohne Ampelwechsel (nur Kauf oder Miete geändert)

| Ort | Ampel vorher | Ampel jetzt | Kauf vorher | Kauf jetzt | Miete vorher | Miete jetzt | neue Quellen |
|---|---|---|---|---|---|---|---|
| Planebruch | grün | grün | 2.268 | 2.268 | 10,31 | 9,96 | miet-check Miete |
| Neulewin | gelb | gelb | 2.411 | 2.411 | 7,62 | 7,78 | miet-check Miete |
| Straupitz (Spreewald) | rot | rot | 2.542 | 2.542 | 6,32 | 6,80 | miet-check Miete |
| Mixdorf | gelb | gelb | 1.450 | 1.450 | 9,90 | 9,59 | miet-check Miete |
| Linthe | grün | grün | 2.118 | 2.118 | 10,31 | 10,59 | miet-check Miete |
| Planetal | gelb | gelb | 2.900 | 2.900 | 9,62 | 9,28 | miet-check Miete |
| Langewahl | grün | grün | 1.850 | 1.850 | 9,70 | 10,48 | miet-check Miete |
| Rosenau | grün | grün | 1.931 | 1.931 | 7,84 | 8,32 | miet-check Miete |
| Alt Tucheband | gelb | gelb | 1.962 | 1.962 | 5,98 | 6,08 | miet-check Miete |
| Golzow | gelb | gelb | 2.227 | 2.227 | 6,42 | 6,21 | miet-check Miete |
| Wollin | rot | rot | 3.021 | 3.021 | 8,01 | 8,36 | miet-check Miete |
| Friedrichswalde | grün | grün | 2.240 | 2.240 | 10,03 | 9,52 | miet-check Miete |
| Wiesenaue | rot | rot | 2.585 | 2.585 | 6,52 | 6,52 | miet-check Miete |
| Mühlenberge | rot | rot | 2.860 | 2.860 | 6,97 | 6,97 | miet-check Miete |
| Beetzseeheide | gelb | gelb | 2.521 | 2.521 | 8,01 | 8,36 | miet-check Miete |
| Vogelsang | gelb | gelb | 2.007 | 2.007 | 7,06 | 6,99 | miet-check Miete |
| Großwoltersdorf | gelb | gelb | 3.445 | 3.445 | 10,32 | 10,05 | miet-check Miete |
| Lietzen | grün | grün | 1.672 | 1.672 | 6,78 | 7,28 | miet-check Miete |
| Zechin | gelb | gelb | 1.964 | 1.964 | 6,01 | 6,11 | miet-check Miete |
| Ihlow | gelb | gelb | 1.838 | 2.042 | 6,73 | 6,26 | miete-aktuell Kauf, miete-aktuell Miete |
| Schlepzig | gelb | gelb | 2.440 | 2.440 | 7,34 | 8,51 | miet-check Miete |
| Lawitz | gelb | gelb | 1.928 | 1.928 | 5,78 | 6,82 | miet-check Miete |
| Päwesin | rot | rot | 3.196 | 3.196 | 7,94 | 8,28 | miet-check Miete |
| Gräben | rot | rot | 3.088 | 3.088 | 8,06 | 7,86 | miet-check Miete |
| Reitwein | gelb | gelb | 1.450 | 1.450 | 5,88 | 5,98 | miet-check Miete |
| Münchehofe | gelb | gelb | 2.393 | 2.393 | 7,18 | 7,18 | miet-check Miete |
| Dahmetal | rot | rot | 2.773 | 2.773 | 5,91 | 6,38 | miet-check Miete |
| Großderschau | grün | grün | 1.892 | 1.892 | 7,48 | 7,75 | miet-check Miete |
| Spreewaldheide | gelb | gelb | 2.318 | 2.318 | 7,25 | 6,88 | miet-check Miete |
| Schönermark | gelb | gelb | 2.970 | 2.970 | 10,33 | 10,05 | miet-check Miete |
| Rheinsberg | gelb | gelb | 2.466 | 2.572 | 8,21 | 8,21 | immoportal Kauf |
| Heiligengrabe | gelb | gelb | 2.007 | 2.007 | 6,58 | 6,91 | miet-check Miete |
| Röderland | gelb | gelb | 1.595 | 1.595 | 5,92 | 6,21 | miet-check Miete |
| Döbern | rot | rot | 1.000 | 1.000 | 6,89 | 6,31 | miet-check Miete |
| Putlitz | gelb | gelb | 1.400 | 1.400 | 5,55 | 7,48 | miet-check Miete |
| Plessa | rot | rot | 1.602 | 1.602 | 5,58 | 6,70 | miet-check Miete |
| Gartz (Oder) | gelb | gelb | 1.943 | 1.943 | 6,04 | 6,08 | miet-check Miete |
| Meyenburg | gelb | gelb | 905 | 905 | 6,61 | 6,24 | miet-check Miete |
| Ortrand | grün | grün | 1.071 | 1.071 | 6,22 | 7,19 | miet-check Miete |
| Hohenleipisch | rot | rot | 1.622 | 1.622 | 5,28 | 5,63 | miet-check Miete |
| Werben | grün | grün | 3.039 | 3.039 | 11,42 | 10,96 | miet-check Miete |
| Casekow | gelb | gelb | 1.999 | 1.999 | 6,57 | 7,19 | miet-check Miete |
| Jänschwalde | gelb | gelb | 2.174 | 2.174 | 7,93 | 7,70 | miet-check Miete |
| Breese | grün | grün | 1.953 | 1.953 | 7,46 | 7,46 | miet-check Miete |
| Temnitztal | gelb | gelb | 2.100 | 2.100 | 7,02 | 7,29 | miet-check Miete |
| Schönborn | gelb | gelb | 1.200 | 1.200 | 6,18 | 6,21 | miet-check Miete |
| Sallgast | gelb | gelb | 1.658 | 1.658 | 7,04 | 6,89 | miet-check Miete |
| Milmersdorf | gelb | gelb | 2.113 | 2.113 | 9,01 | 9,06 | miet-check Miete |
| Wiesengrund | rot | rot | 1.250 | 1.250 | 6,35 | 6,15 | miet-check Miete |
| Gröden | gelb | gelb | 1.589 | 1.589 | 5,24 | 5,87 | miet-check Miete |
| Hirschfeld | gelb | gelb | 1.883 | 1.883 | 5,38 | 6,03 | miet-check Miete |
| Tschernitz | rot | rot | 1.147 | 1.147 | 6,79 | 7,62 | miet-check Miete |
| Teichland | gelb | gelb | 2.034 | 2.034 | 6,29 | 7,25 | miet-check Miete |
| Großkmehlen | grün | grün | 1.096 | 1.096 | 6,22 | 7,19 | miet-check Miete |
| Weisen | gelb | gelb | 2.166 | 2.166 | 7,46 | 7,46 | miet-check Miete |
| Großthiemig | gelb | gelb | 1.616 | 1.616 | 5,29 | 5,94 | miet-check Miete |
| Hohenbocka | gelb | gelb | 1.972 | 1.972 | 6,03 | 6,93 | miet-check Miete |
| Uckerfelde | gelb | gelb | 2.059 | 2.059 | 7,44 | 7,52 | miet-check Miete |
| Grünow | gelb | gelb | 2.269 | 2.269 | 7,44 | 7,52 | miet-check Miete |
| Merzdorf | gelb | gelb | 1.619 | 1.619 | 5,47 | 6,12 | miet-check Miete |
| Tantow | gelb | gelb | 1.820 | 1.820 | 6,83 | 6,22 | miet-check Miete |
| Briesen | grün | grün | 3.039 | 3.039 | 11,42 | 10,96 | miet-check Miete |
| Tettau | gelb | gelb | 2.139 | 1.969 | 6,76 | 6,73 | miet-check Miete, miete-aktuell Kauf, miete-aktuell Miete |
| Luckaitztal | gelb | gelb | 1.807 | 1.807 | 6,01 | 6,72 | miet-check Miete |
| Drachhausen | gelb | gelb | 1.894 | 1.894 | 6,22 | 7,04 | miet-check Miete |
| Mescherin | gelb | gelb | 1.823 | 1.823 | 6,68 | 6,08 | miet-check Miete |
| Cumlosen | gelb | gelb | 2.168 | 2.168 | 7,46 | 7,46 | miet-check Miete |
| Berge | gelb | gelb | 1.717 | 1.954 | 6,86 | 6,84 | miete-aktuell Kauf, miete-aktuell Miete |
| Kroppen | gelb | gelb | 1.970 | 1.970 | 5,95 | 6,87 | miet-check Miete |
| Frauendorf | gelb | gelb | 1.967 | 1.967 | 5,97 | 6,96 | miet-check Miete |
| Tauer | gelb | gelb | 1.892 | 1.892 | 6,25 | 7,07 | miet-check Miete |
| Marienfließ | gelb | gelb | 905 | 905 | 6,57 | 6,21 | miet-check Miete |
| Dabergotz | gelb | gelb | 2.847 | 2.847 | 9,43 | 9,61 | miet-check Miete |
| Schwarzbach | gelb | gelb | 1.524 | 1.524 | 5,92 | 6,86 | miet-check Miete |
| Herzberg (Mark) | gelb | gelb | 2.381 | 2.381 | 7,43 | 7,95 | miet-check Miete |
| Schenkenberg | rot | rot | 2.769 | 2.769 | 7,33 | 7,52 | miet-check Miete |
| Tröbitz | gelb | gelb | 1.150 | 1.150 | 6,18 | 6,21 | miet-check Miete |
| Legde/Quitzöbel | gelb | gelb | 850 | 850 | 7,03 | 6,83 | miet-check Miete |
| Heinersbrück | gelb | gelb | 2.037 | 2.037 | 6,21 | 7,45 | miet-check Miete |
| Grünewald | gelb | gelb | 1.200 | 1.200 | 4,64 | 4,64 | miet-check Miete |
| Guteborn | gelb | gelb | 1.574 | 1.574 | 6,03 | 6,93 | miet-check Miete |
| Triglitz | gelb | gelb | 1.400 | 1.400 | 6,39 | 7,55 | miet-check Miete |
| Drehnow | gelb | gelb | 1.866 | 1.866 | 6,49 | 7,45 | miet-check Miete |
| Schraden | rot | rot | 1.673 | 1.673 | 5,76 | 6,82 | miet-check Miete |
| Guhrow | grün | grün | 3.045 | 3.045 | 11,42 | 10,96 | miet-check Miete |
| Zichow | gelb | gelb | 2.274 | 2.274 | 6,38 | 6,99 | miet-check Miete |
| Rühstädt | gelb | gelb | 850 | 850 | 7,46 | 7,46 | miet-check Miete |
| Vielitzsee | gelb | gelb | 2.481 | 2.481 | 7,46 | 7,91 | miet-check Miete |
| Heideland | gelb | gelb | 1.337 | 1.657 | 7,39 | 6,89 | miet-check Miete, miete-aktuell Kauf, miete-aktuell Miete |
| Gerdshagen | gelb | gelb | 1.400 | 1.400 | 7,15 | 7,37 | miet-check Miete |
| Pirow | gelb | gelb | 2.220 | 2.220 | 7,21 | 7,26 | miet-check Miete |
| Schilda | gelb | gelb | 1.139 | 1.139 | 6,30 | 6,21 | miet-check Miete |
| Kümmernitztal | rot | rot | 2.385 | 2.385 | 6,08 | 6,07 | miet-check Miete |

## 2. Ortsteilseiten Berlin und Potsdam

### Ursache

- miete-aktuell hat eigene Ortsteilseiten unter `/mietspiegel/Berlin/Berlin/<Ortsteil>/` und `/mietspiegel/Potsdam/Potsdam/<Stadtteil>/`, jeweils auch für Kauf.
- Ich hatte nur andere Pfadformen geprüft, die auf die Startseite umleiteten. Daraus hatte ich fälschlich „keine Ortsteilseiten“ geschlossen.

### Prüfung

- Der Seitentitel muss Stadt und Ortsteil nennen.
- Die PLZ der Seite müssen sich mit den PLZ des Ortsteils überschneiden.
- Werte, die exakt einem anderen Ortsteil gleichen, gelten als nicht ortsgenau.

### Berlin

- 176 gewertete miete-aktuell-Werte.
- 90 Ortsteile ändern sich, Ampelwechsel 37: gelb zu grün 18, gelb zu rot 9, unbewertet zu gelb 5, rot zu gelb 2, unbewertet zu rot 2, grün zu gelb 1.
- Neue Verteilung der 97 Ortsteile: grün 27, gelb 47, rot 19, unbewertet 4. Vorher: grün 10, gelb 66, rot 10, unbewertet 11.
- Mehr Rot entsteht, weil mit der zweiten Kaufquelle jetzt der Faktor über 30 belegt ist, zum Beispiel Pankow, Lichtenberg und Rummelsburg.
- In Pankow greift die Zwei-Werte-Regel: homeday 3.800 und miete-aktuell 5.955 liegen über 50 % auseinander. Behalten ist der Wert näher am Gutachterwert, die Datenbasis ist als unsicher markiert.

### Ampelwechsel Berlin

| Ort | Ampel vorher | Ampel jetzt | Kauf vorher | Kauf jetzt | Miete vorher | Miete jetzt | neue Quellen |
|---|---|---|---|---|---|---|---|
| Moabit (Mitte) | rot | gelb | 5.750 | 5.472 | 15,82 | 17,70 | miete-aktuell Kauf, miete-aktuell Miete |
| Blankenburg (Pankow) | gelb | rot | 3.500 | 3.776 | 11,62 | 10,14 | miete-aktuell Kauf, miete-aktuell Miete |
| Heinersdorf (Pankow) | gelb | grün | 4.000 | 4.518 | 17,19 | 17,46 | miete-aktuell Kauf, miete-aktuell Miete |
| Pankow (Pankow) | gelb | rot | 3.800 | 5.955 | 14,42 | 15,16 | miete-aktuell Kauf, miete-aktuell Miete |
| Blankenfelde (Pankow) | gelb | grün | 3.400 | 4.261 | 15,93 | 16,91 | miete-aktuell Kauf, miete-aktuell Miete |
| Buch (Pankow) | gelb | rot | 4.566 | 4.462 | 13,46 | 12,27 | miete-aktuell Kauf, miete-aktuell Miete |
| Niederschönhausen (Pankow) | unbewertet | gelb | 4.100 | 4.538 |  | 15,58 | miete-aktuell Kauf, miete-aktuell Miete |
| Rosenthal (Pankow) | unbewertet | gelb | 3.650 | 4.435 |  | 15,60 | miete-aktuell Kauf, miete-aktuell Miete |
| Wilhelmsruh (Pankow) | gelb | grün | 3.650 | 4.345 | 15,82 | 15,88 | miete-aktuell Kauf, miete-aktuell Miete |
| Charlottenburg (Charlottenburg-Wilmersdorf) | unbewertet | gelb |  | 5.627 | 15,54 | 16,35 | miete-aktuell Kauf, miete-aktuell Miete |
| Spandau (Spandau) | gelb | grün | 3.500 | 3.525 | 13,57 | 13,12 | miete-aktuell Kauf, miete-aktuell Miete |
| Staaken (Spandau) | gelb | grün | 3.600 | 3.408 | 13,07 | 12,12 | miete-aktuell Kauf, miete-aktuell Miete |
| Kladow (Spandau) | unbewertet | gelb | 3.600 | 3.752 |  | 16,57 | miete-aktuell Kauf, miete-aktuell Miete |
| Dahlem (Steglitz-Zehlendorf) | rot | gelb | 6.450 | 6.289 | 17,14 | 18,50 | miete-aktuell Kauf, miete-aktuell Miete |
| Mariendorf (Tempelhof-Schöneberg) | gelb | grün | 3.850 | 4.094 | 15,22 | 15,16 | miete-aktuell Kauf, miete-aktuell Miete |
| Neukölln (Neukölln) | unbewertet | gelb |  | 5.444 | 14,64 | 15,21 | miete-aktuell Kauf, miete-aktuell Miete |
| Alt-Treptow (Treptow-Köpenick) | gelb | rot | 4.878 | 4.997 | 14,03 | 12,95 | miete-aktuell Kauf, miete-aktuell Miete |
| Johannisthal (Treptow-Köpenick) | gelb | grün | 3.954 | 3.893 | 15,19 | 15,27 | miete-aktuell Kauf, miete-aktuell Miete |
| Adlershof (Treptow-Köpenick) | gelb | grün | 3.933 | 3.888 | 18,19 | 16,93 | miete-aktuell Kauf, miete-aktuell Miete |
| Bohnsdorf (Treptow-Köpenick) | gelb | grün | 3.900 | 4.016 | 15,15 | 15,11 | miete-aktuell Kauf, miete-aktuell Miete |
| Friedrichshagen (Treptow-Köpenick) | gelb | rot | 4.876 | 4.825 | 14,40 | 13,32 | miete-aktuell Kauf, miete-aktuell Miete |
| Rahnsdorf (Treptow-Köpenick) | grün | gelb | 4.186 | 4.395 | 15,37 | 15,05 | miete-aktuell Kauf, miete-aktuell Miete |
| Grünau (Treptow-Köpenick) | gelb | grün | 4.290 | 4.389 | 17,54 | 17,30 | miete-aktuell Kauf, miete-aktuell Miete |
| Müggelheim (Treptow-Köpenick) | gelb | grün | 3.200 | 3.371 | 12,27 | 12,45 | miete-aktuell Kauf, miete-aktuell Miete |
| Schmöckwitz (Treptow-Köpenick) | gelb | grün | 4.326 | 4.299 | 15,58 | 16,57 | miete-aktuell Kauf, miete-aktuell Miete |
| Mahlsdorf (Marzahn-Hellersdorf) | gelb | grün | 3.609 | 3.766 | 15,98 | 15,80 | miete-aktuell Kauf, miete-aktuell Miete |
| Lichtenberg (Lichtenberg) | gelb | rot | 4.400 | 4.854 | 13,21 | 13,19 | miete-aktuell Kauf, miete-aktuell Miete |
| Falkenberg (Lichtenberg) | gelb | rot | 3.550 | 3.346 | 12,56 | 7,90 | miete-aktuell Kauf, miete-aktuell Miete |
| Wartenberg (Lichtenberg) | gelb | rot | 3.200 | 3.410 | 10,30 | 9,27 | miete-aktuell Kauf, miete-aktuell Miete |
| Rummelsburg (Lichtenberg) | gelb | rot | 5.500 | 5.544 | 15,35 | 15,07 | miete-aktuell Kauf, miete-aktuell Miete |
| Tegel (Reinickendorf) | gelb | grün | 3.850 | 3.906 | 14,90 | 14,05 | miete-aktuell Kauf, miete-aktuell Miete |
| Konradshöhe (Reinickendorf) | gelb | grün | 4.150 | 4.199 | 17,28 | 18,45 | miete-aktuell Kauf, miete-aktuell Miete |
| Heiligensee (Reinickendorf) | gelb | grün | 3.800 | 3.919 | 16,57 | 16,88 | miete-aktuell Kauf, miete-aktuell Miete |
| Frohnau (Reinickendorf) | gelb | grün | 4.300 | 4.170 | 15,35 | 14,84 | miete-aktuell Kauf, miete-aktuell Miete |
| Hermsdorf (Reinickendorf) | gelb | grün | 4.100 | 4.083 | 15,84 | 15,46 | miete-aktuell Kauf, miete-aktuell Miete |
| Waidmannslust (Reinickendorf) | unbewertet | rot | 3.650 | 4.001 |  | 10,86 | miete-aktuell Kauf, miete-aktuell Miete |
| Lübars (Reinickendorf) | unbewertet | rot | 3.650 | 4.022 |  | 11,05 | miete-aktuell Kauf, miete-aktuell Miete |

### Berlin ohne Ampelwechsel (nur Kauf oder Miete geändert)

| Ort | Ampel vorher | Ampel jetzt | Kauf vorher | Kauf jetzt | Miete vorher | Miete jetzt | neue Quellen |
|---|---|---|---|---|---|---|---|
| Mitte (Mitte) | rot | rot | 6.650 | 7.626 | 16,84 | 19,30 | miete-aktuell Kauf, miete-aktuell Miete |
| Hansaviertel (Mitte) | gelb | gelb | 5.750 | 5.684 | 17,86 | 19,88 | miete-aktuell Kauf, miete-aktuell Miete |
| Tiergarten (Mitte) | gelb | gelb | 6.050 | 5.866 | 16,89 | 18,09 | miete-aktuell Kauf, miete-aktuell Miete |
| Wedding (Mitte) | gelb | gelb | 4.250 | 4.276 | 14,05 | 14,33 | miete-aktuell Kauf, miete-aktuell Miete |
| Friedrichshain (Friedrichshain-Kreuzberg) | gelb | gelb | 5.250 | 5.788 | 16,06 | 17,38 | miete-aktuell Kauf, miete-aktuell Miete |
| Prenzlauer Berg (Pankow) | rot | rot | 5.750 | 6.155 | 15,73 | 16,50 | miete-aktuell Kauf, miete-aktuell Miete |
| Weißensee (Pankow) | gelb | gelb | 5.286 | 5.236 | 15,47 | 15,76 | miete-aktuell Kauf, miete-aktuell Miete |
| Karow (Pankow) | rot | rot | 4.968 | 4.777 | 13,03 | 12,12 | miete-aktuell Kauf, miete-aktuell Miete |
| Stadtrandsiedlung Malchow (Pankow) | gelb | gelb | 4.350 | 4.831 | 13,19 | 14,21 | miete-aktuell Kauf, miete-aktuell Miete |
| Französisch Buchholz (Pankow) | gelb | gelb | 4.673 | 4.607 | 15,51 | 16,11 | miete-aktuell Kauf, miete-aktuell Miete |
| Wilmersdorf (Charlottenburg-Wilmersdorf) | gelb | gelb | 5.550 | 5.687 | 16,47 | 17,57 | miete-aktuell Kauf, miete-aktuell Miete |
| Schmargendorf (Charlottenburg-Wilmersdorf) | gelb | gelb | 5.667 | 5.759 | 18,52 | 18,78 | miete-aktuell Kauf, miete-aktuell Miete |
| Grunewald (Charlottenburg-Wilmersdorf) | gelb | gelb | 6.054 | 5.950 | 18,23 | 18,74 | miete-aktuell Kauf, miete-aktuell Miete |
| Westend (Charlottenburg-Wilmersdorf) | rot | rot | 5.778 | 5.692 | 14,94 | 15,63 | miete-aktuell Kauf, miete-aktuell Miete |
| Halensee (Charlottenburg-Wilmersdorf) | gelb | gelb | 5.828 | 5.811 | 19,47 | 19,15 | miete-aktuell Kauf, miete-aktuell Miete |
| Haselhorst (Spandau) | gelb | gelb | 3.853 | 3.863 | 14,75 | 12,88 | miete-aktuell Kauf, miete-aktuell Miete |
| Siemensstadt (Spandau) | grün | grün | 3.620 | 3.758 | 13,98 | 13,42 | miete-aktuell Kauf, miete-aktuell Miete |
| Gatow (Spandau) | unbewertet | unbewertet | 3.600 | 3.820 |  |  | miete-aktuell Kauf |
| Hakenfelde (Spandau) | grün | grün | 3.578 | 3.629 | 15,14 | 14,43 | miete-aktuell Kauf, miete-aktuell Miete |
| Wilhelmstadt (Spandau) | grün | grün | 3.555 | 3.677 | 13,85 | 13,53 | miete-aktuell Kauf, miete-aktuell Miete |
| Steglitz (Steglitz-Zehlendorf) | gelb | gelb | 4.700 | 4.809 | 15,98 | 16,40 | miete-aktuell Kauf, miete-aktuell Miete |
| Lichterfelde (Steglitz-Zehlendorf) | gelb | gelb | 4.550 | 4.821 | 15,64 | 15,64 | miete-aktuell Kauf |
| Lankwitz (Steglitz-Zehlendorf) | gelb | gelb | 4.354 | 4.415 | 14,26 | 13,81 | miete-aktuell Kauf, miete-aktuell Miete |
| Zehlendorf (Steglitz-Zehlendorf) | gelb | gelb | 5.200 | 4.894 | 15,77 | 16,11 | miete-aktuell Kauf, miete-aktuell Miete |
| Nikolassee (Steglitz-Zehlendorf) | gelb | gelb | 5.350 | 5.314 | 15,99 | 16,80 | miete-aktuell Kauf, miete-aktuell Miete |
| Wannsee (Steglitz-Zehlendorf) | gelb | gelb | 5.450 | 5.328 | 16,50 | 15,95 | miete-aktuell Kauf, miete-aktuell Miete |
| Schöneberg (Tempelhof-Schöneberg) | gelb | gelb | 5.200 | 5.477 | 15,73 | 16,26 | miete-aktuell Kauf, miete-aktuell Miete |
| Friedenau (Tempelhof-Schöneberg) | gelb | gelb | 5.100 | 5.214 | 15,81 | 15,81 | miete-aktuell Kauf |
| Tempelhof (Tempelhof-Schöneberg) | gelb | gelb | 4.550 | 4.523 | 15,10 | 14,93 | miete-aktuell Kauf, miete-aktuell Miete |
| Marienfelde (Tempelhof-Schöneberg) | gelb | gelb | 3.800 | 3.938 | 14,34 | 12,84 | miete-aktuell Kauf, miete-aktuell Miete |
| Lichtenrade (Tempelhof-Schöneberg) | gelb | gelb | 3.850 | 4.037 | 13,64 | 12,60 | miete-aktuell Kauf, miete-aktuell Miete |
| Britz (Neukölln) | gelb | gelb | 4.209 | 4.171 | 13,68 | 13,40 | miete-aktuell Kauf, miete-aktuell Miete |
| Buckow (Neukölln) | gelb | gelb | 4.074 | 4.027 | 13,93 | 13,27 | miete-aktuell Kauf, miete-aktuell Miete |
| Rudow (Neukölln) | gelb | gelb | 4.145 | 4.153 | 12,80 | 12,23 | miete-aktuell Kauf, miete-aktuell Miete |
| Gropiusstadt (Neukölln) | gelb | gelb | 3.800 | 3.962 | 14,45 | 13,03 | miete-aktuell Kauf, miete-aktuell Miete |
| Plänterwald (Treptow-Köpenick) | rot | rot | 5.150 | 4.812 | 13,64 | 12,74 | miete-aktuell Kauf, miete-aktuell Miete |
| Baumschulenweg (Treptow-Köpenick) | gelb | gelb | 4.232 | 4.221 | 13,41 | 13,39 | miete-aktuell Kauf, miete-aktuell Miete |
| Niederschöneweide (Treptow-Köpenick) | grün | grün | 4.088 | 4.080 | 16,87 | 16,37 | miete-aktuell Kauf, miete-aktuell Miete |
| Altglienicke (Treptow-Köpenick) | grün | grün | 4.042 | 4.128 | 15,43 | 14,89 | miete-aktuell Kauf, miete-aktuell Miete |
| Oberschöneweide (Treptow-Köpenick) | grün | grün | 4.086 | 4.216 | 15,19 | 15,03 | miete-aktuell Kauf, miete-aktuell Miete |
| Köpenick (Treptow-Köpenick) | grün | grün | 3.883 | 4.046 | 15,51 | 15,58 | miete-aktuell Kauf, miete-aktuell Miete |
| Marzahn (Marzahn-Hellersdorf) | gelb | gelb | 3.200 | 3.433 | 11,93 | 10,96 | miete-aktuell Kauf, miete-aktuell Miete |
| Biesdorf (Marzahn-Hellersdorf) | grün | grün | 3.700 | 3.769 | 14,93 | 14,89 | miete-aktuell Kauf, miete-aktuell Miete |
| Kaulsdorf (Marzahn-Hellersdorf) | grün | grün | 3.847 | 3.798 | 15,12 | 15,12 | miete-aktuell Kauf |
| Hellersdorf (Marzahn-Hellersdorf) | gelb | gelb | 3.050 | 3.183 | 14,20 | 14,20 | miete-aktuell Kauf |
| Friedrichsfelde (Lichtenberg) | gelb | gelb | 3.800 | 4.498 | 15,41 | 15,34 | miete-aktuell Kauf, miete-aktuell Miete |
| Karlshorst (Lichtenberg) | gelb | gelb | 4.685 | 4.680 | 16,05 | 15,89 | miete-aktuell Kauf, miete-aktuell Miete |
| Malchow (Lichtenberg) | gelb | gelb | 2.800 | 3.207 | 10,00 | 9,38 | miete-aktuell Kauf, miete-aktuell Miete |
| Neu-Hohenschönhausen (Lichtenberg) | gelb | gelb | 2.800 | 3.285 | 11,45 | 10,48 | miete-aktuell Kauf, miete-aktuell Miete |
| Alt-Hohenschönhausen (Lichtenberg) | gelb | gelb | 4.000 | 3.894 | 12,57 | 12,45 | miete-aktuell Kauf, miete-aktuell Miete |
| Reinickendorf (Reinickendorf) | gelb | gelb | 3.800 | 3.889 | 13,28 | 12,86 | miete-aktuell Kauf, miete-aktuell Miete |
| Wittenau (Reinickendorf) | gelb | gelb | 3.550 | 3.746 | 12,01 | 11,88 | miete-aktuell Kauf, miete-aktuell Miete |
| Märkisches Viertel (Reinickendorf) | rot | rot | 3.500 | 3.746 | 8,88 | 8,26 | miete-aktuell Kauf, miete-aktuell Miete |

### Potsdam

13 bestehende Stadtteile sind aktualisiert. 15 Stadtteile sind neu angelegt, weil sie jetzt eine eigene, ortsgenaue Portalseite haben:
Babelsberg Nord, Babelsberg Süd, Waldstadt I, Waldstadt II, Golm, Groß Glienicke, Marquardt, Neu Fahrland, Satzkorn, Sacrow, Nedlitz, Grube, Klein Glienicke, Templiner Vorstadt, Schlaatz.

- **Einwohner:** Stadt Potsdam zum 31.12.2025. Waldstadt I weist die Stadt nur gemeinsam mit dem Industriegelände aus; das ist im Feld einwohnerQuelle vermerkt.
- **Koordinaten:** Schwerpunkte der OSM-Grenzen.
- **Nicht angelegt:**
  - „Nördliche Innenstadt“ und „Südliche Innenstadt“ sind seit 31.12.2019 keine amtlichen Stadtteile mehr. Sie wurden in Historische Innenstadt bzw. Zentrum Ost und Nuthepark und Hauptbahnhof und Brauhausberg Nord umbenannt und geteilt.
  - Zentrum Ost hat keine eigene Seite.
- **Auffällig: Berliner Vorstadt.** miete-aktuell nennt nur 2.298 €/m² Kauf. Nach der Ausreißerregel fällt deshalb immoportal (5.683 €/m²) heraus, weil der Wert mehr als 50 % über der nächsten Portalquelle liegt. Die Ampel ist jetzt gelb statt rot. Ich habe die Regel nicht verändert; der Wert sollte lokal geprüft werden.

| Ort | Ampel vorher | Ampel jetzt | Kauf vorher | Kauf jetzt | Miete vorher | Miete jetzt | neue Quellen |
|---|---|---|---|---|---|---|---|
| Am Stern (Potsdam) | gelb | gelb | 4.297 | 4.208 | 13,98 | 13,12 | miete-aktuell Kauf, miete-aktuell Miete |
| Babelsberg Nord (Potsdam) | neu | rot |  | 5.007 |  | 13,41 | miete-aktuell Kauf, miete-aktuell Miete |
| Babelsberg Süd (Potsdam) | neu | gelb |  | 4.557 |  | 13,76 | miete-aktuell Kauf, miete-aktuell Miete |
| Berliner Vorstadt (Potsdam) | rot | gelb | 5.683 | 2.298 | 15,49 | 14,73 | miete-aktuell Kauf, miete-aktuell Miete |
| Bornim (Potsdam) | rot | rot | 5.322 | 5.463 | 12,92 | 13,96 | miete-aktuell Kauf, miete-aktuell Miete |
| Bornstedt (Potsdam) | rot | rot | 6.665 | 6.178 | 16,75 | 15,51 | miete-aktuell Kauf, miete-aktuell Miete |
| Brandenburger Vorstadt (Potsdam) | rot | rot | 5.766 | 5.618 | 12,76 | 12,70 | miete-aktuell Kauf, miete-aktuell Miete |
| Drewitz (Potsdam) | unbewertet | gelb | 4.583 | 4.316 |  | 12,30 | miete-aktuell Kauf, miete-aktuell Miete |
| Eiche (Potsdam) | rot | rot | 4.847 | 4.988 | 13,42 | 13,63 | miete-aktuell Kauf, miete-aktuell Miete |
| Fahrland (Potsdam) | gelb | gelb | 4.552 | 4.338 | 13,77 | 13,68 | miete-aktuell Kauf, miete-aktuell Miete |
| Jägervorstadt (Potsdam) | gelb | gelb | 5.001 | 5.127 | 16,60 | 15,39 | miete-aktuell Kauf, miete-aktuell Miete |
| Kirchsteigfeld (Potsdam) | gelb | gelb | 4.388 | 4.214 | 12,41 | 12,36 | miete-aktuell Kauf, miete-aktuell Miete |
| Nauener Vorstadt (Potsdam) | rot | rot | 5.378 | 5.436 | 14,79 | 14,71 | miete-aktuell Kauf, miete-aktuell Miete |
| Potsdam West (Potsdam) | rot | rot | 6.165 | 5.760 | 12,62 | 12,68 | miete-aktuell Kauf, miete-aktuell Miete |
| Teltower Vorstadt (Potsdam) | rot | gelb | 5.122 | 4.619 | 12,71 | 13,29 | miete-aktuell Kauf, miete-aktuell Miete |
| Waldstadt I (Potsdam) | neu | gelb |  | 3.581 |  | 11,07 | miete-aktuell Kauf, miete-aktuell Miete |
| Waldstadt II (Potsdam) | neu | gelb |  | 3.657 |  | 11,13 | miete-aktuell Kauf, miete-aktuell Miete |
| Golm (Potsdam) | neu | rot |  | 5.442 |  | 13,73 | miete-aktuell Kauf, miete-aktuell Miete |
| Groß Glienicke (Potsdam) | neu | gelb |  | 3.768 |  | 13,20 | miete-aktuell Kauf, miete-aktuell Miete |
| Marquardt (Potsdam) | neu | gelb |  | 3.848 |  | 13,29 | miete-aktuell Kauf, miete-aktuell Miete |
| Neu Fahrland (Potsdam) | neu | gelb |  | 3.821 |  | 12,87 | miete-aktuell Kauf, miete-aktuell Miete |
| Satzkorn (Potsdam) | neu | gelb |  | 3.918 |  | 12,81 | miete-aktuell Kauf, miete-aktuell Miete |
| Sacrow (Potsdam) | neu | rot |  | 5.381 |  | 14,71 | miete-aktuell Kauf, miete-aktuell Miete |
| Nedlitz (Potsdam) | neu | rot |  | 5.371 |  | 14,81 | miete-aktuell Kauf, miete-aktuell Miete |
| Grube (Potsdam) | neu | gelb |  | 5.101 |  | 14,58 | miete-aktuell Kauf, miete-aktuell Miete |
| Klein Glienicke (Potsdam) | neu | rot |  | 5.068 |  | 13,27 | miete-aktuell Kauf, miete-aktuell Miete |
| Templiner Vorstadt (Potsdam) | neu | gelb |  | 5.403 |  | 15,58 | miete-aktuell Kauf, miete-aktuell Miete |
| Schlaatz (Potsdam) | neu | gelb |  | 3.471 |  | 11,46 | miete-aktuell Kauf, miete-aktuell Miete |

## 3. Prognose für kleine BW-Gemeinden

- Ich habe GENESIS-Online BW (Tabelle 12421-0006) am 20.10.2026 erneut abgefragt.
- Die Gebietsauswahl findet heute für keine Gemeinde einen Eintrag, auch nicht für Bad Urach, das am 19.10.2026 noch gefunden wurde. Die Seite meldet „Zur angegebenen Auswahl wurden keine Einträge gefunden“.
- Am Vortag brach der Werteabruf mit Server-Timeout ab.
- Wie gewünscht blockiert das nicht. Die Lücken bleiben bestehen:
  - **ergebnis19 Teil 1:** 18 Gemeinden ohne Prognose, die Ampel ist höchstens gelb. 17 davon haben unter 5.000 Einwohner. Es sind Bad Bellingen, Stegen, Rheinhausen, Freiamt, Meißenheim, Riegel, Biberach, Sasbach am Kaiserstuhl, Malterdingen, Gottenheim, Eisenbach, Hofstetten, Wittnau, Malsburg-Marzell, Wutach, Häg-Ehrsberg, Utzenfeld und Wembach. Bad Bellingen hat zwar über 5.000 Einwohner, aber bei Wegweiser Kommune keine Werte.
  - **ergebnis16:** Ebringen und Pfaffenweiler.
- Die größeren BW-Orte haben die Ersatzprognose von Wegweiser Kommune, wie bisher gekennzeichnet.
- Ob die Tabelle Gemeinden unter 5.000 Einwohnern überhaupt enthält, ließ sich heute wegen der Störung nicht klären.

## Geänderte Programmteile (zur Nachvollziehbarkeit)

- miet-check-Muster um das zweite Seitenlayout erweitert.
- miete-aktuell-Ortsteilseiten (Berlin, Potsdam) und Kandidatensuche über die Ortsverzeichnisse von miet-check, immoportal und miete-aktuell.
- Alle anderen Regeln sind unverändert.
