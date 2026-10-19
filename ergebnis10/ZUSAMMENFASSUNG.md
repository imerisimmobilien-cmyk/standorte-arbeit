# Zusammenfassung Block 12 (Hamburg-Umland, Schleswig-Holstein und Niedersachsen), 95 Gemeinden

Dateien: `ergebnis10/lieferung-01.json` bis `lieferung-02.json`. Branch: `claude/laughing-sagan-q2wyfw`. Verfahren wie Block 05 und 07 in der jetzigen Fassung, mit allen Regeln aus Block 06 und 10: Ortsbestätigung je Quelle (streng bei gleichnamigen Orten), Mietpreisbremse und Kappung per Gemeindeschlüssel, Gutachter-Kreiswert nur bis 40 % Abweichung, Ersatzquellen nur bei weniger als zwei Auftragsquellen, Prognose mit Basis- und Zieljahr wie im Profil, Rendite auf eine Nachkommastelle (ab 4,25 % grün bei mindestens zwei Quellen). Fehlende Werte sind null, es gibt keine Landkreis- oder Nachbarortwerte als Ersatz.

## Ampel

- gesamt: grün 51, gelb 44, rot 0, unbewertet 0
- Niedersachsen: grün 25, gelb 18, rot 0, unbewertet 0
- Schleswig-Holstein: grün 26, gelb 26, rot 0, unbewertet 0
- Ampel durch Prognose-Deckel begrenzt (gelb oder rot): 1

## Unbewertete Orte (0)

- keine

## Quellenlücken

- dünne Datenbasis (weniger als zwei Quellen bei Kauf oder Miete), aber bewertet: 10
- mit Ersatzquelle (ohne-makler.net oder Engel & Völkers): 0
- Ortsverwechslung bereinigt (strenge Prüfung): 1
- Gutachter-Kreiswert nicht gewertet (über 40 %): 0
- fehlende Auftragsquellen je Ort: Kauf ohne immoportal 55, Miete ohne immoportal 55, Miete ohne miet-check 2, Kauf ohne miete-aktuell 1, Miete ohne miete-aktuell 1, Kauf ohne homeday 1
- ohne Prognose: 23 (Appen, Börnsen, Moorrege, Bönningstedt, Ellerbek, Amt Neuhaus, Escheburg, Hasloh, Kisdorf, Groß Grönau, Hoisdorf, Bornhöved, Kölln-Reisiek, Dassendorf, Klein Nordende, Sülfeld, Lütjensee, Holm, Aumühle, Großenaspe, Rickling, Klein Offenseth-Sparrieshoop, Heist)
- Prognose-Zeiträume: 2020 bis 2040: 72

## Weitere Angaben

- Mietpreisbremse laut amtlicher Liste: 13 Orte (Seevetal, Buchholz in der Nordheide, Winsen (Luhe), Neu Wulmstorf, Tostedt, Adendorf, Bleckede, Reppenstedt, Bienenbüttel, Bardowick, Hanstedt, Deutsch Evern, Melbeck)
- Arbeitgeber aus dem Wikipedia-Artikel belegt: 3 Orte. Bei den übrigen nennt der Artikel keine Firma mit Beschäftigtenzahl am Ort, das Feld bleibt null.
- Hochwasser, amtlicher Mietspiegel, Pendler und Leerstand sind nicht erhoben.


## Regulierung und Prognose in diesem Block

- Schleswig-Holstein: keine Mietpreisbremse-Verordnung, mpb ist überall false. Die Kappung kommt aus der Kappungsgrenzenverordnung (seit 1.5.2024, 62 Gemeinden): 15 % bei gelisteten Gemeinden, sonst 20 %.
- Niedersachsen: Niedersächsische Mieterschutzverordnung vom 20.12.2024, Mietpreisbremse verlängert bis 31.12.2029, Kappung nach § 2. Mitglieder der gelisteten Samtgemeinden gelten als gelistet.
- Prognose: Die Landesämter von Schleswig-Holstein und Niedersachsen veröffentlichen keine freien Gemeindewerte. Genutzt ist deshalb die Bevölkerungsvorausberechnung 2020 bis 2040 der Bertelsmann Stiftung (Wegweiser Kommune). Bei Mitgliedern niedersächsischer Samtgemeinden ohne eigenen Wert steht der Samtgemeindewert, mit Ebene im Feld `prognose.ebene`. Kleine schleswig-holsteinische Gemeinden haben keinen freien Wert, dort ist die Prognose null.
