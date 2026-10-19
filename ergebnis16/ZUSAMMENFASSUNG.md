# Zusammenfassung ergebnis16

Dateien: `ergebnis16/lieferung-01.json` (Teil 1, 15 Orte, Format wie ergebnis6) und `ergebnis16/test-stufe2.json` (Teil 2, 5 Städte, gleiches Format plus Feld `stufe2`). Branch: `claude/laughing-sagan-q2wyfw`.

Regeln wie in ergebnis14 und ergebnis15:

- Ausreißer werden nur unter Portalwerten bestimmt.
- Es gilt die Zwei-Werte-Regel.
- Der Gutachter-Kreiswert zählt nur in Bayern, ab zwei Portalwerten und bis 40 % Abweichung.
- Ersatzquellen kommen nur zum Einsatz, wenn weniger als zwei Auftragsquellen übrig sind.
- Ohne Prognose ist die Ampel höchstens gelb.

Mietpreisbremse und Kappung werden über den Gemeindeschlüssel gegen die amtlichen Listen geprüft:

- NRW: MietSchVO NRW vom 28.01.2025
- Niedersachsen: Mieterschutzverordnung
- Baden-Württemberg: MietBegrenzVO vom 16.12.2025
- Hessen: Mieterschutzverordnung, 49 Gemeinden
- Rheinland-Pfalz: Mietpreisbegrenzungsverordnung vom 16.09.2025, Koblenz nicht gelistet
- Bayern: Mieterschutzverordnung

Kirchhofen und Norsingen sind nicht eigens bewertet. Sie haben keine eigene Portalseite.

## Teil 1: 15 Orte

| Land | Orte | grün | gelb |
|---|---|---|---|
| Baden-Württemberg | 7 | 2 | 5 |
| Nordrhein-Westfalen | 4 | 4 | 0 |
| Niedersachsen | 2 | 2 | 0 |
| Bayern | 2 | 0 | 2 |
| **Summe** | **15** | **8** | **7** |

Stand nach der Nachlieferung vom 19.10.2026, siehe unten.

Rot und unbewertet kommen nicht vor.

- **Grün:**
  - Bad Urach (4,8 %, seit Nachlieferung)
  - Blaubeuren (4,5 %, seit Nachlieferung)
  - Wolfenbüttel (5,5 %)
  - Frechen (4,5 %, Mietpreisbremse)
  - Gummersbach (5,1 %)
  - Peine (6,3 %)
  - Bad Oeynhausen (5,0 %)
  - Gronau (Westf.) (4,8 %)
- **Gelb wegen Rendite unter 4,25 %:**
  - Schongau (3,8 %)
  - Gaimersheim (3,6 %)
  - Dossenheim (4,0 %)
  - Ehrenkirchen (3,9 %)
  - Schallstadt (4,2 %)
  - Ebringen (4,0 %)
  - Pfaffenweiler (3,8 %)

### Nachlieferung Baden-Württemberg

Der Werteabruf bei GENESIS-Online BW (Tabelle 12421-0006) brach am 19.10.2026 bei jedem Versuch mit einem Server-Timeout ab. Wie lokal freigegeben, ist die Prognose deshalb aus der Ersatzquelle Bertelsmann Wegweiser Kommune, 2020 bis 2040, Gemeindewert. Die Quelle steht je Ort im Feld prognose.

| Ort | Prognose | Rendite | Ampel vorher | Ampel jetzt |
|---|---|---|---|---|
| Bad Urach | +9,5 % | 4,8 % | gelb | grün |
| Blaubeuren | +8,7 % | 4,5 % | gelb | grün |
| Dossenheim | -2,8 % | 4,0 % | gelb | gelb |
| Ehrenkirchen | +1,0 % | 3,9 % | gelb | gelb |
| Schallstadt | +3,0 % | 4,2 % | gelb | gelb |
| Ebringen | keine | 4,0 % | gelb | gelb |
| Pfaffenweiler | keine | 3,8 % | gelb | gelb |

- Ebringen und Pfaffenweiler stehen nicht bei Wegweiser Kommune, weil sie unter 5.000 Einwohner haben. Sie bleiben ohne Prognose und damit höchstens gelb.
- `lieferung-01.json` ist aktualisiert. Die 7 BW-Orte stehen zusätzlich einzeln in `nachlieferung-bw-01.json`, damit sie sich lokal leicht einspielen lassen.

