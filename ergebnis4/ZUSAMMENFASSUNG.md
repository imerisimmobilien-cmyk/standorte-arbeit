# Zusammenfassung Block 06 (Lückenfüllung), ergebnis2 und ergebnis3

Patches: `ergebnis4/patch-a-01.json` bis `patch-a-13.json` mit je 100 Orten. Zuerst kommen die 1000 Orte aus ergebnis2, danach die 300 aus ergebnis3, jeweils in Lieferreihenfolge, der Süden zuerst. Jeder Eintrag hat `satz`, `id` und `ags` sowie nur die neuen oder geänderten Felder. Alles liegt auf dem Branch `claude/laughing-sagan-q2wyfw`.

## (1) Mietpreisbremse und Kappung

Die Gemeindelisten sind jetzt über den Gemeindeschlüssel abgeglichen, nicht mehr über den Namen. Die bayerische Anlage hat 284 Gemeinden (285 minus Reut). 282 davon ließen sich direkt dem Gemeindeverzeichnis zuordnen, 2 von Hand: Mainburg, in der Anlage unter "Kehlheim", und Bernried am Starnberger See. Von den 130 Gemeinden aus § 1 MietBegrenzVO BW waren 128 direkt zuzuordnen, 2 von Hand: Rheinhausen und Freiburg im Breisgau.

- ergebnis2: Keiner der 1000 Orte steht in einer der beiden Listen. `mpb false` und Kappung 20 sind deshalb richtig, auch wenn der Hinweis von 2Alltag etwas anderes vermutet hat. Die Liste der 1000 Orte enthält offenbar keine Gemeinde mit Mietpreisbremse. Die gelisteten Gemeinden waren schon in den Blöcken 02 bis 04. Gleichnamige Orte wie Bernried (Landkreis Deggendorf), Eching (Landkreis Landshut), Stammham und Röttenbach liegen in anderen Landkreisen als die gelisteten.
- ergebnis3: Eine Korrektur. Mainburg (09273147) wechselt von mpb false auf true und von Kappung 20 auf 15. Die übrigen 90 gelisteten und 209 nicht gelisteten Orte stimmen.
- Jeder Patch nennt die Quelle im Feld `mpbQuelle`.

## (2) Unbewertete Orte und dünne Datenbasis

- Vorher 186 Orte mit dünner Datenbasis oder ohne Bewertung (davon 15 unbewertet), nachher 62 (davon 6 unbewertet).
- miet-check hat einen vollständigen Ortsindex mit 11.854 Seiten. Damit wurden 173 bisher fehlende miet-check-Werte gefunden, darunter Pfade wie `grassau_chiemgau` und `trochtelfingen_hohenzollern`. Jeder Wert ist über die PLZ auf der Seite bestätigt.
- Für die dünnen und unbewerteten Orte zählen zusätzlich ohne-makler.net (Kauf und Miete) und Engel & Völkers (Kauf) als Ersatz, gekennzeichnet mit "(Ersatz)". Eine Seite wird nur genommen, wenn der Landkreis auf ihr genannt ist. Bei allen anderen Orten bleiben die Ersatzwerte außen vor.
- immoportal hat für viele kleine Orte keine Mietspiegel-Seite. Laut Sitemap gibt es nur 3.283 Mietspiegel-Seiten, die Lücke ist also echt.
- Immowelt, ImmoScout24 (Atlas und Preisseiten) und wohnungsboerse sperren den Abruf aus dieser Umgebung (403, 401 oder Weiterleitung). Landkreis- oder Nachbarortwerte als Näherung habe ich nicht eingesetzt.

## (3) Ortsbestätigung

- Jede genutzte Seite wurde am 19.10.2026 erneut abgerufen. PLZ und Landkreis kommen aus dem Destatis-Gemeindeverzeichnis. Das Feld `ortspruefung` nennt je Quelle Pfad, Ergebnis und Methode: PLZ passt, Bundesland passt, Landkreis auf der Seite genannt oder Nachbarorte passen.
- Je Ort gesamt: bestätigt 1298, Nachbarorte passen 2, nicht bestätigt 0.
- Je Quelle: bestätigt 4114, Nachbarorte passen 3389, nicht bestätigt 153. Keine bisher gewertete Seite fiel bei der Nachprüfung durch. immoportal und homeday zeigen keine PLZ, dort zählen die Nachbarorte auf der Seite.
- Die alte Angabe "Ort/PLZ geprüft: keine Quelle" in den Belegen kam von der früheren, zu strengen Prüfung. Sie wird für die Orte mit Wertänderung im Patch überschrieben.

## (4) Arbeitgeber

