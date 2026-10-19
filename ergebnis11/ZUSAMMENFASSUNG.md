# Zusammenfassung Block 13 (Hessen, Gemeinden ab 5.000 Einwohnern), 265 Gemeinden

Dateien: `ergebnis11/lieferung-01.json` bis `lieferung-06.json`. Branch: `claude/laughing-sagan-q2wyfw`. Verfahren wie Block 05 und 07 in der jetzigen Fassung, mit allen Regeln aus Block 06 und 10: Ortsbestätigung je Quelle (streng bei gleichnamigen Orten), Mietpreisbremse und Kappung per Gemeindeschlüssel, Gutachter-Kreiswert nur bis 40 % Abweichung, Ersatzquellen nur bei weniger als zwei Auftragsquellen, Prognose mit Basis- und Zieljahr wie im Profil, Rendite auf eine Nachkommastelle (ab 4,25 % grün bei mindestens zwei Quellen). Fehlende Werte sind null, es gibt keine Landkreis- oder Nachbarortwerte als Ersatz.

## Ampel

- gesamt: grün 189, gelb 75, rot 1, unbewertet 0
- rot wegen Prognose-Deckel: 12

## Unbewertete Orte (0)

- keine

## Quellenlücken

- dünne Datenbasis (weniger als zwei Quellen bei Kauf oder Miete), aber bewertet: 24
- mit Ersatzquelle (ohne-makler.net oder Engel & Völkers): 4
- Ortsverwechslung bereinigt (strenge Prüfung): 3
- Gutachter-Kreiswert nicht gewertet (über 40 %): 0
- fehlende Auftragsquellen je Ort: Kauf ohne immoportal 91, Miete ohne immoportal 80, Kauf ohne homeday 10, Kauf ohne miete-aktuell 7, Miete ohne miete-aktuell 7, Miete ohne miet-check 7
- ohne Prognose: 2 (Höchst i. Odw., Allendorf (Eder))
- Prognose-Zeiträume: 2020 bis 2040: 263

## Weitere Angaben

- Mietpreisbremse laut amtlicher Liste: 33 Orte (Maintal, Griesheim, Kelkheim (Taunus), Weiterstadt, Friedrichsdorf, Pfungstadt, Groß-Gerau, Obertshausen, Bad Soden am Taunus, Flörsheim am Main, Nidderau, Heusenstamm, Eltville am Rhein, Kelsterbach, Ginsheim-Gustavsburg, Usingen, Schwalbach am Taunus, Raunheim, Groß-Zimmern, Hainburg, Langenselbold, Neu-Anspach, Bischofsheim, Rosbach v. d. Höhe, Roßdorf, Kriftel, Egelsbach, Steinbach (Taunus), Nauheim, Mainhausen, Fuldabrück, Biebesheim am Rhein, Walluf)
- Arbeitgeber aus dem Wikipedia-Artikel belegt: 15 Orte. Bei den übrigen nennt der Artikel keine Firma mit Beschäftigtenzahl am Ort, das Feld bleibt null.
- Hochwasser, amtlicher Mietspiegel, Pendler und Leerstand sind nicht erhoben.


## Regulierung und Prognose in diesem Block

- Mietpreisbremse und Kappung: Hessische Mieterschutzverordnung vom 18.11.2020 (GVBl. S. 802), geändert am 12.11.2025 (GVBl. 2025 Nr. 74), § 1, 49 Gemeinden, gültig bis 25.11.2026. Die geplante Neufassung mit 71 Gemeinden ist noch nicht in Kraft. Sobald sie gilt, sollte mpb neu abgeglichen werden.
- Prognose: Das Hessische Statistische Landesamt veröffentlicht keine freien Gemeindewerte. Genutzt ist deshalb die Bevölkerungsvorausberechnung 2020 bis 2040 der Bertelsmann Stiftung (Wegweiser Kommune), Ebene Gemeinde.
