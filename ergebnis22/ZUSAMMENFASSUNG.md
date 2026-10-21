# Zusammenfassung ergebnis22: Nachbesserung älterer Lieferungen und BW-Prognose

Branch: `claude/laughing-sagan-q2wyfw`, kein Pull Request. Es sind nur Patches enthalten. Was in ergebnis21 schon gepatcht wurde (ergebnis17 und 18), ist nicht erneut bewertet.

| Datei | Inhalt |
|---|---|
| `patch-mietcheck-01.json` | 111 Orte mit neuer miet-check-Miete, vollständig neu gerechnet. Feld `nachtrag22` mit Wert vorher, neuer Quelle und Lieferung, aus der der Ort stammt |
| `mietcheck-nur-wert-01.json` | 71 Orte, für die ein gültiger miet-check-Wert gefunden, aber nicht automatisch nachgerechnet wurde (Grund je Ort) |

## Teil 1: miet-check-Lesefehler in ergebnis2 bis 16, 19 und 20

### Vorgehen (per Skript)

1. Je Ort die jüngste vollständige Fassung aus ergebnis1 bis 16, 19 und 20 genommen. Teilpatches ohne Namen und Ampel zählen nicht, sie ändern nur einzelne Felder.
2. Betroffen sind 370 Orte, bei denen miet-check fehlte (Hinweis „Miete ohne miet-check“).
3. Für diese Orte im miet-check-Ortsverzeichnis alle Seiten mit gleichem Namen gesucht, mit und ohne Zusatz, zum Beispiel `_bei_…`. Das ergab 387 Kandidaten bei 237 Orten.
4. Jeder Kandidat lief durch die strenge Ortsprüfung (PLZ, Landkreis, Nachbarorte), jetzt mit Lesen beider Seitenlayouts. Bei 182 Orten ist ein Wert gültig.
5. Neu gerechnet mit dem Bewertungsprogramm des jeweiligen Arbeitsordners, ohne neue Abrufe. Alle Regeln sind unverändert, einschließlich Zwei-Werte-Regel und Ausreißerregel.

### Sicherheitsprüfung

Ein Patch geht nur raus, wenn Kaufwert und bisherige Mietquellen im Arbeitsstand genau der gelieferten Fassung entsprechen. Das trifft auf 111 Orte zu.

71 Orte stelle ich zurück:
- Bei 37 weicht der Kaufwert im Arbeitsstand von der Lieferung ab, wegen späterer Patches mit Ersatzquelle oder Gutachterwert.
- Bei 32 weichen die Mietquellen ab.
- Bei 2 (Schönau, Malsch) wurde kein passender Arbeitsordner gefunden.

Für diese 71 Orte steht der geprüfte miet-check-Wert mit Pfad in `mietcheck-nur-wert-01.json`. Lokal kann er in die aktuelle Fassung eingespielt werden. Eine automatische Neuberechnung hätte sonst Werte aus dem alten Arbeitsstand mitgenommen.

### Ampeländerungen (36)

Alle durch die zusätzlich gewertete miet-check-Miete: gelb zu grün 32, rot zu gelb 3, unbewertet zu gelb 1.

