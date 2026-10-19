# Zusammenfassung Block 07, 37 Gemeinden

Datei: `ergebnis5/lieferung-01.json`, ein Array mit 37 Objekten. Branch: `claude/laughing-sagan-q2wyfw`. Das Verfahren entspricht Block 05 in zweiter Fassung, zusätzlich mit allem aus Block 06 und den Regeln aus Block 10:

- miet-check über den vollständigen Ortsindex, miete-aktuell mit Pfadvarianten.
- Ersatzquellen (zuerst ohne-makler.net, dann Engel & Völkers) nur, wenn weniger als zwei Auftragsquellen Werte liefern, und nur nach Landkreis-Prüfung.
- Ortsbestätigung je Quelle im Feld `ortspruefung`. Bei Ortsnamen, die es in Deutschland mehrfach gibt, gilt die strenge Prüfung: PLZ exakt, oder Landkreis und PLZ-Bereich, oder mindestens zwei Nachbarorte im Landkreis.
- Der Gutachter-Kreiswert zählt nur, wenn er höchstens 40 % vom Median der Portalwerte abweicht.
- Prognose je Gemeinde mit Basis- und Zieljahr genau wie im Profil. Mietpreisbremse per Gemeindeschlüssel mit `mpbQuelle`. Arbeitgeber aus dem Wikipedia-Artikel.

## Ampel

- gesamt: grün 18, gelb 17, rot 2, unbewertet 0
- Bayern: grün 8, gelb 13, rot 2, unbewertet 0
- Baden-Württemberg: grün 10, gelb 4, rot 0, unbewertet 0

## Datenlage

- Mietpreisbremse laut Liste: 7 Orte (Odelzhausen, Haimhausen, Umkirch, Aying, Brunnthal, Egling, Fahrenzhausen)
- dünne Datenbasis: 0
- mit Ersatzquelle: 0
- Gutachter-Kreiswert nicht gewertet (über 40 %): 0
- Ortsverwechslung bereinigt: 1 (Wörth a.d.Donau)
- ohne Prognose: 0
- Arbeitgeber belegt: 1 Ort (Wörth a.d.Donau). Bei allen anderen nennt der Wikipedia-Artikel keine Firma mit Beschäftigtenzahl am Ort, das Feld bleibt null.
- Hochwasser, amtlicher Mietspiegel, Pendler und Leerstand sind nicht erhoben.

