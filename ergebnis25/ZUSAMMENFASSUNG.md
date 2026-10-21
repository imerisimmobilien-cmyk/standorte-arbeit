# ergebnis25

## Teil 1: miete-aktuell-Prüfung 2026 rückwirkend (Berlin und Potsdam)

Alle 238 miete-aktuell-Ortsteilseiten aus ergebnis21 (Berlin) und ergebnis18/21 (Potsdam) wurden per Skript neu gelesen, ohne neue Quellensuche. Gewertet wird der Wert der Zeile 2026 in der Verlaufstabelle; weicht der gelesene Wert davon ab, gilt der Wert 2026. Ein Sprung von mehr als 50 % gegenüber 2025 gilt als Portalfehler und wird nicht gewertet.

- Berlin: 88 miete-aktuell-Mieten wichen vom Wert 2026 ab und wurden korrigiert. Bei 81 Ortsteilen ändert sich dadurch die Miete; diese stehen im Patch. Ohne Wirkung auf das Mittel und daher nicht im Patch: Kreuzberg (Friedrichshain-Kreuzberg) (17,01 → 17,82), Gatow (Spandau) (17,57 → 16,49), Lichterfelde (Steglitz-Zehlendorf) (14,88 → 14,60), Oberschöneweide (Treptow-Köpenick) (14,73 → 14,71), Kaulsdorf (Marzahn-Hellersdorf) (17,01 → 16,43), Hellersdorf (Marzahn-Hellersdorf) (14,88 → 15,27), Friedrichsfelde (Lichtenberg) (15,26 → 15,28) (Wert dort nicht gewertet, etwa als Dublette, oder Mittel nach Rundung gleich).
- Berlin Kauf: keine Abweichung, alle miete-aktuell-Kaufwerte entsprachen dem Wert 2026.
- Potsdam: alle Mieten entsprachen dem Wert 2026. Berliner Vorstadt Kauf: 2.297,50 €/m² gegenüber 5.757,38 €/m² im Jahr 2025 (-60 %), also Portalfehler, nicht gewertet. Der Kauf kommt damit wieder aus immoportal (5.683 €/m²), die Ampel wechselt von gelb auf rot (Stand vor ergebnis21).
- Die 12 Bezirkseinträge sind mitgeliefert, weil sich die Ortsteilliste in stufe2 ändert; Kauf, Miete und Ampel der Bezirke bleiben gleich.

Dateien: `patch-ergebnis17-berlin-01.json` (93 Einträge, ersetzen die Einträge aus ergebnis21), `patch-ergebnis18-teil2-ortsteile-01.json` (1 Eintrag). Jeder Eintrag trägt `nachtrag25` mit den Werten vorher und dem Grund.

### Ampelwechsel

| Ort | Miete alt | Miete neu | Kauf alt | Kauf neu | Ampel alt | Ampel neu |
|---|---|---|---|---|---|---|
| Neukölln (Neukölln) | 15,21 | 14,93 | 5.444 | 5.444 | gelb | rot |
| Rummelsburg (Lichtenberg) | 15,07 | 15,54 | 5.544 | 5.544 | rot | gelb |
| Berliner Vorstadt (Potsdam) | 14,73 | 14,73 | 2.298 | 5.683 | gelb | rot |

### Alle geänderten Orte