### Weitere Hinweise

- Ehrenkirchen, Ebringen und Pfaffenweiler haben bei Kauf nur zwei Portalquellen, weil immoportal keine Seite hat. Ebringen und Pfaffenweiler haben auch bei Miete nur zwei Quellen.
- Pfaffenweiler Miete: miet-check 13,90 und miete-aktuell 10,92 liegen 27 % auseinander, also unter der Ausreißergrenze.
- Arbeitgeber aus Wikipedia, nur Sätze mit Firma und Beschäftigtenzahl am Ort:
  - Wolfenbüttel: MKN, Klinikum
  - Bad Oeynhausen: HDZ NRW, Städtisches Krankenhaus
  - Schongau: UPM, Hoerbiger, Comprevia, Hirschvogel, Hochland
  - Ehrenkirchen: Anton Hübner
- Nicht übernommen: Engbers in Gronau (die Zahl gilt für die ganze Kette) und die Ostfalia in Wolfenbüttel (vier Standorte).

## Teil 2: Test Stufe 2, 5 Städte

| Land | Orte | grün | gelb |
|---|---|---|---|
| Hessen | 4 | 3 | 1 |
| Rheinland-Pfalz | 1 | 1 | 0 |
| **Summe** | **5** | **4** | **1** |

Die Ampel ist wie bei allen anderen Orten nur aus Portalwerten, Prognose und Regulierung gerechnet. Die Tiefenwerte stehen in `stufe2` und fließen nicht in Kauf, Miete oder Ampel ein.

### Abweichungen zu den lokalen Tiefenwerten

Die lokalen Werte stammen aus der Auftragsnachricht und wurden nicht übernommen.

| Stadt | Kauf hier | Kauf lokal | Abw. | Miete hier | Miete lokal | Rendite hier | Ampel hier | Ampel lokal |
|---|---|---|---|---|---|---|---|---|
| Offenbach am Main | 3.922 | 3.727 | +5,2 % | 14,42 | 14,42 | 4,4 % | grün | grün |
| Hanau | 3.071 | 2.988 | +2,8 % | 12,76 | 12,76 | 5,0 % | grün | grün |
| Gießen | 3.491 | 3.424 | +2,0 % | 12,03 | 12,03 | 4,1 % | gelb | gelb |
| Marburg | 3.481 | 3.331 | +4,5 % | 12,57 | 12,57 | 4,3 % | grün | grün |
| Koblenz | 3.091 | 3.011 | +2,7 % | 11,10 | 11,10 | 4,3 % | grün | gelb |

- Die Mieten stimmen in allen fünf Städten überein.
- Kauf liegt hier überall 2 bis 5 % höher. Der wahrscheinliche Grund ist, dass homeday Kauf hier mitzählt (Offenbach 4.050, Marburg 3.600, Koblenz 3.450). Die lokale Rechnung scheint homeday Kauf nicht oder anders zu gewichten.
- **Einzige Ampelabweichung: Koblenz.** Auch mit dem lokalen Kaufwert 3.011 ergäbe sich nach diesen Regeln eine Rendite von 4,4 %, also grün. Die Prognose von -2,8 % liegt über dem Deckel von -8 %. Das lokale Gelb muss deshalb aus einem Tiefenwert kommen, etwa Leerstand 4,2 % oder schrumpfende Prognose. Aus den Portalwerten lässt es sich nicht erklären.
- **Offenbach:** Die strenge Ortsprüfung hatte immoportal und homeday zunächst gestrichen. Grund: Bei einer kreisfreien Stadt umfasst die Landkreisliste nur die Stadt selbst, die Nachbarorte passten also nie. Korrigiert: Bei kreisfreien Städten zählen jetzt die Gemeinden des gleichnamigen Umlandkreises. Die Nachbarorte Heusenstamm, Obertshausen, Neu-Isenburg, Dietzenbach und Dreieich liegen im Landkreis Offenbach. miet-check führt Offenbach am Main unter dem Pfad `offenbach`. Die Seite nennt Hessen / Offenbach am Main und die PLZ 63065 bis 63075, ist also strikt geprüft und mit 15,00 aufgenommen.

