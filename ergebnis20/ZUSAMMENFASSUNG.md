# Zusammenfassung ergebnis20: Tiefenprüfung der 27 offenen Städte (Stufe 2)

Datei: `ergebnis20/lieferung-01.json`. Das Format entspricht `ergebnis16/test-stufe2.json`, die Tiefenwerte stehen im Feld `stufe2`. Branch: `claude/laughing-sagan-q2wyfw`.

## Städte, Gemeindeschlüssel und Ampel

Die Gemeindeschlüssel stammen aus dem Destatis-Gemeindeverzeichnis (Gebietsstand 31.12.2025), die Namen sind eindeutig geprüft. Ergebnis: 18 grün, 9 gelb, kein Rot, kein Unbewertet.

| Land | Städte |
|---|---|
| Baden-Württemberg | 15 |
| Bayern | 6 |
| Sachsen | 3 |
| Brandenburg | 2 |
| Thüringen | 1 |

Gelb sind:
- Friedrichshafen (4,2 %), Ravensburg (4,0 %), Aschaffenburg (3,9 %), Landshut (3,6 %), Kempten (4,2 %), Rosenheim (3,9 %), Cottbus (3,9 %) und Brandenburg an der Havel (3,7 %): Rendite unter 4,25 %.
- Zwickau: Rendite 7,6 %, aber Prognose-Deckel bei -12,4 %.

Cottbus steht auch in ergebnis18 (Teil 1, fern), mit denselben Portalwerten. Hier kommen die Tiefenwerte dazu.

## Kaufwert je Stadt und Gutachter-Gewichtung

Zum Hinweis aus dem Test: Der Gutachterwert zählt im Kaufmittel weiterhin nur in Bayern. Dort ist es der Wert des Immobilienmarktberichts Bayern 2026 für die kreisfreie Stadt selbst, also kein fremder Kreiswert. Er zählt ab zwei Portalwerten und bis 40 % Abweichung.

In allen anderen Ländern steht der örtliche Gutachterwert nur in `stufe2`. Er fließt nicht ins Kaufmittel und nicht in die Ampel ein.

Der Abstand von +2 bis +5 % zu den lokalen Tiefenwerten im Test kam nicht aus dem Gutachterwert. Er kam daher, dass homeday Kauf als Auftragsquelle mitzählt. homeday liegt in den Großstädten meist über immoportal und miete-aktuell. Ich habe das nach der Regel so gelassen.