| Ort | AGS | Lieferung | Ampel alt | Ampel neu | Miete alt | Miete neu | Grund |
|---|---|---|---|---|---|---|---|
| Oberasbach | 09573122 | ergebnis3 | gelb | grün | 11,81 | 12,30 | miet-check 13,27 neu gewertet (PLZ exakt) |
| Dietenheim | 08425028 | ergebnis3 | gelb | grün | 11,59 | 11,77 | miet-check 11,94 neu gewertet (PLZ exakt) |
| Laudenbach | 08226040 | ergebnis3 | gelb | grün | 12,34 | 12,41 | miet-check 12,48 neu gewertet (PLZ exakt) |
| Trochtelfingen | 08415073 | ergebnis2 | gelb | grün | 9,41 | 9,28 | miet-check 9,15 neu gewertet (PLZ exakt) |
| Seelbach | 08317127 | ergebnis2 | gelb | grün | 10,88 | 11,12 | miet-check 11,36 neu gewertet (PLZ exakt) |
| Hornberg | 08317051 | ergebnis2 | gelb | grün | 9,26 | 9,23 | miet-check 9,20 neu gewertet (PLZ exakt) |
| Hohentengen | 08437053 | ergebnis2 | gelb | grün | 9,88 | 10,10 | miet-check 10,32 neu gewertet (PLZ exakt) |
| Wurmlingen | 08327054 | ergebnis2 | gelb | grün | 10,05 | 10,46 | miet-check 10,87 neu gewertet (PLZ exakt) |
| Welden | 09772216 | ergebnis2 | gelb | grün | 12,42 | 12,52 | miet-check 12,61 neu gewertet (PLZ exakt) |
| Rickenbach | 08337090 | ergebnis2 | gelb | grün | 9,73 | 10,63 | miet-check 11,53 neu gewertet (PLZ exakt) |
| Ettringen | 09778137 | ergebnis2 | rot | gelb | 9,95 | 10,96 | miet-check 11,98 neu gewertet (PLZ exakt) |
| Staig | 08425138 | ergebnis2 | gelb | grün | 12,63 | 12,59 | miet-check 12,55 neu gewertet (PLZ exakt) |
| Kuchen | 08117033 | ergebnis2 | gelb | grün | 10,71 | 10,88 | miet-check 11,04 neu gewertet (PLZ exakt) |
| Hochdorf | 08116027 | ergebnis2 | gelb | grün | 12,64 | 12,89 | miet-check 13,14 neu gewertet (PLZ exakt) |
| Gschwend | 08136027 | ergebnis2 | gelb | grün | 9,97 | 10,04 | miet-check 10,12 neu gewertet (PLZ exakt) |
| Krautheim | 08126045 | ergebnis2 | gelb | grün | 9,23 | 9,72 | miet-check 10,21 neu gewertet (PLZ exakt) |
| Mulfingen | 08126056 | ergebnis2 | gelb | grün | 10,37 | 10,47 | miet-check 10,58 neu gewertet (PLZ exakt) |
| Beuren | 08116011 | ergebnis2 | gelb | grün | 12,57 | 12,62 | miet-check 12,67 neu gewertet (PLZ exakt) |
| Oberrot | 08127062 | ergebnis2 | gelb | grün | 8,48 | 9,68 | miet-check 10,87 neu gewertet (PLZ exakt) |
| Rödelmaier | 09673156 | ergebnis14 | gelb | grün | 8,51 | 8,67 | miet-check 8,83 neu gewertet (Landkreis auf der Seite genannt) |
| Schlammersdorf | 09374155 | ergebnis14 | gelb | grün | 8,50 | 8,76 | miet-check 9,02 neu gewertet (Landkreis auf der Seite genannt) |
| Rüdenhausen | 09675162 | ergebnis14 | gelb | grün | 11,45 | 10,63 | miet-check 9,81 neu gewertet (Landkreis auf der Seite genannt) |
| Mittelsinn | 09677159 | ergebnis14 | rot | gelb | 6,33 | 6,75 | miet-check 7,17 neu gewertet (Landkreis auf der Seite genannt) |
| Gleiritsch | 09376131 | ergebnis14 | gelb | grün | 8,35 | 8,88 | miet-check 9,40 neu gewertet (Landkreis auf der Seite genannt) |
| Stadlern | 09376167 | ergebnis14 | rot | gelb | 5,62 | 6,52 | miet-check 7,41 neu gewertet (Landkreis auf der Seite genannt) |
| Betzenweiler | 08426020 | ergebnis7 | gelb | grün | 10,43 | 10,30 | miet-check 10,18 neu gewertet (Landkreis auf der Seite genannt) |
| Alleshausen | 08426005 | ergebnis7 | gelb | grün | 10,43 | 10,30 | miet-check 10,18 neu gewertet (Landkreis auf der Seite genannt) |
| Kanzach | 08426064 | ergebnis7 | gelb | grün | 10,43 | 10,30 | miet-check 10,18 neu gewertet (Landkreis auf der Seite genannt) |
| Fröhnd | 08336025 | ergebnis7 | gelb | grün | 9,68 | 10,07 | miet-check 10,46 neu gewertet (Landkreis auf der Seite genannt) |
| Aitern | 08336004 | ergebnis7 | gelb | grün | 9,79 | 10,12 | miet-check 10,46 neu gewertet (Landkreis auf der Seite genannt) |
| Nerenstetten | 08425085 | ergebnis7 | gelb | grün | 11,68 | 11,81 | miet-check 11,95 neu gewertet (Landkreis auf der Seite genannt) |
| Unterwachingen | 08425125 | ergebnis7 | gelb | grün | 10,09 | 10,58 | miet-check 11,07 neu gewertet (Landkreis auf der Seite genannt) |
| Tunau | 08336089 | ergebnis7 | gelb | grün | 9,89 | 10,18 | miet-check 10,46 neu gewertet (Landkreis auf der Seite genannt) |
| Vierlinden | 12064482 | ergebnis9 | gelb | grün | 6,59 | 7,28 | miet-check 7,97 neu gewertet (Landkreis auf der Seite genannt) |
| Golzow | 12069216 | ergebnis9 | unbewertet | gelb |  | 8,61 | miet-check 8,61 neu gewertet (Landkreis auf der Seite genannt) |
| Lindendorf | 12064290 | ergebnis9 | gelb | grün | 6,59 | 7,28 | miet-check 7,97 neu gewertet (Landkreis auf der Seite genannt) |