| Ort | miete-aktuell gelesen | miete-aktuell 2026 | Miete alt (Mittel) | Miete neu (Mittel) | Ampel |
|---|---|---|---|---|---|
| Mitte (Mitte) | 21,75 | 20,59 | 19,30 | 18,71 | rot |
| Moabit (Mitte) | 19,57 | 19,40 | 17,70 | 17,61 | gelb |
| Hansaviertel (Mitte) | 21,89 | 22,12 | 19,88 | 19,99 | gelb |
| Tiergarten (Mitte) | 19,29 | 19,41 | 18,09 | 18,15 | gelb |
| Wedding (Mitte) | 14,61 | 14,03 | 14,33 | 14,04 | gelb |
| Friedrichshain (Friedrichshain-Kreuzberg) | 18,70 | 18,92 | 17,38 | 17,49 | gelb |
| Prenzlauer Berg (Pankow) | 17,27 | 17,01 | 16,50 | 16,37 | rot |
| Weißensee (Pankow) | 16,33 | 15,66 | 15,76 | 15,53 | gelb |
| Blankenburg (Pankow) | 8,66 | 8,73 | 10,14 | 10,18 | rot |
| Heinersdorf (Pankow) | 17,74 | 18,42 | 17,46 | 17,80 | grün |
| Karow (Pankow) | 11,21 | 10,73 | 12,12 | 11,88 | rot |
| Stadtrandsiedlung Malchow (Pankow) | 15,23 | 14,26 | 14,21 | 13,72 | gelb |
| Pankow (Pankow) | 15,91 | 15,97 | 15,16 | 15,20 | rot |
| Blankenfelde (Pankow) | 17,88 | 17,13 | 16,91 | 16,53 | grün |
| Buch (Pankow) | 11,08 | 10,73 | 12,27 | 12,10 | rot |
| Französisch Buchholz (Pankow) | 17,30 | 17,04 | 16,11 | 16,02 | gelb |
| Niederschönhausen (Pankow) | 15,58 | 16,14 | 15,58 | 16,14 | gelb |
| Rosenthal (Pankow) | 15,60 | 15,95 | 15,60 | 15,95 | gelb |
| Wilhelmsruh (Pankow) | 15,94 | 15,31 | 15,88 | 15,57 | grün |
| Charlottenburg (Charlottenburg-Wilmersdorf) | 17,16 | 17,36 | 16,35 | 16,45 | gelb |
| Wilmersdorf (Charlottenburg-Wilmersdorf) | 18,67 | 17,76 | 17,57 | 17,12 | gelb |
| Schmargendorf (Charlottenburg-Wilmersdorf) | 19,31 | 20,73 | 18,78 | 19,25 | gelb |
| Grunewald (Charlottenburg-Wilmersdorf) | 19,75 | 19,91 | 18,74 | 18,79 | gelb |
| Westend (Charlottenburg-Wilmersdorf) | 17,02 | 16,98 | 15,63 | 15,62 | rot |
| Halensee (Charlottenburg-Wilmersdorf) | 18,83 | 18,00 | 19,15 | 18,73 | gelb |
| Spandau (Spandau) | 12,21 | 12,29 | 13,12 | 13,15 | grün |
| Haselhorst (Spandau) | 11,02 | 11,15 | 12,88 | 12,95 | gelb |
| Siemensstadt (Spandau) | 12,30 | 11,99 | 13,42 | 13,32 | grün |
| Staaken (Spandau) | 11,18 | 11,30 | 12,12 | 12,19 | grün |
| Kladow (Spandau) | 16,57 | 17,74 | 16,57 | 17,74 | gelb |
| Hakenfelde (Spandau) | 13,00 | 12,43 | 14,43 | 14,24 | grün |
| Wilhelmstadt (Spandau) | 12,90 | 13,00 | 13,53 | 13,57 | grün |
| Steglitz (Steglitz-Zehlendorf) | 16,82 | 15,86 | 16,40 | 15,92 | gelb |
| Lankwitz (Steglitz-Zehlendorf) | 12,92 | 13,70 | 13,81 | 14,07 | gelb |
| Zehlendorf (Steglitz-Zehlendorf) | 16,45 | 16,29 | 16,11 | 16,03 | gelb |
| Dahlem (Steglitz-Zehlendorf) | 19,86 | 19,10 | 18,50 | 18,12 | gelb |
| Nikolassee (Steglitz-Zehlendorf) | 17,61 | 16,92 | 16,80 | 16,46 | gelb |
| Wannsee (Steglitz-Zehlendorf) | 15,40 | 14,66 | 15,95 | 15,58 | gelb |
| Schöneberg (Tempelhof-Schöneberg) | 16,79 | 17,39 | 16,26 | 16,56 | gelb |
| Tempelhof (Tempelhof-Schöneberg) | 14,75 | 14,20 | 14,93 | 14,65 | gelb |
| Mariendorf (Tempelhof-Schöneberg) | 15,09 | 14,70 | 15,16 | 14,96 | grün |
| Marienfelde (Tempelhof-Schöneberg) | 11,33 | 12,02 | 12,84 | 13,18 | gelb |
| Lichtenrade (Tempelhof-Schöneberg) | 11,56 | 12,40 | 12,60 | 13,02 | gelb |
| Neukölln (Neukölln) | 15,78 | 15,22 | 15,21 | 14,93 | gelb → rot |
| Britz (Neukölln) | 12,84 | 13,40 | 13,40 | 13,59 | gelb |
| Buckow (Neukölln) | 11,94 | 12,36 | 13,27 | 13,41 | gelb |
| Rudow (Neukölln) | 11,09 | 10,90 | 12,23 | 12,17 | gelb |
| Gropiusstadt (Neukölln) | 11,61 | 12,41 | 13,03 | 13,43 | gelb |
| Alt-Treptow (Treptow-Köpenick) | 11,86 | 12,44 | 12,95 | 13,23 | rot |
| Plänterwald (Treptow-Köpenick) | 11,84 | 12,64 | 12,74 | 13,14 | rot |
| Baumschulenweg (Treptow-Köpenick) | 13,34 | 13,62 | 13,39 | 13,48 | gelb |
| Johannisthal (Treptow-Köpenick) | 15,36 | 16,02 | 15,27 | 15,61 | grün |
| Niederschöneweide (Treptow-Köpenick) | 15,37 | 15,47 | 16,37 | 16,40 | grün |
| Adlershof (Treptow-Köpenick) | 15,66 | 15,47 | 16,93 | 16,83 | grün |
| Bohnsdorf (Treptow-Köpenick) | 15,06 | 14,33 | 15,11 | 14,74 | grün |
| Köpenick (Treptow-Köpenick) | 15,73 | 16,05 | 15,58 | 15,69 | grün |
| Friedrichshagen (Treptow-Köpenick) | 11,17 | 11,29 | 13,32 | 13,36 | rot |
| Rahnsdorf (Treptow-Köpenick) | 14,40 | 15,40 | 15,05 | 15,38 | gelb |
| Grünau (Treptow-Köpenick) | 17,06 | 17,15 | 17,30 | 17,34 | grün |
| Müggelheim (Treptow-Köpenick) | 12,62 | 12,38 | 12,45 | 12,32 | grün |
| Schmöckwitz (Treptow-Köpenick) | 17,56 | 18,45 | 16,57 | 17,02 | grün |
| Marzahn (Marzahn-Hellersdorf) | 9,98 | 9,67 | 10,96 | 10,80 | gelb |
| Biesdorf (Marzahn-Hellersdorf) | 14,82 | 15,37 | 14,89 | 15,07 | grün |
| Mahlsdorf (Marzahn-Hellersdorf) | 15,62 | 15,31 | 15,80 | 15,64 | grün |
| Karlshorst (Lichtenberg) | 15,57 | 15,72 | 15,89 | 15,94 | gelb |
| Lichtenberg (Lichtenberg) | 13,17 | 12,86 | 13,19 | 13,04 | rot |
| Malchow (Lichtenberg) | 8,76 | 8,57 | 9,38 | 9,29 | gelb |
| Wartenberg (Lichtenberg) | 8,23 | 8,00 | 9,27 | 9,15 | rot |
| Neu-Hohenschönhausen (Lichtenberg) | 9,52 | 9,07 | 10,48 | 10,26 | gelb |
| Alt-Hohenschönhausen (Lichtenberg) | 12,32 | 12,56 | 12,45 | 12,57 | gelb |
| Rummelsburg (Lichtenberg) | 14,80 | 15,74 | 15,07 | 15,54 | rot → gelb |
| Reinickendorf (Reinickendorf) | 12,43 | 12,26 | 12,86 | 12,77 | gelb |
| Tegel (Reinickendorf) | 13,20 | 13,17 | 14,05 | 14,04 | grün |
| Konradshöhe (Reinickendorf) | 19,63 | 19,57 | 18,45 | 18,43 | grün |
| Heiligensee (Reinickendorf) | 17,18 | 16,50 | 16,88 | 16,54 | grün |
| Frohnau (Reinickendorf) | 14,34 | 14,26 | 14,84 | 14,80 | grün |
| Hermsdorf (Reinickendorf) | 15,07 | 14,67 | 15,46 | 15,25 | grün |
| Waidmannslust (Reinickendorf) | 10,86 | 10,32 | 10,86 | 10,32 | rot |
| Lübars (Reinickendorf) | 11,05 | 10,89 | 11,05 | 10,89 | rot |
| Wittenau (Reinickendorf) | 11,75 | 11,51 | 11,88 | 11,76 | gelb |
| Märkisches Viertel (Reinickendorf) | 7,64 | 7,75 | 8,26 | 8,32 | rot |
| Berliner Vorstadt (Potsdam) (Kauf) | Kauf 2.297,50 | Portalfehler | Kauf 2.298 | Kauf 5.683 | gelb → rot |