| Stadt | Land | Kauf €/m² | Miete €/m² | Rendite | Ampel | Quelle des Kaufwerts (Kaufmittel) | Gutachterwert | Kaufmittel zu Gutachter |
|---|---|---|---|---|---|---|---|---|
| Heilbronn | Baden-Württemberg | 3.537 | 13,65 | 4,6 % | grün | immoportal 3.466, homeday 3.650, miete-aktuell 3.494, Gutachterausschuss keine Angabe | 3.114 €/m² (2024) | 13,6 % |
| Ludwigsburg | Baden-Württemberg | 4.042 | 14,88 | 4,4 % | grün | immoportal 3.833, homeday 4.350, miete-aktuell 3.943, Gutachterausschuss keine Angabe | 3.635 €/m² (2024) | 11,2 % |
| Waiblingen | Baden-Württemberg | 3.835 | 14,35 | 4,5 % | grün | immoportal 3.736, homeday 4.000, miete-aktuell 3.770, Gutachterausschuss keine Angabe | 3.134 €/m² (2024) | 22,4 % |
| Esslingen am Neckar | Baden-Württemberg | 3.838 | 13,69 | 4,3 % | grün | immoportal 3.750, homeday 3.950, miete-aktuell 3.813, Gutachterausschuss keine Angabe | keiner | k. A. |
| Sindelfingen | Baden-Württemberg | 3.901 | 15,50 | 4,8 % | grün | immoportal 3.771, homeday 4.100, miete-aktuell 3.832, Gutachterausschuss keine Angabe | 3.500 €/m² (2025 (Verkäufe 01/2025 bis 03/2026)) | 11,5 % |
| Böblingen | Baden-Württemberg | 3.933 | 15,28 | 4,7 % | grün | immoportal 3.801, homeday 4.150, miete-aktuell 3.849, Gutachterausschuss keine Angabe | 3.335 €/m² (2023 bis 2024 (Verkäufe 2023/2024)) | 17,9 % |
| Göppingen | Baden-Württemberg | 2.976 | 11,70 | 4,7 % | grün | immoportal 2.900, homeday 3.050, miete-aktuell 2.979, Gutachterausschuss keine Angabe | 2.457 €/m² (2024) | 21,1 % |
| Aalen | Baden-Württemberg | 3.263 | 12,19 | 4,5 % | grün | immoportal 3.110, homeday 3.600, miete-aktuell 3.079, Gutachterausschuss keine Angabe | 2.748 €/m² (2024) | 18,7 % |
| Heidenheim an der Brenz | Baden-Württemberg | 2.651 | 10,55 | 4,8 % | grün | immoportal 2.569, homeday 2.850, miete-aktuell 2.534, Gutachterausschuss keine Angabe | keiner | k. A. |
| Reutlingen | Baden-Württemberg | 3.576 | 13,44 | 4,5 % | grün | immoportal 3.527, homeday 3.650, miete-aktuell 3.551, Gutachterausschuss keine Angabe | keiner | k. A. |
| Villingen-Schwenningen | Baden-Württemberg | 2.611 | 10,76 | 4,9 % | grün | immoportal 2.547, homeday 2.850, miete-aktuell 2.435, Gutachterausschuss keine Angabe | keiner | k. A. |
| Friedrichshafen | Baden-Württemberg | 4.130 | 14,34 | 4,2 % | gelb | immoportal 4.167, homeday 4.150, miete-aktuell 4.073, Gutachterausschuss keine Angabe | 3.710 €/m² (2022) | 11,3 % |
| Ravensburg | Baden-Württemberg | 4.063 | 13,59 | 4,0 % | gelb | immoportal 3.845, homeday 4.350, miete-aktuell 3.995, Gutachterausschuss keine Angabe | keiner | k. A. |
| Lörrach | Baden-Württemberg | 3.800 | 14,30 | 4,5 % | grün | immoportal 3.687, homeday 3.950, miete-aktuell 3.764, Gutachterausschuss keine Angabe | 3.457 €/m² (2021 bis 2022) | 9,9 % |
| Rastatt | Baden-Württemberg | 2.903 | 11,39 | 4,7 % | grün | immoportal 2.903, homeday 3.050, miete-aktuell 2.755, Gutachterausschuss keine Angabe | keiner | k. A. |
| Aschaffenburg | Bayern | 3.784 | 12,41 | 3,9 % | gelb | immoportal 3.985, homeday 3.800, miete-aktuell 3.751, Gutachterausschuss Bayern (Kreiswert) 3.600 (Wiederverkäufe ETW 2025) | 3.600 €/m² (2025) | 5,1 % |
| Bayreuth | Bayern | 3.041 | 11,95 | 4,7 % | grün | immoportal 3.268, homeday 3.500, miete-aktuell 2.696, Gutachterausschuss Bayern (Kreiswert) 2.700 (Wiederverkäufe ETW 2025) | 2.700 €/m² (2025) | 12,6 % |
| Landshut | Bayern | 4.330 | 13,13 | 3,6 % | gelb | immoportal 4.724, homeday 4.150, miete-aktuell 4.244, Gutachterausschuss Bayern (Kreiswert) 4.200 (Wiederverkäufe ETW 2025) | 4.200 €/m² (2025) | 3,1 % |
| Kempten (Allgäu) | Bayern | 3.913 | 13,63 | 4,2 % | gelb | immoportal 3.956, homeday 4.250, miete-aktuell 3.847, Gutachterausschuss Bayern (Kreiswert) 3.600 (Wiederverkäufe ETW 2025) | 3.600 €/m² (2025) | 8,7 % |
| Rosenheim | Bayern | 4.683 | 15,27 | 3,9 % | gelb | immoportal 4.643, homeday 5.100, miete-aktuell 4.688, Gutachterausschuss Bayern (Kreiswert) 4.300 (Wiederverkäufe ETW 2025) | 4.300 €/m² (2025) | 8,9 % |
| Passau | Bayern | 3.052 | 11,50 | 4,5 % | grün | immoportal 3.022, homeday 3.400, miete-aktuell 2.988, Gutachterausschuss Bayern (Kreiswert) 2.800 (Wiederverkäufe ETW 2025) | 2.800 €/m² (2025) | 9,0 % |
| Cottbus | Brandenburg | 2.576 | 8,35 | 3,9 % | gelb | immoportal 2.634, miete-aktuell 2.518, Gutachterausschuss keine Angabe | 2.392 €/m² (2025) | 7,7 % |
| Zwickau | Sachsen | 1.032 | 6,50 | 7,6 % | gelb | immoportal 835, homeday 1.150, miete-aktuell 1.112, Gutachterausschuss keine Angabe | 1.149 €/m² (2024/2025) | minus 10,2 % |
| Brandenburg an der Havel | Brandenburg | 2.806 | 8,68 | 3,7 % | gelb | immoportal 2.938, homeday 2.650, miete-aktuell 2.829, Gutachterausschuss keine Angabe | 2.136 €/m² (2025) | 31,4 % |
| Weimar | Thüringen | 2.796 | 10,51 | 4,5 % | grün | immoportal 2.916, miete-aktuell 2.676, Gutachterausschuss keine Angabe. homeday 2.750 (nicht gewertet: Ortsname mehrfach in Deutschland und Seite nicht über PLZ, Landkreis oder Bundesland bestätigt) | keiner | k. A. |
| Plauen | Sachsen | 915 | 5,69 | 7,5 % | grün | immoportal 669, homeday 1.000, miete-aktuell 1.076, Gutachterausschuss keine Angabe | 784 €/m² (2023/2024) | 16,7 % |
| Görlitz | Sachsen | 1.199 | 6,55 | 6,6 % | grün | immoportal 971, homeday 1.300, miete-aktuell 1.326, Gutachterausschuss keine Angabe | keiner | k. A. |