### Ohne Ampelwechsel (nur Miete geändert)

| Ort | Lieferung | Miete alt | Miete neu |
|---|---|---|---|
| Bruckmühl | ergebnis3 | 13,86 | 14,06 |
| Gunzenhausen | ergebnis3 | 10,17 | 10,41 |
| Poing | ergebnis3 | 16,79 | 16,98 |
| Dorfen | ergebnis3 | 12,94 | 12,84 |
| Vöhringen | ergebnis3 | 11,78 | 11,93 |
| Roding | ergebnis3 | 8,59 | 8,72 |
| Hemsbach | ergebnis3 | 11,10 | 11,52 |
| Walldürn | ergebnis3 | 9,75 | 9,78 |
| Korb | ergebnis3 | 14,80 | 14,58 |
| Sinzheim | ergebnis3 | 10,97 | 11,43 |
| Altdorf | ergebnis3 | 11,95 | 12,25 |
| Engen | ergebnis3 | 11,29 | 11,17 |
| Stephanskirchen | ergebnis3 | 14,04 | 14,33 |
| Bad Wildbad | ergebnis3 | 9,53 | 9,65 |
| Schwabhausen | ergebnis3 | 15,34 | 15,70 |
| Bisingen | ergebnis2 | 10,14 | 10,40 |
| Hohberg | ergebnis2 | 10,93 | 11,18 |
| Türkheim | ergebnis2 | 12,05 | 12,02 |
| Laufen | ergebnis2 | 10,73 | 11,03 |
| Grassau | ergebnis2 | 13,85 | 14,47 |
| Durach | ergebnis2 | 13,71 | 13,55 |
| Hausach | ergebnis2 | 9,68 | 10,04 |
| Schechen | ergebnis2 | 14,58 | 14,66 |
| Warthausen | ergebnis2 | 10,85 | 11,29 |
| Buch | ergebnis2 | 10,66 | 11,16 |
| Anger | ergebnis2 | 10,30 | 11,69 |
| Dietingen | ergebnis2 | 8,63 | 9,69 |
| Ried | ergebnis2 | 13,26 | 13,35 |
| Mauerstetten | ergebnis2 | 9,52 | 10,72 |
| Buchenbach | ergebnis2 | 11,76 | 12,46 |
| Reute | ergebnis2 | 12,21 | 12,88 |
| Urbach | ergebnis2 | 11,86 | 12,02 |
| Mühlhausen | ergebnis2 | 11,35 | 11,64 |
| Rauenberg | ergebnis2 | 11,80 | 12,03 |
| Aspach | ergebnis2 | 12,26 | 12,53 |
| Hengersberg | ergebnis2 | 9,69 | 9,64 |
| Flein | ergebnis2 | 12,87 | 13,06 |
| Hardheim | ergebnis2 | 8,99 | 9,09 |
| Bad Birnbach | ergebnis2 | 9,54 | 9,36 |
| Schöntal | ergebnis2 | 9,35 | 9,62 |
| Waldbrunn | ergebnis2 | 9,04 | 9,55 |
| Massing | ergebnis2 | 9,27 | 9,45 |
| Döhlau | ergebnis2 | 7,42 | 7,81 |
| Straßkirchen | ergebnis2 | 8,51 | 9,09 |
| Owen | ergebnis2 | 11,90 | 12,34 |
| Villenbach | ergebnis14 | 11,24 | 11,24 |
| Sandberg | ergebnis14 | 6,92 | 7,28 |
| Wartmannsroth | ergebnis14 | 7,07 | 7,52 |
| Fladungen | ergebnis14 | 6,67 | 7,15 |
| Mähring | ergebnis14 | 7,01 | 7,95 |
| Stadelhofen | ergebnis14 | 6,67 | 7,25 |
| Raitenbuch | ergebnis14 | 8,21 | 8,66 |
| Bergen | ergebnis14 | 8,02 | 8,57 |
| Burgsalach | ergebnis14 | 8,58 | 8,85 |
| Stockheim | ergebnis14 | 6,49 | 7,28 |
| Höchheim | ergebnis14 | 7,55 | 7,70 |
| Bayerisch Eisenstein | ergebnis14 | 6,83 | 6,83 |
| Hausen | ergebnis14 |  | 8,06 |
| Reichenbach | ergebnis14 | 6,62 | 6,63 |
| Wattendorf | ergebnis14 | 7,93 | 8,34 |
| Philippsreut | ergebnis14 | 6,38 | 6,98 |
| Biederbach | ergebnis7 | 9,55 | 9,71 |
| Dürnau | ergebnis7 |  | 10,18 |
| Schönenberg | ergebnis7 | 8,75 | 9,61 |
| Moosburg | ergebnis7 | 10,43 | 10,30 |
| Friesack | ergebnis9 | 7,54 | 8,58 |
| Schlaubetal | ergebnis9 | 6,89 | 6,99 |
| Neißemünde | ergebnis9 | 5,92 | 6,89 |
| Oderaue | ergebnis9 | 7,76 | 7,78 |
| Schwielochsee/Gójacki Jazor | ergebnis9 | 7,25 | 6,88 |
| Siehdichum | ergebnis9 | 6,89 | 6,99 |
| Lieberose | ergebnis9 | 9,01 | 8,29 |
| Schönwald | ergebnis9 |  | 9,46 |
| Görzke | ergebnis9 | 7,02 | 6,90 |
| Wembach | ergebnis19 | 8,85 | 9,66 |

