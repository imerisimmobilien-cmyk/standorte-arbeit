# Zusammenfassung Block 05, 1000 Gemeinden

Ausgabe: `ergebnis2/lieferung-01.json` bis `lieferung-20.json` (je 50 Orte), Nachprüfung in `ergebnis2/NACHPRUEFUNG.md`. Branch: `claude/laughing-sagan-q2wyfw` (siehe `BRANCH.txt`), main ist unberührt. Quellen, Regeln und Korrekturen wie in Block 04 (zweite Fassung).

## Ampel

- gesamt (1000 Orte): grün 401, gelb 544, rot 40, unbewertet 15
- Bayern (604 Orte): grün 165, gelb 391, rot 39, unbewertet 9
- Baden-Württemberg (396 Orte): grün 236, gelb 153, rot 1, unbewertet 6

## Datenlage

- unbewertet (zu wenig Portaldaten): 15: Altenstadt, Bergen, Seeon-Seebruck, Ortenberg, Altenstadt, Oberhausen, Mühlhausen, Rosengarten, Lichtenau, Bischofsheim i.d.Rhön, Schönau, Freudenberg, Neukirchen b.Hl.Blut, Freudenberg, Gundelsheim
- Orte mit gestrichenem Wert (Ortsverwechslung oder Ausreißer): 62
- Orte mit dünner Datenbasis (weniger als zwei Quellen bei Kauf oder Miete): 179
- Orte mit Ersatzquelle: 300
- Orte ohne Landesamt-Prognose: 0
- Prognose bis Deckel rot (höchstens minus 15 Prozent): 1
- Mietpreisbremse laut amtlicher Liste: 0 Orte (Kappung 15 Prozent), übrige Kappung 20 Prozent

## Orte mit Ampel rot

- Oberstdorf (09780133)
- Pfronten (09777159)
- Altmannstein (09176112)
- Pöttmes (09771156)
- Schliersee (09182131)
- Rottach-Egern (09182129)
- Reichertshausen (09186146)
- Bad Hindelang (09780123)
- Bad Wiessee (09182111)
- Fridolfing (09189118)
- Eurasburg (09173123)
- Fuchstal (09181121)
- Buchenberg (09780117)
- Bockhorn (09177113)
- Pfaffing (09187159)
- Gerolsbach (09186125)
- Windach (09181146)
- Schnaitsee (09189142)
- Mettenheim (09183127)
- Weichs (09174151)
- Grainau (09180118)
- Ettringen (09778137)
- Halblech (09777173)
- Gaienhofen (08335025)
- Hilgertshausen-Tandern (09174147)
- Kirchanschöring (09189127)
- Polling (09183136)
- Ohlstadt (09180127)
- Schwangau (09777169)
- Babensham (09187116)
- Oberau (09180126)
- Fischen i.Allgäu (09780121)
- Burgberg i.Allgäu (09780118)
- Seeg (09777170)
- Soyen (09187176)
- Karlstein a.Main (09671114)
- Röthlein (09678170)
- Hohenthann (09274141)
- Eching (09274124)
- Hunderdorf (09278139)

## Hinweise

- Kauf ist der Mittelwert aus immoportal, homeday, miete-aktuell und für Bayern zusätzlich dem Kreiswert des Immobilienmarktberichts Bayern. Für Baden-Württemberg gibt es keinen freien Marktbericht.
- Miete ist der Mittelwert aus immoportal, miete-aktuell und miet-check, homeday nur daneben.
- Prognose Bayern: Demographie-Spiegel des Landesamts (2024 bis 2044). Prognose Baden-Württemberg: GENESIS 12421-0006 (2024 bis 2045, Hauptvariante mit Wanderung).
- Arbeitgeber, Pendler, Hochwasser, Leerstand und amtliche Mietspiegel wurden nicht erhoben.