Die Spalte „Kaufmittel zu Gutachter“ dient nur zur Einordnung. Gründe:
- Hier stehen Angebotspreise gegen Kaufpreise.
- Viele BW-Gutachter nennen nur einen Wert für ein Baujahres-Segment, das Segment steht in `stufe2.gutachter.segment`. Nur Heilbronn und Aalen haben einen Wert über alle Baujahre, frei abrufbar.
- In Zwickau, Plauen und Cottbus gilt der Wert nur für ein Segment (Altbau saniert bzw. Neubau ab 1994).

## Zusätzlich verfügbare Quellen (stufe2)

| Stadt | Mietspiegel | Zweckentfremdungssatzung | Leerstand Zensus 2022 | Prognose Gemeinde |
|---|---|---|---|---|
| Heilbronn | ja, qualifiziert | nein | 4,0 % | +5,2 % (2020 bis 2040) |
| Ludwigsburg | ja, qualifiziert | nein | 3,7 % | +4,8 % (2020 bis 2040) |
| Waiblingen | ja, qualifiziert | nein | 3,4 % | +6,4 % (2020 bis 2040) |
| Esslingen am Neckar | ja, qualifiziert | nein | 4,3 % | +5,3 % (2020 bis 2040) |
| Sindelfingen | ja, qualifiziert | nein | 4,1 % | +7,1 % (2020 bis 2040) |
| Böblingen | ja, qualifiziert | nein | 3,4 % | +8,6 % (2020 bis 2040) |
| Göppingen | ja, qualifiziert | nein | 4,1 % | +6,5 % (2020 bis 2040) |
| Aalen | ja, qualifiziert | nein | 4,2 % | +3,5 % (2020 bis 2040) |
| Heidenheim an der Brenz | nein | nein | 4,6 % | +10,0 % (2020 bis 2040) |
| Reutlingen | ja, qualifiziert | nein | 3,1 % | +5,8 % (2020 bis 2040) |
| Villingen-Schwenningen | ja, qualifiziert | nein | 3,8 % | +7,1 % (2020 bis 2040) |
| Friedrichshafen | ja, qualifiziert | nein | 3,5 % | +6,6 % (2020 bis 2040) |
| Ravensburg | ja, qualifiziert | nein | 3,2 % | +4,1 % (2020 bis 2040) |
| Lörrach | nein | nein | 3,6 % | +2,5 % (2020 bis 2040) |
| Rastatt | ja, qualifiziert | nein | 3,8 % | +7,1 % (2020 bis 2040) |
| Aschaffenburg | ja, qualifiziert | nein | 4,4 % | +1,3 % (2024 bis 2044) |
| Bayreuth | ja, qualifiziert | nein | 4,9 % | -1,8 % (2024 bis 2044) |
| Landshut | ja, qualifiziert | nein | 4,2 % | +4,7 % (2024 bis 2044) |
| Kempten (Allgäu) | ja, qualifiziert | nein | 2,9 % | +2,1 % (2024 bis 2044) |
| Rosenheim | ja, qualifiziert | nein | 2,0 % | +3,2 % (2024 bis 2044) |
| Passau | ja, qualifiziert | nein | 5,7 % | +4,6 % (2024 bis 2044) |
| Cottbus | ja, qualifiziert | nein | 6,4 % | -2,5 % (2023 bis 2040) |
| Zwickau | ja, einfach | nein | 13,1 % | -12,4 % (2020 bis 2040) |
| Brandenburg an der Havel | ja, qualifiziert | nein | 8,6 % | +3,1 % (2023 bis 2040) |
| Weimar | ja, einfach | nein | 4,2 % | -1,7 % (2020 bis 2040) |
| Plauen | ja, qualifiziert | nein | 13,3 % | -4,0 % (2020 bis 2040) |
| Görlitz | ja, qualifiziert | nein | 13,0 % | +1,4 % (2020 bis 2040) |