Auffällig: Niederschönhausen war mit 15,58 gelesen, der Wert 2026 ist 16,14 (Fehllesung eines Vorjahreswerts bestätigt). Größte Abweichungen: Kladow 16,57 → 17,74, Schmargendorf 19,31 → 20,73, Mitte 21,75 → 20,59.

## Teil 2: GENESIS-Online Baden-Württemberg

Genau ein Versuch am 21.10.2026 09:34 (erste Gemeinde der Liste, Bad Bellingen): Fehler „Tabelle nicht lesbar“. Wie vorgegeben abgebrochen, kein weiterer Versuch. Für folgende 20 Gemeinden bleibt die Bevölkerungsvorausberechnung offen (weiter Wegweiser-Kommune bzw. bisheriger Stand):

- Bad Bellingen (08336006)
- Stegen (08315109)
- Rheinhausen im Breisgau (08316053)
- Freiamt (08316054)
- Meißenheim (08317075)
- Riegel am Kaiserstuhl (08316037)
- Biberach (08317011)
- Sasbach am Kaiserstuhl (08316038)
- Malterdingen (08316024)
- Gottenheim (08315043)
- Eisenbach (Hochschwarzwald) (08315031)
- Hofstetten (08317046)
- Wittnau (08315125)
- Malsburg-Marzell (08336104)
- Wutach (08337127)
- Häg-Ehrsberg (08336106)
- Utzenfeld (08336090)
- Wembach (08336094)
- Ebringen (08315028)
- Pfaffenweiler (08315089)

## Offen und Kosten

- Offen: GENESIS BW für die 20 Gemeinden oben.
- Ungefährer Verbrauch dieses Auftrags: rund 3 bis 4 US-Dollar (Skriptlauf über 238 Seiten, Neuaufbau, ein GENESIS-Versuch).
- Kein Pull Request, nur Branch `claude/laughing-sagan-q2wyfw`.