### Zusätzlich verfügbare Quellen

| Stadt | Mietspiegel | Gutachterwert ETW Wiederverkauf | Kauffälle | Zweckentfremdung | Leerstand Zensus 2022 | Prognose Gemeinde |
|---|---|---|---|---|---|---|
| Offenbach am Main | Mietspiegel 2026 mit Rechner | 3.500 €/m² (Landesbericht Hessen 2025, Jahr 2024); örtlicher vorläufiger Bericht 2.921 €/m² aus 98 Wiederverkäufen (nur Pressemeldung) | im Landesbericht nicht je Stadt | keine; Anträge 29.01.2025 und 12.02.2026 abgelehnt | 3,7 % (2.416 Wohnungen) | +4,7 % (2020 bis 2040) |
| Hanau | Mietspiegel 2024 (Verbände, vom Magistrat anerkannt), gültig bis 30.04.2026, Nachfolger nicht gefunden | 3.450 €/m² (Landesbericht 2025) | nicht je Stadt | keine gefunden | 4,3 % (1.967) | +10,2 % |
| Gießen | qualifizierter Mietspiegel 2026 | 3.350 €/m² (Landesbericht 2025) | nicht je Stadt | keine gefunden | 3,5 % (1.572) | +7,7 % |
| Marburg | qualifizierter Mietspiegel 2026 | 3.500 €/m² (Landesbericht 2025) | nicht je Stadt | keine gefunden | 2,8 % (1.095) | +1,4 % |
| Koblenz | qualifizierter Mietspiegel 2025/2026 | 2.770 €/m² (Gutachterausschuss Koblenz, Grundstücksmarkt 2025) | 302 geeignete | keine (Landesgesetz RLP 2020 erlaubt sie) | 4,2 % (2.565) | -2,8 % |

#### Gutachterwerte

- **Hessen:** Die Werte stammen aus Tab. 6.2.2 des Immobilienmarktberichts des Landes Hessen 2025, Spalte Oberzentren. Das ist ein Modellwert für eine 20 Jahre alte Wohnung mit 80 m² in mittlerer Lage. Kauffälle je Stadt weist der Landesbericht nicht aus.
- **Koblenz:** Der Wert ist der Durchschnitt aller Weiterverkäufe 2025 aus 302 geeigneten Kauffällen.

#### Abstand Portalmittel zum Gutachterwert

Das ist nur zur Einordnung gedacht, denn hier stehen Angebotspreise gegen Kaufpreise.

| Stadt | Abstand |
|---|---|
| Offenbach am Main | +12,1 % |
| Hanau | -11,0 % |
| Gießen | +4,2 % |
| Marburg | -0,5 % |
| Koblenz | +11,6 % |

#### Weitere Erläuterungen

- **Leerstand:** Zensus 2022, Stichtag 15.05.2022. Gezählt sind Wohnungen in Wohngebäuden ohne Wohnheime (Tabellen 4000W-0001 und 4000W-3002). Die früher genannten 2.491 Wohnungen in Offenbach zählen alle Gebäude mit Wohnraum. Die Quote ist auch so 3,7 %.
- **Zweckentfremdung in Hessen:**
  - Es gibt kein allgemeines Zweckentfremdungsgesetz.
  - Möglich sind nur Ferienwohnungssatzungen nach § 12a Hessisches Wohnungsaufsichtsgesetz. Das Ministerium nennt dafür Frankfurt und Maintal.
  - Seit 21.11.2025 sind Leerstandssatzungen möglich, bisher hat aber keine Kommune eine erlassen.
  - Die frühere Annahme „nur Frankfurt und Darmstadt“ ist damit ungenau.
- **Prognose:** Bertelsmann Wegweiser Kommune 2020 bis 2040, Gemeindewert.

## Noch offen

- BW: Ebringen und Pfaffenweiler haben weiter keine Prognose.
- Die Korrektur der Ortsprüfung für kreisfreie Städte betrifft nur Orte, deren Name mehrfach in Deutschland vorkommt. Frühere Lieferungen habe ich darauf nicht nachgeprüft.