### Mietspiegel

- Fast alle Städte haben einen; Ausgabe, Gültigkeit und Link stehen je Stadt in `stufe2`.
- Ohne Mietspiegel sind Heidenheim (kein qualifizierter; die Angabe stammt aus einem Ratsdokument, das ich nur im Suchindex lesen konnte) und Lörrach („kein offizieller Mietspiegel“).
- Einfache Mietspiegel haben Zwickau und Weimar.

### Gutachterwert fehlt in 8 Städten

- Esslingen, Heidenheim, Reutlingen, Villingen-Schwenningen und Rastatt: Der Bericht ist kostenpflichtig, und es gibt keine freie Zusammenfassung.
- Ravensburg: 2025 kein Bericht veröffentlicht.
- Weimar: Der gemeinsame Gutachterausschuss veröffentlicht nur beim TLBG, und diese Seite ist per Captcha gesperrt.
- Görlitz: Der Landkreis gibt keinen Preis an.

### Ältere oder gemeinsame Gutachterwerte

- Friedrichshafen: Bericht 2023 über Kauffälle 2022.
- Lörrach: 2021/2022 (Verwaltungsgemeinschaft Lörrach-Inzlingen).
- Plauen: 2023/2024.
- Böblingen, Waiblingen und Göppingen: gemeinsame Gutachterausschüsse.

### Zweckentfremdung

- Keine der 27 Städte hat eine geltende Satzung.
- Esslingen hatte eine Satzung vom 24.07.2023, aufgehoben am 17.04.2026.
- Friedrichshafen: Abstimmung 2022 zweimal 18:18 und vertagt, später kein Beschluss gefunden.
- Landesrecht:
  - Brandenburg: Zweckentfremdungsverbotsgesetz von 2019, eine Satzung nur in Potsdam.
  - Sachsen: Gesetz seit 19.03.2024, Satzung nur in Leipzig.
  - Thüringen: kein geltendes Landesgesetz.

### Leerstand

- Zensus 2022, Tabelle 4000W-0001, Wohngebäude ohne Wohnheime.
- Hoch im Osten: Zwickau 13,1 %, Plauen 13,3 %, Görlitz 13,0 %, Brandenburg an der Havel 8,6 %, Cottbus 6,4 %. Die Ampel bleibt davon unberührt.

### Prognose

- BW: Bertelsmann Wegweiser Kommune 2020 bis 2040. Das ist die Ersatzquelle, weil GENESIS-Online BW am 19.10.2026 mit Server-Timeout abbrach; die Quelle ist je Stadt vermerkt.
- Bayern: Demographie-Spiegel 2024 bis 2044, Profil der kreisfreien Stadt. Für kreisfreie Städte liegt das PDF unter dem fünfstelligen Schlüssel; den Abruf dafür habe ich angepasst.
- Brandenburg: LBV 2023 bis 2040.
- Sachsen und Thüringen: Wegweiser Kommune.

### Mietpreisbremse

- Nach der amtlichen Landesliste. Neu ist Thüringen: Die Mietpreisbegrenzungsverordnung, zuletzt verlängert am 09.12.2025 bis 31.12.2027, gilt nur für Erfurt und Jena. Weimar ist nicht gelistet.
- Sachsen: nur Dresden und Leipzig.
- Bayern und BW nach den Listen wie bisher.

### Arbeitgeber

- Nur Wikipedia-Sätze mit Firma und Beschäftigtenzahl am Ort.
- Nicht übernommen: Alstom Görlitz (Werk 2025 an KNDS verkauft, Zugproduktion bis März 2026 eingestellt) und Pflanzen-Kölle sowie Kreissparkasse Heilbronn (Zahlen gelten für das ganze Unternehmen).
