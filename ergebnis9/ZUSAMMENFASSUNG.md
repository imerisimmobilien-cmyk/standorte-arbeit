# Zusammenfassung Block 11 (Berlin-Umland, Brandenburg), 148 Gemeinden

Dateien: `ergebnis9/lieferung-01.json` bis `lieferung-03.json`. Branch: `claude/laughing-sagan-q2wyfw`. Verfahren wie Block 05 und 07 in der jetzigen Fassung, mit allen Regeln aus Block 06 und 10: Ortsbestätigung je Quelle (streng bei gleichnamigen Orten), Mietpreisbremse und Kappung per Gemeindeschlüssel, Gutachter-Kreiswert nur bis 40 % Abweichung, Ersatzquellen nur bei weniger als zwei Auftragsquellen, Prognose mit Basis- und Zieljahr wie im Profil, Rendite auf eine Nachkommastelle (ab 4,25 % grün bei mindestens zwei Quellen). Fehlende Werte sind null, es gibt keine Landkreis- oder Nachbarortwerte als Ersatz.

## Ampel

- gesamt: grün 68, gelb 70, rot 8, unbewertet 2
- rot wegen Prognose-Deckel: 20

## Unbewertete Orte (2)

- Golzow (12069216, 1372 Einwohner): Kauf 2650, Miete None
- Schönwald (12061435, 1226 Einwohner): Kauf None, Miete None

## Quellenlücken

- dünne Datenbasis (weniger als zwei Quellen bei Kauf oder Miete), aber bewertet: 35
- mit Ersatzquelle (ohne-makler.net oder Engel & Völkers): 17
- Ortsverwechslung bereinigt (strenge Prüfung): 3
- Gutachter-Kreiswert nicht gewertet (über 40 %): 0
- fehlende Auftragsquellen je Ort: Kauf ohne immoportal 102, Miete ohne immoportal 94, Miete ohne miet-check 33, Kauf ohne miete-aktuell 11, Miete ohne miete-aktuell 11, Kauf ohne homeday 4
- ohne Prognose: 0
- Prognose-Zeiträume: 2023 bis 2040: 148

## Weitere Angaben

- Mietpreisbremse laut amtlicher Liste: 25 Orte (Blankenfelde-Mahlow, Panketal, Kleinmachnow, Stahnsdorf, Mühlenbecker Land, Fredersdorf-Vogelsdorf, Ahrensfelde, Brieselang, Glienicke/Nordbahn, Erkner, Zeuthen, Wildau, Schönwalde-Glien, Schulzendorf, Altlandsberg, Bestensee, Großbeeren, Nuthetal, Grünheide (Mark), Woltersdorf, Birkenwerder, Leegebruch, Eichwalde, Biesenthal, Rehfelde)
- Arbeitgeber aus dem Wikipedia-Artikel belegt: 3 Orte. Bei den übrigen nennt der Artikel keine Firma mit Beschäftigtenzahl am Ort, das Feld bleibt null.
- Hochwasser, amtlicher Mietspiegel, Pendler und Leerstand sind nicht erhoben.


## Regulierung und Prognose in diesem Block

- Mietpreisbremse: Mietpreisbegrenzungsverordnung Brandenburg vom 3.12.2025 (GVBl. II 2025 Nr. 95, gültig 1.1.2026 bis 31.12.2029), 36 Gemeinden. Kappung 15 % laut Kappungsgrenzenverordnung vom 3.12.2025 (GVBl. II 2025 Nr. 94) für dieselben Gemeinden. Der Abgleich läuft über den Gemeindeschlüssel.
- Prognose: Bevölkerungsvorausschätzung 2024 bis 2040 des Landesamts für Bauen und Verkehr und des Amts für Statistik Berlin-Brandenburg, Tabellenanhang, mittlere Variante, Entwicklung 2023 bis 2040. Werte gibt es für amtsfreie Gemeinden. Bei amtsangehörigen Gemeinden ist der Wert des Amts angegeben, mit Ebene im Feld `prognose.ebene`.

## Zusatzort Oelsnitz/Vogtl. (Sachsen, ags 14523300)

Eigene Datei: `ergebnis9/oelsnitz-vogtl.json`. Nicht verwechselt mit Oelsnitz/Erzgeb. (14521450). Die Seiten sind über Nachbarorte im Vogtlandkreis bestätigt.

- Kauf 661 €/m², Miete 5,99 €/m², Ampel rot mit Prognose-Deckel. Die Prognose der Bertelsmann Stiftung für 2020 bis 2040 liegt bei minus 15,6 %. Das Datenblatt des Statistischen Landesamts Sachsen war nicht abrufbar.
- Keine Mietpreisbremse und Kappung 20 %. In Sachsen gelten beide Regeln nur für Dresden und Leipzig.
- Wird dort gekauft? Ja, aber wenig. Der Grundstücksmarktbericht 2025 des Gutachterausschusses im Vogtlandkreis (Auswertung 2023 bis 2024) zählt 43 Erwerbsvorgänge im Teilmarkt Wohnungs- und Teileigentum. Die Weiterverkäufe von Eigentumswohnungen (Tab. 64) verteilen sich so:
  - bis 1949, saniert: 633 €/m² im Mittel (Median 555), 10 Fälle
  - 1950 bis 1975: 516 €/m² (Median 538), 7 Fälle
  - 1976 bis 1990: 508 €/m², 1 Fall
  - ab 1991: 967 €/m², 2 Fälle
  
  Quelle: https://www.vogtlandkreis.de/media/custom/3434_6169_1.PDF. Der daraus gewichtete Gemeindewert von 619 €/m² geht als vierte Quelle in den Kaufpreis ein.
