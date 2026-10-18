# Zusammenfassung Block 04 (zweite Fassung mit Korrekturen), 300 Gemeinden

Ausgabe: `ergebnis3/lieferung-01.json` bis `lieferung-06.json`. Erste Fassung: `ergebnis/`. Alles liegt auf dem Branch `claude/laughing-sagan-q2wyfw`, main ist unberührt.

## Angewendete Korrekturen

- miete-aktuell: mehrere Schreibweisen je Ort (Kürzel mit und ohne Punkt, Klammer, Zusatz Kr. oder Lk.), Mietseite direkt aus dem Pfad der Kaufseite abgeleitet.
- miet-check: zusätzliche Pfadzusätze (Flüsse, Regionen), die Deutschlandwerte 9,65 und 9,75 zählen nie.
- Ortsprüfung weniger streng: Nachbarorte der Seite werden gegen das Bundesland geprüft, nicht nur gegen den Landkreis. Passen alle Nachbarorte nicht zum Bundesland, gilt die Seite als falscher Ort.
- Gleichnamige Orte: bei immoportal werden die Pfade mit -0, -1, -2, -bw und -by zusätzlich versucht.
- Ausreißerregel: ein Kaufwert unter 60 % oder über 150 % des Medians der übrigen Quellen zählt nicht. Der Gutachterwert gilt dabei als Vergleichswert. Der Grund steht im Beleg.
- Rundung: die Rendite wird auf eine Nachkommastelle gerundet, ab 4,25 % gilt 4,3 % und damit grün (wenn Faktor höchstens 25 und die Datenbasis trägt).

## Ampel gesamt

- gesamt: erste Fassung grün 129, gelb 161, rot 10; neu grün 143, gelb 148, rot 9
- Bayern: erste Fassung grün 40, gelb 120, rot 10; neu grün 43, gelb 118, rot 9
- Baden-Württemberg: erste Fassung grün 89, gelb 41, rot 0; neu grün 100, gelb 30, rot 0

## Änderungen gegenüber der ersten Fassung

53 von 300 Orten haben einen anderen Kaufwert, Mietwert oder eine andere Ampel. Ampelwechsel: 21.

### Die 15 Referenzorte (alt zu neu)

| Ort | Kauf alt | Kauf neu | Miete alt | Miete neu | Ampel alt | Ampel neu |
|---|---|---|---|---|---|---|
| Pyrbaum | 2.390 | 2.950 | 10,38 | 10,38 | grün | gelb |
| Sulz am Neckar | 1.874 | 2.303 | 9,96 | 9,96 | gelb | grün |
| Landau a.d.Isar | 3.496 | 3.015 | 10,54 | 10,51 | gelb | gelb |
| Taufkirchen (Vils) | 5.508 | 5.038 | 12,21 | 12,42 | rot | rot |
| Brühl | 3.396 | 3.552 | 12,36 | 12,68 | gelb | gelb |
| Altdorf b.Nürnberg | 3.270 | 3.152 | 11,05 | 10,91 | gelb | gelb |
| Kirchheim b.München | 6.604 | 6.523 | 18,59 | 19,12 | gelb | gelb |
| Neuried | 6.368 | 6.402 | 19,57 | 19,80 | gelb | gelb |
| Karlstadt | 2.556 | 2.556 | 9,23 | 9,29 | grün | grün |
| Regenstauf | 3.112 | 3.112 | 11,12 | 11,12 | gelb | grün |
| Holzkirchen | 6.220 | 6.220 | 16,78 | 16,78 | rot | rot |
| Kernen im Remstal | 3.763 | 3.763 | 13,93 | 13,93 | grün | grün |
| Schönaich | 3.938 | 3.938 | 14,55 | 14,55 | grün | grün |
| Baiersbronn | 1.869 | 1.869 | 9,92 | 9,92 | grün | grün |
| Eppelheim | 3.346 | 3.346 | 13,57 | 13,57 | grün | grün |

Die Sollwerte aus dem Prüfbericht kenne ich nicht, der Vergleich mit ihnen steht aus.

### Alle Orte mit Ampelwechsel

- Regenstauf (09375190): gelb zu grün, Kauf 3.112 zu 3.112, Miete 11,12 zu 11,12
- Lohr a.Main (09677155): gelb zu grün, Kauf 2.514 zu 2.594, Miete 9,37 zu 9,84
- Neustadt b.Coburg (09473151): gelb zu grün, Kauf 2.107 zu 1.981, Miete 7,31 zu 7,24
- Eggenfelden (09277116): gelb zu grün, Kauf 2.895 zu 2.895, Miete 10,33 zu 10,33
- St. Leon-Rot (08226103): gelb zu grün, Kauf 3.421 zu 3.410, Miete 11,98 zu 12,10
- Meckenbeuren (08435035): gelb zu grün, Kauf 3.811 zu 3.811, Miete 13,59 zu 13,59
- Sulz am Neckar (08325057): gelb zu grün, Kauf 1.874 zu 2.303, Miete 9,96 zu 9,96
- Graben-Neudorf (08215099): gelb zu grün, Kauf 3.466 zu 3.466, Miete 12,35 zu 12,35
- Heddesheim (08226028): gelb zu grün, Kauf 3.288 zu 3.288, Miete 11,74 zu 11,74
- Wernau (Neckar) (08116072): gelb zu grün, Kauf 3.740 zu 3.639, Miete 13,15 zu 13,16
- Rheinau (08317153): gelb zu grün, Kauf 3.031 zu 3.031, Miete 10,75 zu 10,75
- Burgkirchen a.d.Alz (09171113): grün zu gelb, Kauf 2.966 zu 3.215, Miete 10,93 zu 10,89
- Haigerloch (08417025): gelb zu grün, Kauf 2.409 zu 2.354, Miete 9,98 zu 9,98
- Dornstadt (08425031): gelb zu grün, Kauf 4.199 zu 3.571, Miete 12,69 zu 12,69
- Schwaig b.Nürnberg (09574156): gelb zu grün, Kauf 3.372 zu 3.405, Miete 12,31 zu 12,36
- Waldenbuch (08115048): gelb zu grün, Kauf 3.805 zu 3.805, Miete 13,61 zu 13,61
- Pullach i.Isartal (09184139): rot zu gelb, Kauf 7.045 zu 7.134, Miete 19,40 zu 20,02
- Arnstein (09677114): grün zu gelb, Kauf 1.978 zu 2.530, Miete 8,58 zu 8,58
- Weissach (08115052): gelb zu grün, Kauf 3.907 zu 3.907, Miete 13,91 zu 13,91
- Pfaffenhofen a.d.Roth (09775143): gelb zu grün, Kauf 3.025 zu 2.950, Miete 11,86 zu 11,50
- Pyrbaum (09373156): grün zu gelb, Kauf 2.390 zu 2.950, Miete 10,38 zu 10,38