- 96 Orte haben jetzt 1 bis 5 Arbeitgeber mit Beschäftigtenzahl, zusammen 132 Einträge. Quelle ist jeweils der Abschnitt Wirtschaft des Wikipedia-Artikels der Gemeinde, den Artikel habe ich über den Gemeindeschlüssel bei Wikidata gefunden.
- Jeder Satz wurde von Hand geprüft. Aufgenommen sind nur Firmen mit Namen und Beschäftigtenzahl am Ort. Weggelassen sind historische Angaben, reine Weltweit- oder Deutschlandzahlen, Sätze ohne Firmennamen und Angaben vor 2010. `stand` ist das Jahr aus dem Artikelsatz, sonst steht dort "Jahr im Artikel nicht genannt".
- Bei den übrigen 1204 Orten bleibt arbeitgeber null. Bundesagentur und IHK haben keine freien Listen der größten Arbeitgeber je Gemeinde.

## (5) Hochwasser und amtlicher Mietspiegel

- Nicht ergänzt. Das Geoportal der LUBW ist aus dieser Umgebung nicht erreichbar (502). Eine Punktabfrage am Ortsmittelpunkt würde nichts über die Gemeinde als Ganzes aussagen. Für amtliche Mietspiegel gibt es keine freie Gemeindeliste. Beide Felder bleiben "keine Angabe" und gehören zu den offenen Punkten.

## (6) Gutachterwert BW

- Entfällt. Keine der Städte mit freiem örtlichen Marktbericht (Stuttgart, Karlsruhe, Freiburg, Ulm, Heilbronn, Konstanz usw.) ist in ergebnis2 oder ergebnis3. Die größten BW-Orte dort sind Stockach, Trossingen und Willstätt.

## (7) Neue Werte und Ampel

- 195 Orte haben neue Kauf- oder Mietwerte. Die Belege, das Fazit und die offenen Punkte stehen im Patch.
- Ampelwechsel: 70 (gelb zu grün 52, unbewertet zu gelb 7, rot zu gelb 9, unbewertet zu rot 2). Gerechnet wird nach den gleichen Regeln: Rendite auf eine Nachkommastelle, ab 4,25 % grün, Faktor über 30 rot, Prognose-Deckel, und grün nur bei mindestens zwei Quellen. Ein Teil der Wechsel nach grün kommt ohne Wertänderung über 5 % aus. Dort war die Ampel nur wegen dünner Datenbasis gelb, und jetzt gibt es eine zweite Mietquelle. Jeder Wechsel ist im Feld `ampelNeu` mit Alt- und Neuwert vermerkt.
- Ampel nach dem Patch, beide Sätze zusammen: grün 596, gelb 656, rot 42, unbewertet 6.

## Orte mit Ampelwechsel