## Teil 2: Prognose für die kleinen BW-Gemeinden

- Ich habe GENESIS-Online BW am 21.10.2026 erneut versucht. Die Gebietsauswahl funktioniert wieder, Bad Urach wird gefunden.
- Der Abruf der Werte für die 20 Gemeinden ohne Prognose ist beim ersten Versuch (Bad Bellingen) wieder gescheitert.
- Ein Hintergrundlauf hat bis 09:04 Uhr alle 20 Gemeinden versucht und keinen Wert erhalten ("Tabelle nicht lesbar" bzw. "kein Treffer"). Damit ist die Prognose für diese Gemeinden weiter offen.
- **Stand jetzt bleiben die Lücken:**
  - ergebnis19 Teil 1: Bad Bellingen, Stegen, Rheinhausen, Freiamt, Meißenheim, Riegel, Biberach, Sasbach am Kaiserstuhl, Malterdingen, Gottenheim, Eisenbach, Hofstetten, Wittnau, Malsburg-Marzell, Wutach, Häg-Ehrsberg, Utzenfeld und Wembach.
  - ergebnis16: Ebringen und Pfaffenweiler.
- **Ersatzquelle Bertelsmann Wegweiser Kommune:**
  - Sie führt nur Gemeinden ab 5.000 Einwohnern. Keine der 20 Gemeinden hat dort einen Wert.
  - Bad Bellingen ist zwar gelistet, aber ohne Prognosewerte („k. A.“).
- Folge: Die Ampel dieser 20 Orte bleibt nach der Regel höchstens gelb.

## Kosten

Die genauen Kosten kann ich in dieser Sitzung nicht sehen. Der Auftrag lief vollständig in wenigen Skripten (Kandidatensuche, Ortsprüfung, Neuberechnung), ohne Einzelrecherche und ohne Hilfsagenten. Grob geschätzt waren es einige Dollar.
