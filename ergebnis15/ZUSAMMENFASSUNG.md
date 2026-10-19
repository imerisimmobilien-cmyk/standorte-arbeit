# Zusammenfassung ergebnis15: zurückgehaltene Änderungen aus ergebnis13, mit korrigierter Ausreißerregel

Datei: `ergebnis15/patch-e-01.json`, Format wie ergebnis13. Ausgangsstand ist derselbe wie bei ergebnis13: ergebnis2 und ergebnis3 mit den Patches aus ergebnis4 und ergebnis8, ohne ergebnis13. Branch: `claude/laughing-sagan-q2wyfw`.

## Korrigierte Regel

- Ausreißer werden nur unter den Portalwerten bestimmt (immoportal, homeday, miete-aktuell und gegebenenfalls Ersatzquellen), ohne Gutachterwert. Kriterium: Ein Wert liegt mehr als 50 % über der nächsten Portalquelle. Die Regel für zu niedrige Werte bleibt: unter 60 % des Medians der übrigen Portalwerte, ebenfalls ohne Gutachterwert.
- Die Ortsprüfung (Abweichung über 25 %) rechnet ebenfalls ohne Gutachterwert.
- Ersatz nach gestrichenem Ausreißer: zuerst ohne-makler.net, dann Engel & Völkers, jeweils nur nach Landkreis-Prüfung. Die Ersatzwerte aus dem Nachabruf (Block 06) sind dafür jetzt bei allen Orten hinterlegt, nicht nur bei den dünnen. Benutzt werden sie weiterhin nur, wenn weniger als zwei Auftragsquellen übrig sind.
- Unverändert gilt: Der Gutachterwert zählt erst ab zwei Portalwerten und nur bis 40 % Abweichung vom Median der Portalwerte. Ohne Prognose ist die Ampel höchstens gelb.

## Ergebnis

- In patch-d-01.json haben 59 Orte eine Änderung von Ampel oder Kaufwert mit Muster 3 oder 4. Alle stehen in patch-e-01.json, neu gerechnet mit der korrigierten Regel. Die 22 lokal schon eingespielten Orte kann ich nicht erkennen, sie sind deshalb enthalten und lokal auszusortieren.
- Je Ort steht in `ergebnis13` der Wert aus patch-d-01.json und in `korrekturWirkung`, ob sich durch die Korrektur etwas ändert: 26 Orte anders als ergebnis13, 33 gleich.
- Ampelwechsel gegenüber dem Stand vor ergebnis13: 21 (unbewertet zu gelb 4, gelb zu rot 3, grün zu gelb 12, gelb zu grün 2).
- Die sieben in der lokalen Prüfung genannten Orte (Emskirchen, Oberaurach, Mistelgau, Waischenfeld, Bodenmais, Luhe-Wildenau, Bischofsmais) bleiben mit der korrigierten Regel grün. Ihre Kaufwerte ändern sich leicht, weil die Ersatzquelle mitzählt.
- Über alle 1300 Orte von ergebnis2 und ergebnis3 ändern sich durch die Korrektur 58 Orte in Kauf, Miete oder Ampel, gemessen am Stand nach ergebnis13. Die übrigen Orte außerhalb dieser 59 sind hier nicht als Patch geliefert. Auf Wunsch liefere ich sie nach.

## Ampelwechsel (gegenüber dem Stand vor ergebnis13)

- Babenhausen (09778115, ergebnis2): unbewertet zu gelb, Kauf None zu 1833, Miete 10.38 zu 10.62 (gleich wie ergebnis13)
- Isen (09177123, ergebnis2): gelb zu rot, Kauf 4043 zu 4750, Miete 12.25 zu 12.25 (anders als ergebnis13)
- Seeon-Seebruck (09189143, ergebnis2): gelb zu rot, Kauf 4450 zu 5000, Miete 12.99 zu 12.99 (gleich wie ergebnis13)
- Haldenwang (09780122, ergebnis2): grün zu gelb, Kauf 3547 zu 3494, Miete 13.11 zu 13.11 (gleich wie ergebnis13)
- Buxheim (09778123, ergebnis2): grün zu gelb, Kauf 3584 zu 3768, Miete 12.94 zu 12.94 (gleich wie ergebnis13)
- Auerbach i.d.OPf. (09371113, ergebnis2): grün zu gelb, Kauf 2044 zu 1889, Miete 8.04 zu 8.04 (gleich wie ergebnis13)
- Altenkunstadt (09478111, ergebnis2): grün zu gelb, Kauf 1700 zu 1400, Miete 7.96 zu 7.96 (gleich wie ergebnis13)
- Oberkotzau (09475158, ergebnis2): gelb zu grün, Kauf 1350 zu 1338, Miete 7.79 zu 7.79 (anders als ergebnis13)
- Erbendorf (09377116, ergebnis2): grün zu gelb, Kauf 1900 zu 1900, Miete 9.42 zu 9.42 (gleich wie ergebnis13)
- Hollfeld (09472154, ergebnis2): grün zu gelb, Kauf 1850 zu 1800, Miete 8.37 zu 8.37 (gleich wie ergebnis13)
- Leidersbach (09676136, ergebnis2): grün zu gelb, Kauf 2400 zu 3025, Miete 10.41 zu 10.41 (anders als ergebnis13)
- Eching (09274124, ergebnis2): unbewertet zu gelb, Kauf None zu 4193, Miete 12.71 zu 12.82 (gleich wie ergebnis13)
- Neureichenau (09272136, ergebnis2): gelb zu grün, Kauf 950 zu 1060, Miete 8.2 zu 8.2 (gleich wie ergebnis13)
- Eschau (09676123, ergebnis2): grün zu gelb, Kauf 2250 zu 3036, Miete 9.5 zu 9.5 (anders als ergebnis13)
- Falkenstein (09372125, ergebnis2): grün zu gelb, Kauf 1570 zu 1140, Miete 9.85 zu 9.85 (gleich wie ergebnis13)
- Rinchnach (09276139, ergebnis2): grün zu gelb, Kauf 1441 zu 1182, Miete 8.23 zu 8.23 (gleich wie ergebnis13)
- Schmidgaden (09376159, ergebnis2): grün zu gelb, Kauf 2225 zu 1950, Miete 10.54 zu 10.54 (gleich wie ergebnis13)
- Schorndorf (09372158, ergebnis2): unbewertet zu gelb, Kauf None zu 2181, Miete 9.2 zu 8.73 (gleich wie ergebnis13)
- Wald (09372169, ergebnis2): grün zu gelb, Kauf 2508 zu 3016, Miete 8.97 zu 8.97 (gleich wie ergebnis13)
- Rain (09278177, ergebnis2): unbewertet zu gelb, Kauf None zu 3191, Miete 10.77 zu 10.12 (anders als ergebnis13)
- Schwarzach (09278187, ergebnis2): gelb zu rot, Kauf 2768 zu 3099, Miete 8.48 zu 8.48 (anders als ergebnis13)