- Jettingen-Scheppach (09774144, ergebnis2): gelb zu grün, Kauf 2859 zu 2859, Miete 11.39 zu 11.09 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Trochtelfingen (08415073, ergebnis2): gelb zu grün, Kauf 2528 zu 2528, Miete 9.41 zu 9.28 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Altenstadt (09775111, ergebnis2): unbewertet zu gelb, Kauf 3281 zu 3218, Miete None zu 11.47 (Änderung über 5 %)
- Ühlingen-Birkendorf (08337128, ergebnis2): gelb zu grün, Kauf 2166 zu 2166, Miete 8.6 zu 9.66 (Änderung über 5 %)
- Reichertshausen (09186146, ergebnis2): rot zu gelb, Kauf 4321 zu 4195, Miete 11.5 zu 12.47 (Änderung über 5 %)
- Emmingen-Liptingen (08327057, ergebnis2): gelb zu grün, Kauf 2770 zu 2770, Miete 10.2 zu 10.73 (Änderung über 5 %)
- Seelbach (08317127, ergebnis2): gelb zu grün, Kauf 2841 zu 2841, Miete 10.88 zu 11.12 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Bergen (09189113, ergebnis2): unbewertet zu gelb, Kauf None zu 4234, Miete None zu 13.27 (Änderung über 5 %)
- Seeon-Seebruck (09189143, ergebnis2): unbewertet zu gelb, Kauf 4520 zu 4520, Miete None zu 12.99 (Änderung über 5 %)
- Eurasburg (09173123, ergebnis2): rot zu gelb, Kauf 5188 zu 4856, Miete 13.98 zu 14.91 (Änderung über 5 %)
- Fuchstal (09181121, ergebnis2): rot zu gelb, Kauf 3857 zu 3669, Miete 10.29 zu 11.34 (Änderung über 5 %)
- Hornberg (08317051, ergebnis2): gelb zu grün, Kauf 1865 zu 1865, Miete 9.26 zu 9.23 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Hohentengen (08437053, ergebnis2): gelb zu grün, Kauf 2371 zu 2371, Miete 9.88 zu 10.1 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Buchenberg (09780117, ergebnis2): rot zu gelb, Kauf 3749 zu 3759, Miete 10.31 zu 11.62 (Änderung über 5 %)
- Pfaffing (09187159, ergebnis2): rot zu gelb, Kauf 4354 zu 3929, Miete 11.16 zu 11.73 (Änderung über 5 %)
- Wurmlingen (08327054, ergebnis2): gelb zu grün, Kauf 2771 zu 2771, Miete 10.05 zu 10.46 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Haldenwang (09780122, ergebnis2): gelb zu grün, Kauf 3663 zu 3663, Miete 13.03 zu 13.11 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Rickenbach (08337090, ergebnis2): gelb zu grün, Kauf 2014 zu 2014, Miete 9.73 zu 10.63 (Änderung über 5 %)
- Windach (09181146, ergebnis2): rot zu gelb, Kauf 4784 zu 4590, Miete 13.25 zu 13.7 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Buxheim (09176118, ergebnis2): gelb zu grün, Kauf 3271 zu 3130, Miete 12.93 zu 12.97 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Holzheim (09773140, ergebnis2): gelb zu grün, Kauf 3053 zu 3053, Miete 10.25 zu 11.5 (Änderung über 5 %)
- Orsingen-Nenzingen (08335099, ergebnis2): gelb zu grün, Kauf 2688 zu 2688, Miete 10.08 zu 11.36 (Änderung über 5 %)
- Ettringen (09778137, ergebnis2): rot zu gelb, Kauf 3779 zu 3834, Miete 9.95 zu 11.05 (Änderung über 5 %)
- Herdwangen-Schönach (08437124, ergebnis2): gelb zu grün, Kauf 2656 zu 2656, Miete 9.81 zu 11.02 (Änderung über 5 %)
- Polling (09183136, ergebnis2): rot zu gelb, Kauf 4093 zu 4148, Miete 11.03 zu 11.55 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Staig (08425138, ergebnis2): gelb zu grün, Kauf 3351 zu 3351, Miete 12.63 zu 12.59 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Altenstadt (09190111, ergebnis2): unbewertet zu gelb, Kauf 3681 zu 3681, Miete None zu 11.59 (Änderung über 5 %)
- Oberhausen (09185150, ergebnis2): unbewertet zu gelb, Kauf 4140 zu 3324, Miete None zu 11.35 (Änderung über 5 %)
- Buxheim (09778123, ergebnis2): gelb zu grün, Kauf 3346 zu 3346, Miete 13.51 zu 12.94 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Fluorn-Winzeln (08325070, ergebnis2): gelb zu grün, Kauf 1808 zu 1808, Miete 7.95 zu 8.65 (Änderung über 5 %)
- Rietheim-Weilheim (08327056, ergebnis2): gelb zu grün, Kauf 2839 zu 2839, Miete 10.27 zu 10.52 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Obernburg a.Main (09676145, ergebnis2): gelb zu grün, Kauf 3127 zu 3127, Miete 11.03 zu 11.22 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Mallersdorf-Pfaffenberg (09278148, ergebnis2): gelb zu grün, Kauf 2939 zu 2939, Miete 11.01 zu 10.68 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Bechhofen (09571115, ergebnis2): gelb zu grün, Kauf 2431 zu 2431, Miete 9.2 zu 9.17 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Riedenburg (09273164, ergebnis2): gelb zu grün, Kauf 2723 zu 2528, Miete 9.45 zu 9.61 (Änderung über 5 %)
- Klingenberg a.Main (09676134, ergebnis2): gelb zu grün, Kauf 2655 zu 2655, Miete 11.7 zu 11.11 (Änderung über 5 %)
- Kemnath (09377129, ergebnis2): gelb zu grün, Kauf 2740 zu 2966, Miete 11.52 zu 11.38 (Änderung über 5 %)
- Weidenberg (09472199, ergebnis2): gelb zu grün, Kauf 1850 zu 1785, Miete 8.92 zu 9.29 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Zeil a.Main (09674221, ergebnis2): gelb zu grün, Kauf 2300 zu 2300, Miete 8.72 zu 8.92 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Wernberg-Köblitz (09376150, ergebnis2): gelb zu grün, Kauf 2526 zu 2526, Miete 9.14 zu 9.18 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Kuchen (08117033, ergebnis2): gelb zu grün, Kauf 2680 zu 2680, Miete 10.71 zu 10.88 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Wörth a.Main (09676169, ergebnis2): gelb zu grün, Kauf 2732 zu 2732, Miete 9.21 zu 9.96 (Änderung über 5 %)
- Hochdorf (08116027, ergebnis2): gelb zu grün, Kauf 3365 zu 3365, Miete 12.64 zu 12.89 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Bischofsheim i.d.Rhön (09673117, ergebnis2): unbewertet zu gelb, Kauf 2050 zu 2050, Miete None zu 7.9 (Änderung über 5 %)
- Gschwend (08136027, ergebnis2): gelb zu grün, Kauf 2690 zu 2690, Miete 9.97 zu 10.04 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Neunkirchen a.Sand (09574141, ergebnis2): gelb zu grün, Kauf 2932 zu 2932, Miete 10.9 zu 11.28 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Krautheim (08126045, ergebnis2): gelb zu grün, Kauf 2116 zu 2116, Miete 9.23 zu 9.72 (Änderung über 5 %)
- Kirchberg i.Wald (09276126, ergebnis2): gelb zu grün, Kauf 2066 zu 2066, Miete 6.4 zu 7.33 (Änderung über 5 %)
- Zell a.Main (09679209, ergebnis2): gelb zu grün, Kauf 3535 zu 3535, Miete 12.4 zu 12.58 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Schönau (08226080, ergebnis2): unbewertet zu rot, Kauf 4450 zu 4450, Miete None zu 12.22 (Änderung über 5 %)
- Hohenthann (09274141, ergebnis2): rot zu gelb, Kauf 3510 zu 3669, Miete 9.7 zu 10.62 (Änderung über 5 %)
- Bad Berneck i.Fichtelgebirge (09472116, ergebnis2): gelb zu grün, Kauf 1691 zu 1691, Miete 6.99 zu 7.68 (Änderung über 5 %)
- Neureichenau (09272136, ergebnis2): gelb zu grün, Kauf 950 zu 1060, Miete 8.2 zu 8.01 (Änderung über 5 %)
- Freudenberg (09371122, ergebnis2): unbewertet zu rot, Kauf None zu 3638, Miete 10.79 zu 7.14 (Änderung über 5 %)
- Helmstadt-Bargen (08226106, ergebnis2): gelb zu grün, Kauf 2276 zu 2276, Miete 9.76 zu 10.3 (Änderung über 5 %)
- Mulfingen (08126056, ergebnis2): gelb zu grün, Kauf 2214 zu 2214, Miete 10.37 zu 10.47 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Beuren (08116011, ergebnis2): gelb zu grün, Kauf 2981 zu 2981, Miete 12.57 zu 12.62 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Oberrot (08127062, ergebnis2): gelb zu grün, Kauf 2424 zu 2424, Miete 8.48 zu 9.68 (Änderung über 5 %)
- Gundelsheim (09471137, ergebnis2): unbewertet zu gelb, Kauf None zu 3070, Miete 12.17 zu 11.87 (Änderung über 5 %)
- Dörfles-Esbach (09473120, ergebnis2): gelb zu grün, Kauf 2255 zu 2255, Miete 9.04 zu 9.37 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Ölbronn-Dürrn (08236075, ergebnis2): gelb zu grün, Kauf 3146 zu 3146, Miete 12.89 zu 12.13 (Änderung über 5 %)
- Luhe-Wildenau (09374133, ergebnis2): gelb zu grün, Kauf 1950 zu 1950, Miete 8.53 zu 9.23 (Änderung über 5 %)
- Wolframs-Eschenbach (09571229, ergebnis2): gelb zu grün, Kauf 2597 zu 2512, Miete 8.82 zu 9.4 (Änderung über 5 %)
- Uehlfeld (09575167, ergebnis2): gelb zu grün, Kauf 2536 zu 2584, Miete 9.44 zu 9.73 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Sand a.Main (09674195, ergebnis2): gelb zu grün, Kauf 2295 zu 2295, Miete 8.75 zu 8.88 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Oberasbach (09573122, ergebnis3): gelb zu grün, Kauf 3445 zu 3445, Miete 11.81 zu 12.3 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Eggenstein-Leopoldshafen (08215102, ergebnis3): gelb zu grün, Kauf 3498 zu 3498, Miete 12.18 zu 12.51 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Karlsdorf-Neuthard (08215103, ergebnis3): gelb zu grün, Kauf 3370 zu 3370, Miete 11.9 zu 12.02 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Dietenheim (08425028, ergebnis3): gelb zu grün, Kauf 3221 zu 3221, Miete 11.59 zu 11.77 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
- Laudenbach (08226040, ergebnis3): gelb zu grün, Kauf 2938 zu 2938, Miete 12.34 zu 12.41 (Änderung höchstens 5 %, Ampel nach denselben Regeln neu gerechnet)