### Orte mit geändertem Kauf- oder Mietwert, Ampel gleich

- Altdorf b.Nürnberg (09574112): Kauf 3.270 zu 3.152, Miete 11,05 zu 10,91
- Bad Neustadt a.d.Saale (09673114): Kauf 2.558 zu 2.574, Miete 8,98 zu 8,96
- Neustadt a.d.Donau (09273152): Kauf 3.096 zu 3.136, Miete 11,25 zu 11,29
- Landau a.d.Isar (09279122): Kauf 3.496 zu 3.015, Miete 10,54 zu 10,51
- Karlstadt (09677148): Kauf 2.556 zu 2.556, Miete 9,23 zu 9,29
- Brühl (08226009): Kauf 3.396 zu 3.552, Miete 12,36 zu 12,68
- Krumbach (Schwaben) (09774150): Kauf 3.498 zu 3.200, Miete 10,84 zu 10,84
- Immenstadt i.Allgäu (09780124): Kauf 3.859 zu 3.804, Miete 12,43 zu 11,78
- Grafing b.München (09175122): Kauf 5.916 zu 5.796, Miete 15,44 zu 15,59
- Höchstadt a.d.Aisch (09572135): Kauf 3.131 zu 3.000, Miete 10,54 zu 10,51
- Kirchheim b.München (09184131): Kauf 6.604 zu 6.523, Miete 18,59 zu 19,12
- Röthenbach a.d.Pegnitz (09574152): Kauf 3.132 zu 3.119, Miete 11,88 zu 11,85
- Wasserburg a.Inn (09187182): Kauf 4.380 zu 4.356, Miete 12,43 zu 12,39
- St. Georgen im Schwarzwald (08326052): Kauf 2.190 zu 2.136, Miete 8,92 zu 8,57
- Osterhofen (09271141): Kauf 2.930 zu 2.735, Miete 9,66 zu 9,66
- Murnau a.Staffelsee (09180124): Kauf 5.755 zu 5.730, Miete 14,86 zu 15,26
- Lauingen (Donau) (09773144): Kauf 2.896 zu 2.862, Miete 10,53 zu 10,59
- Lindenberg i.Allgäu (09776117): Kauf 3.693 zu 3.577, Miete 11,97 zu 12,04
- Herrsching a.Ammersee (09188124): Kauf 6.670 zu 6.663, Miete 17,54 zu 18,12
- Regen (09276138): Kauf 1.441 zu 2.030, Miete 8,57 zu 8,57
- Prien a.Chiemsee (09187162): Kauf 4.913 zu 4.931, Miete 14,47 zu 14,98
- Taufkirchen (Vils) (09177139): Kauf 5.508 zu 5.038, Miete 12,21 zu 12,42
- Bogen (09278118): Kauf 2.796 zu 2.884, Miete 9,94 zu 9,94
- Simbach a.Inn (09277145): Kauf 2.708 zu 2.662, Miete 9,14 zu 9,21
- Birkenfeld (08236004): Kauf 3.232 zu 3.223, Miete 10,83 zu 10,83
- Werneck (09678193): Kauf 1.830 zu 2.178, Miete 8,77 zu 8,77
- Gemünden a.Main (09677131): Kauf 2.355 zu 2.452, Miete 7,65 zu 7,52
- Langweid a.Lech (09772171): Kauf 4.022 zu 3.961, Miete 12,76 zu 13,17
- Neuried (09184132): Kauf 6.368 zu 6.402, Miete 19,57 zu 19,80
- Neunkirchen a.Brand (09474154): Kauf 3.475 zu 3.562, Miete 10,51 zu 10,98
- Sauerlach (09184141): Kauf 6.989 zu 6.542, Miete 17,45 zu 17,45
- Hemmingen (08118027): Kauf 2.880 zu 3.353, Miete 14,20 zu 13,90

## Datenlage

- Orte mit gestrichenem Wert (Ortsverwechslung oder Ausreißer): 6
- Orte mit dünner Datenbasis (weniger als zwei Quellen): 7
- Orte mit Ersatzquelle: 20
- Mietpreisbremse: 90 Orte

