# Zusammenfassung Standortbewertung Block 04 (300 Gemeinden)

Abruf der Quellen: 18.10.2026 per curl. Lieferungen: `ergebnis/lieferung-01.json` bis `lieferung-06.json`, je 50 Orte.

## Ampel

- Gesamt: grün 129, gelb 161, rot 10 (von 300)
- Bayern (170 Orte): grün 40, gelb 120, rot 10
- Baden-Württemberg (130 Orte): grün 89, gelb 41, rot 0
- Rot (Faktor über 30): holzkirchen, dorfen, grafing-b-muenchen, murnau-a-staffelsee, herrsching-a-ammersee, gruenwald, taufkirchen-by, tutzing, pullach-i-isartal, sauerlach
- Prognose-Deckel angewendet (-8 % oder schlechter): 1 Orte (eichenau)
- Keine Ampel wurde durch den Prognose-Deckel auf rot gesetzt (kein Ort mit -15 % oder schlechter).

## Regeln und Quellen

- Kauf: Mittel aus immoportal, homeday, miete-aktuell; bei Bayern als vierte Quelle der Kreis- oder Stadtwert der Wiederverkäufe ETW 2025 aus dem Immobilienmarktbericht Bayern 2026. In BW gibt es keinen freien Marktbericht.
- Miete: Mittel aus immoportal, miete-aktuell, miet-check. homeday nur daneben genannt.
- Ersatzquellen (ohne-makler.net, Engel & Völkers) nur, wenn die drei Auftragsquellen nach Pfadsuche erschöpft waren.
- Ortsprüfung: miete-aktuell, miet-check und ohne-makler.net über PLZ und Bundesland; immoportal und homeday über die aufgelisteten Nachbarorte. Nicht bestätigte Werte mit mehr als 25 % Abweichung vom Median der geprüften Quellen wurden nicht gewertet.
- Ausreißer: mehr als 50 % über der nächsten Quelle oder unter 60 % des Medians der übrigen Quellen zählt nicht.
- Prognose: Bayern Demographie-Spiegel (2024 bis 2044), BW GENESIS 12421-0006 (Basis 2023, Hauptvariante mit Wanderung, 2024 bis 2045). Für alle 300 Orte ein Gemeindewert.
- Mietpreisbremse: Bayern nach der Anlage der MiSchuV (284 Gemeinden, Stand nach Änderung vom 16.06.2026) mit Landkreis-Zuordnung, BW nach § 1 der MietBegrenzVO vom 16.12.2025 (130 Gemeinden). Gelistet: 90 Orte, dort Kappung 15 %, sonst 20 %. Die Kappungsgrenzenverordnung selbst wurde nicht gelesen.
- Einwohner: Destatis Gemeindeverzeichnis, Bevölkerung 31.12.2024 (Zensus 2022), Gebietsstand 31.12.2025.

## Offene Punkte

Bei allen 300 Orten offen: amtlicher Mietspiegel, Arbeitgeber (`arbeitgeber` ist überall `null`), Pendler, Hochwasser, Leerstand. Die Kappungsgrenzenverordnung wurde nicht direkt gelesen.

- Gutachterausschuss BW ohne freien Bericht: 130 Orte
- Gutachterwert Bayern nur als Kreiswert: 167 Orte; ohne Kreiswert im Bericht: 3 Orte
- Datenbasis dünn (weniger als zwei Quellen bei Kauf oder Miete): 21 Orte (lohr-a-main, immenstadt-i-allgaeu, st-leon-rot, sulz-am-neckar, murnau-a-staffelsee, lindenberg-i-allgaeu, herrsching-a-ammersee, prien-a-chiemsee, haigerloch, gemuenden-a-main, langweid-a-lech, neuried, pullach-i-isartal, neunkirchen-a-brand, hemmingen, pfaffenhofen-a-d-roth, dietenheim, emmering, laudenbach, grafenau, schwabhausen)
- Ersatzquelle genutzt: 28 Orte (altdorf-b-nuernberg, stein, neustadt-b-coburg, krumbach, grafing-b-muenchen, kirchheim-b-muenchen, wasserburg-a-inn, lauingen, simbach-a-inn, hemau, nittenau, schwaig-b-nuernberg, neuried, volkach, arnstein, schwarzenbruck, feldkirchen, bergkirchen, rimpar, schwanstetten, dettelbach, emmering, leinburg, zellingen, langquaid, barbing, dasing, hebertshausen)
- Wert wegen Ausreißerregel oder Ortsverwechslung nicht gewertet: 15 Orte (landau-a-d-isar, sulz-am-neckar, osterhofen, regen, haigerloch, schoenaich, bogen, werneck, frickenhausen, neuried, arnstein, sauerlach, hemmingen, grafenau, pyrbaum)
- Ort nicht über PLZ oder Nachbarorte bestätigt (bei mindestens einer Quelle): 290 Orte

## Welche Quellen oft fehlten

| Quelle | Fehlte bei Kauf | Fehlte bei Miete |
|---|---|---|
| immoportal | 29 | 30 |
| homeday | 3 | nicht vorgesehen |
| miete-aktuell | 34 | 34 |
| miet-check | nicht vorgesehen | 45 |

## Hinweise

- Die Dateien liegen auf dem Branch `claude/laughing-sagan-q2wyfw`. Ein Push auf `main` war nach der Vorgabe dieser Sitzung nicht vorgesehen.
- Fazit je Ort: drei Sätze, `{R}` und `{F}` je einmal. Die Bruttorendite und der Faktor sind aus den gemittelten Werten berechnet.
