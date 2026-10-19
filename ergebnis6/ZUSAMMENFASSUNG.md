# Zusammenfassung Block 08 (Bayern, restliche Gemeinden), 993 Gemeinden

Dateien: `ergebnis6/lieferung-01.json` bis `lieferung-20.json`. Branch: `claude/laughing-sagan-q2wyfw`. Verfahren wie Block 05 und 07 in der jetzigen Fassung, mit allen Regeln aus Block 06 und 10: Ortsbestätigung je Quelle (streng bei gleichnamigen Orten), Mietpreisbremse und Kappung per Gemeindeschlüssel, Gutachter-Kreiswert nur bis 40 % Abweichung, Ersatzquellen nur bei weniger als zwei Auftragsquellen, Prognose mit Basis- und Zieljahr wie im Profil, Rendite auf eine Nachkommastelle (ab 4,25 % grün bei mindestens zwei Quellen). Fehlende Werte sind null, es gibt keine Landkreis- oder Nachbarortwerte als Ersatz.

## Ampel

- gesamt: grün 294, gelb 620, rot 40, unbewertet 39
- Ampel durch Prognose-Deckel begrenzt (gelb oder rot): 70

## Unbewertete Orte (39)

- Breitenbrunn (09778121, 2280 Einwohner): Kauf None, Miete 10.7
- Oberhausen (09190135, 2129 Einwohner): Kauf None, Miete 13.56
- Holzheim (09775126, 1971 Einwohner): Kauf None, Miete 12.76
- Eurasburg (09771129, 1838 Einwohner): Kauf None, Miete None
- Schwenningen (09773164, 1399 Einwohner): Kauf None, Miete 6.82
- Münster (09779187, 1228 Einwohner): Kauf None, Miete 11.37
- Kirchberg (09177124, 1170 Einwohner): Kauf None, Miete 11.29
- Ehingen (09772134, 1163 Einwohner): Kauf None, Miete 11.02
- Holzheim (09779163, 1141 Einwohner): Kauf None, Miete 10.67
- Schönberg (09183143, 1131 Einwohner): Kauf None, Miete None
- Wiesenbach (09774189, 1024 Einwohner): Kauf None, Miete 10.61
- Sankt Oswald-Riedlhütte (09272143, 2944 Einwohner): Kauf 1900, Miete None
- Bad Weißenstadt (09479166, 2880 Einwohner): Kauf 1550, Miete None
- Neukirchen b.Sulzbach-Rosenberg (09371141, 2514 Einwohner): Kauf 2150, Miete None
- Auerbach (09271113, 2125 Einwohner): Kauf None, Miete 9.59
- Birkenfeld (09677119, 2176 Einwohner): Kauf None, Miete 9.5
- Haibach (09278129, 2036 Einwohner): Kauf None, Miete 10.16
- Feldkirchen (09278121, 1999 Einwohner): Kauf None, Miete 10.58
- Mühlhausen (09572143, 1845 Einwohner): Kauf None, Miete 9.83
- Tiefenbach (09372163, 1871 Einwohner): Kauf None, Miete 6.94
- Rettenbach (09372150, 1788 Einwohner): Kauf None, Miete 9.97
- Sulzfeld (09673173, 1751 Einwohner): Kauf None, Miete 8.0
- Schneeberg (09676156, 1762 Einwohner): Kauf None, Miete 7.87
- Velden (09574160, 1712 Einwohner): Kauf None, Miete 9.32
- Wilhelmsdorf (09575181, 1430 Einwohner): Kauf None, Miete 11.84
- Neunkirchen (09676143, 1428 Einwohner): Kauf None, Miete 6.3
- Bad Neualbenreuth (09377142, 1412 Einwohner): Kauf 1725, Miete None
- Oberreichenbach (09572147, 1334 Einwohner): Kauf None, Miete 10.14
- Glashütten (09472141, 1284 Einwohner): Kauf None, Miete 10.83
- Bruckberg (09571122, 1252 Einwohner): Kauf None, Miete 9.58
- Kohlberg (09374131, 1190 Einwohner): Kauf None, Miete 7.98
- Bergen (09577115, 1157 Einwohner): Kauf None, Miete None
- Stockheim (09673170, 1025 Einwohner): Kauf None, Miete None
- Wettringen (09571222, 983 Einwohner): Kauf None, Miete 9.48
- Holzkirchen (09679149, 936 Einwohner): Kauf None, Miete 10.31
- Falkenberg (09377117, 920 Einwohner): Kauf None, Miete 8.33
- Adelshofen (09571111, 908 Einwohner): Kauf None, Miete 9.6
- Hausen (09673129, 690 Einwohner): Kauf None, Miete None
- Weiding (09376176, 461 Einwohner): Kauf None, Miete 8.62

## Quellenlücken

- dünne Datenbasis (weniger als zwei Quellen bei Kauf oder Miete), aber bewertet: 87
- mit Ersatzquelle (ohne-makler.net oder Engel & Völkers): 69
- Ortsverwechslung bereinigt (strenge Prüfung): 67
- Gutachter-Kreiswert nicht gewertet (über 40 %): 30
- fehlende Auftragsquellen je Ort: Kauf ohne immoportal 992, Miete ohne immoportal 991, Kauf ohne homeday 89, Miete ohne miet-check 88, Kauf ohne miete-aktuell 61, Miete ohne miete-aktuell 61
- ohne Prognose: 0
- Prognose-Zeiträume: 2024 bis 2038: 992, 2024 bis 2044: 1

## Weitere Angaben

- Mietpreisbremse laut amtlicher Liste: 0 Orte
- Arbeitgeber aus dem Wikipedia-Artikel belegt: 14 Orte. Bei den übrigen nennt der Artikel keine Firma mit Beschäftigtenzahl am Ort, das Feld bleibt null.
- Hochwasser, amtlicher Mietspiegel, Pendler und Leerstand sind nicht erhoben.


## Hinweise zu diesem Block

- Die übergebene Liste enthielt 993 Gemeindeschlüssel, nicht 996. Alle 993 sind bewertet, keiner davon war schon in einem früheren Block.
- Prognose: Demographie-Spiegel des Bayerischen Landesamts für Statistik. Basis- und Zieljahr sind wie im jeweiligen Gemeindeprofil angegeben, bei kleinen Gemeinden meist 2024 bis 2038.
- Die Mietpreisbremse ist per Gemeindeschlüssel gegen die Anlage der Mieterschutzverordnung Bayern abgeglichen (Begründung BayMBl. 2025 Nr. 558, Reut seit 16.06.2026 gestrichen).
