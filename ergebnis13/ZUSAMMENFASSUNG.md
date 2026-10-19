# Zusammenfassung Nacharbeit (ergebnis13), ergebnis2 und ergebnis3

Patches: `ergebnis13/patch-d-01.json`, Format wie ergebnis12. Jeder Eintrag hat `satz`, `id` und `ags`, dazu nur die geänderten Felder, außerdem `muster`, `korrekturen` und `ampelNeu`. Ausgangsstand sind ergebnis2 und ergebnis3 mit den Patches aus ergebnis4 und ergebnis8. Geprüft sind alle 1300 Orte, geändert sind 81 (ergebnis2 78, ergebnis3 3). Dazu kommt `ergebnis13/oelsnitz-vogtl.json`, die vollständige Bewertung von Oelsnitz/Vogtl. (ags 14523300) mit Kauffällen und Wohnungspreisen aus dem Grundstücksmarktbericht 2025 des Gutachterausschusses im Vogtlandkreis (https://www.vogtlandkreis.de/media/custom/3434_6169_1.PDF). Branch: `claude/laughing-sagan-q2wyfw`.

## Muster, geänderte Orte und Ampelwechsel

- (1) miete-aktuell-Pfade mit Zusatz: 23 Orte, Ampelwechsel: unbewertet zu gelb 10, grün zu gelb 1, rot zu gelb 1, gelb zu grün 3. Beispiel: Eching (Landkreis Landshut) jetzt über `Eching-Niederbayern/Eching/`.
- (2) stille homeday-Umleitung: 4 Orte, Ampelwechsel: gelb zu unbewertet 1, grün zu gelb 1. Der Abgleich ist korrigiert wie bei ergebnis12. Schreibvarianten zählen als derselbe Ort, nur echte Umleitungen auf einen anderen Ort sind entfernt.
- (3) Gutachterwert bei nur einem Portalwert: 47 Orte, Ampelwechsel: unbewertet zu gelb 4, gelb zu rot 1, grün zu gelb 20. Der Kreiswert zählt erst ab zwei Portalwerten, sonst steht er nur im Beleg.
- (4) Ersatzwert nach gestrichenem Ausreißer: 14 Orte, Ampelwechsel: gelb zu grün 2, grün zu gelb 2. Auslegung wie bei ergebnis12: Die Ersatzquelle kommt zum ursprünglichen Wertesatz, die Ausreißerregel läuft neu.
- Ohne Prognose ist die Ampel höchstens gelb. Es gab keinen grünen Ort ohne Prognose.

Ein Ort kann mehrere Muster haben. Die Ampelwechsel je Muster zählen deshalb jeden Wechsel bei allen beteiligten Mustern.

## Alle Ampelwechsel

Zusammen 41: unbewertet zu gelb 10, gelb zu rot 1, grün zu gelb 23, gelb zu grün 5, gelb zu unbewertet 1, rot zu gelb 1.

- Babenhausen (09778115, ergebnis2, Muster 1, 3): unbewertet zu gelb, Kauf None zu 1833, Miete 10.38 zu 10.62
- Seeon-Seebruck (09189143, ergebnis2, Muster 3): gelb zu rot, Kauf 4450 zu 5000, Miete 12.99 zu 12.99
- Vöhringen (08325061, ergebnis2, Muster 1): unbewertet zu gelb, Kauf None zu 1840, Miete 10.2 zu 10.84
- Haldenwang (09780122, ergebnis2, Muster 3): grün zu gelb, Kauf 3547 zu 3494, Miete 13.11 zu 13.11
- Buxheim (09176118, ergebnis2, Muster 1): grün zu gelb, Kauf 3053 zu 3669, Miete 12.97 zu 11.29
- Ortenberg (08317100, ergebnis2, Muster 1): unbewertet zu gelb, Kauf None zu 3455, Miete 11.77 zu 12.36
- Buxheim (09778123, ergebnis2, Muster 3): grün zu gelb, Kauf 3584 zu 3768, Miete 12.94 zu 12.94
- Auerbach i.d.OPf. (09371113, ergebnis2, Muster 3): grün zu gelb, Kauf 2044 zu 1889, Miete 8.04 zu 8.04
- Illingen (08236028, ergebnis2, Muster 1): unbewertet zu gelb, Kauf None zu 3090, Miete 11.71 zu 11.75
- Emskirchen (09575121, ergebnis2, Muster 3): grün zu gelb, Kauf 2425 zu 2450, Miete 11.49 zu 11.49
- Altenkunstadt (09478111, ergebnis2, Muster 3): grün zu gelb, Kauf 1700 zu 1400, Miete 7.96 zu 7.96
- Rosengarten (08127100, ergebnis2, Muster 1): unbewertet zu gelb, Kauf None zu 2392, Miete 11.29 zu 11.24
- Oberkotzau (09475158, ergebnis2, Muster 4): gelb zu grün, Kauf 1350 zu 1612, Miete 7.79 zu 7.79
- Erbendorf (09377116, ergebnis2, Muster 3): grün zu gelb, Kauf 1900 zu 1900, Miete 9.42 zu 9.42
- Lichtenau (08216028, ergebnis2, Muster 1): unbewertet zu gelb, Kauf None zu 2507, Miete 10.68 zu 10.0
- Creußen (09472127, ergebnis2, Muster 3, 4): grün zu gelb, Kauf 1975 zu 2050, Miete 9.82 zu 9.82
- Hollfeld (09472154, ergebnis2, Muster 3): grün zu gelb, Kauf 1850 zu 1800, Miete 8.37 zu 8.37
- Bischofsheim i.d.Rhön (09673117, ergebnis2, Muster 2): gelb zu unbewertet, Kauf 2050 zu None, Miete 7.9 zu 7.9
- Leidersbach (09676136, ergebnis2, Muster 4): grün zu gelb, Kauf 2400 zu 2992, Miete 10.41 zu 10.41
- Lautertal (09473141, ergebnis2, Muster 3): grün zu gelb, Kauf 2409 zu 2919, Miete 9.4 zu 9.4
- Eching (09274124, ergebnis2, Muster 1, 3): unbewertet zu gelb, Kauf None zu 4193, Miete 12.71 zu 12.82
- Neureichenau (09272136, ergebnis2, Muster 4): gelb zu grün, Kauf 950 zu 1060, Miete 8.2 zu 8.2
- Freudenberg (09371122, ergebnis2, Muster 1): rot zu gelb, Kauf 3638 zu 2873, Miete 7.14 zu 9.49
- Oberaurach (09674159, ergebnis2, Muster 3): grün zu gelb, Kauf 1750 zu 1500, Miete 8.02 zu 8.02
- Eschau (09676123, ergebnis2, Muster 3): grün zu gelb, Kauf 2250 zu 1900, Miete 9.5 zu 9.5
- Mistelgau (09472167, ergebnis2, Muster 3): grün zu gelb, Kauf 1925 zu 1950, Miete 10.41 zu 10.41
- Bodenmais (09276117, ergebnis2, Muster 3): grün zu gelb, Kauf 1950 zu 2200, Miete 9.56 zu 9.56
- Freudenberg (08128039, ergebnis2, Muster 1): unbewertet zu gelb, Kauf None zu 3075, Miete 10.01 zu 9.47
- Thalmassing (09375205, ergebnis2, Muster 2): grün zu gelb, Kauf 3183 zu 3835, Miete 11.55 zu 11.55
- Gundelsheim (09471137, ergebnis2, Muster 1): gelb zu grün, Kauf 3070 zu 3251, Miete 11.87 zu 12.38
- Luhe-Wildenau (09374133, ergebnis2, Muster 3): grün zu gelb, Kauf 1950 zu 2100, Miete 9.23 zu 9.23
- Falkenstein (09372125, ergebnis2, Muster 3): grün zu gelb, Kauf 1570 zu 1140, Miete 9.85 zu 9.85
- Bischofsmais (09276116, ergebnis2, Muster 3): grün zu gelb, Kauf 1775 zu 1850, Miete 8.47 zu 8.47
- Rinchnach (09276139, ergebnis2, Muster 3): grün zu gelb, Kauf 1441 zu 1182, Miete 8.23 zu 8.23
- Schmidgaden (09376159, ergebnis2, Muster 3): grün zu gelb, Kauf 2225 zu 1950, Miete 10.54 zu 10.54
- Schorndorf (09372158, ergebnis2, Muster 1, 3): unbewertet zu gelb, Kauf None zu 2181, Miete 9.2 zu 8.73
- Wald (09372169, ergebnis2, Muster 3): grün zu gelb, Kauf 2508 zu 3016, Miete 8.97 zu 8.97
- Rain (09278177, ergebnis2, Muster 1, 3): unbewertet zu gelb, Kauf None zu 3355, Miete 10.77 zu 10.12
- Waischenfeld (09472197, ergebnis2, Muster 3): grün zu gelb, Kauf 1975 zu 2050, Miete 8.54 zu 8.54
- Hemmingen (08118027, ergebnis3, Muster 1): gelb zu grün, Kauf 3353 zu 3257, Miete 13.9 zu 13.77
- Grafenau (08115054, ergebnis3, Muster 1): gelb zu grün, Kauf 4058 zu 3782, Miete 13.46 zu 13.63

## Geänderte Quellen (Muster 1 und 2)

- babenhausen (09778115): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Babenhausen-Schwaben/Babenhausen/ (Wert 1833.33); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Babenhausen-Schwaben/Babenhausen/ (Wert 10.87)
- isen (09177123): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/heldenstein (Wert 3300.0); homeday Miete: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/heldenstein (Wert 8.8)
- wartenberg (09177143): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Wartenberg-Oberbayern/Wartenberg/ (Wert 4462.83); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Wartenberg-Oberbayern/Wartenberg/ (Wert 12.9)
- denkendorf (09176120): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Denkendorf-Oberbayern/Denkendorf/ (Wert 3119.48); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Denkendorf-Oberbayern/Denkendorf/ (Wert 8.97)
- voehringen (08325061): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Voehringen-Wuerttemberg/Voehringen/ (Wert 1840.21); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Voehringen-Wuerttemberg/Voehringen/ (Wert 11.47)
- bockhorn (09177113): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Bockhorn-Oberbayern/Bockhorn/ (Wert 3916.52); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Bockhorn-Oberbayern/Bockhorn/ (Wert 11.62)
- steinach-08317129 (08317129): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Steinach-Baden/Steinach/ (Wert 2766.62); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Steinach-Baden/Steinach/ (Wert 9.33)
- hohenstein (08415090): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Hohenstein-Wuerttemberg/Hohenstein/ (Wert 2694.29); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Hohenstein-Wuerttemberg/Hohenstein/ (Wert 8.03)
- buxheim-09176118 (09176118): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Buxheim-Oberbayern/Buxheim/ (Wert 4558.45); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Buxheim-Oberbayern/Buxheim/ (Wert 9.64)
- ortenberg (08317100): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Ortenberg-Baden/Ortenberg/ (Wert 3455.08); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Ortenberg-Baden/Ortenberg/ (Wert 12.94)
- illingen (08236028): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Illingen-Wuerttemberg/Illingen/ (Wert 3090.07); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Illingen-Wuerttemberg/Illingen/ (Wert 11.84)
- rosengarten (08127100): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Rosengarten-Wuerttemberg/Rosengarten/ (Wert 2392.02); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Rosengarten-Wuerttemberg/Rosengarten/ (Wert 11.19)
- seubersdorf-i-d-opf (09373160): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/seubersdorf+i.d.+opf./seubersdorf+in+der+oberpfalz+92358 (Wert 2400.0)
- lichtenau (08216028): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Lichtenau-Baden/Lichtenau/ (Wert 2506.58); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Lichtenau-Baden/Lichtenau/ (Wert 9.32)
- bischofsheim-i-d-rhoen (09673117): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/bischofsheim+a.d.+rhoen (Wert 2000.0); homeday Miete: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/bischofsheim+a.d.+rhoen (Wert 5.8)
- eching (09274124): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Eching-Niederbayern/Eching/ (Wert 4192.53); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Eching-Niederbayern/Eching/ (Wert 12.93)
- freudenberg-09371122 (09371122): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Freudenberg-Oberpfalz/Freudenberg/ (Wert 2872.92); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Freudenberg-Oberpfalz/Freudenberg/ (Wert 8.2)
- hausen (09474134): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Hausen-Oberfranken/Hausen/ (Wert 4014.9); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Hausen-Oberfranken/Hausen/ (Wert 8.94)
- freudenberg-08128039 (08128039): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Freudenberg-Baden/Freudenberg/ (Wert 3075.22); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Freudenberg-Baden/Freudenberg/ (Wert 8.93)
- thalmassing (09375205): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/thalmaessing (Wert 2650.0); homeday Miete: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/thalmaessing (Wert 7.7)
- gundelsheim-09471137 (09471137): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Gundelsheim-Oberfranken/Gundelsheim/ (Wert 3612.54); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Gundelsheim-Oberfranken/Gundelsheim/ (Wert 12.6)
- schorndorf (09372158): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Schorndorf-Oberpfalz/Schorndorf/ (Wert 2180.89); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Schorndorf-Oberpfalz/Schorndorf/ (Wert 8.47)
- waldenburg (08126085): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Waldenburg-Wuerttemberg/Waldenburg/ (Wert 3646.17); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Waldenburg-Wuerttemberg/Waldenburg/ (Wert 11.93)
- rain-09278177 (09278177): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Rain-Niederbayern/Rain/ (Wert 3355.3); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Rain-Niederbayern/Rain/ (Wert 9.46)
- bruehl (08226009): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Bruehl-Baden/Bruehl/ (Wert 3455.93); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Bruehl-Baden/Bruehl/ (Wert 12.06)
- hemmingen (08118027): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Hemmingen-Wuerttemberg/Hemmingen/ (Wert 3160.1); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Hemmingen-Wuerttemberg/Hemmingen/ (Wert 13.51)
- grafenau (08115054): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Grafenau-Wuerttemberg/Grafenau/ (Wert 3506.59); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Grafenau-Wuerttemberg/Grafenau/ (Wert 13.97)
