# Zusammenfassung Nacharbeit (ergebnis12), neue Orte

Patches: `ergebnis12/patch-c-01.json` bis `patch-c-02.json`, Format wie ergebnis8. Jeder Eintrag hat `satz`, `id` und `ags`, dazu nur die geänderten Felder. `muster` nennt die Fehlermuster, `korrekturen` die geänderten Quellen, `ampelNeu` den Ampelwechsel. Geprüft sind alle 1847 Orte aus ergebnis5, ergebnis6 (Bayern), ergebnis7, ergebnis9, ergebnis10 und ergebnis11 (Hessen) sowie Oelsnitz/Vogtl. Geändert sind 173 Orte, je Satz: ergebnis10 8, ergebnis11 6, ergebnis6 146, ergebnis7 4, ergebnis9 9. Branch: `claude/laughing-sagan-q2wyfw`.

## Muster und Regeln

- (1) miete-aktuell-Pfade mit Zusatz: 42 Orte. Wo miete-aktuell fehlte, habe ich die Pfadform `<Ort>-<Zusatz>/<Ort>/` mit Zusätzen je Land durchprobiert. Das sind die Regierungsbezirke in Bayern (zum Beispiel `Eching-Niederbayern/Eching/`), in Brandenburg Mark, Spree, Havel und Elster (zum Beispiel `Falkenberg-Mark/Falkenberg/`), außerdem Landesnamen, Flüsse und der Kreisname. Ein Wert zählt nur, wenn die PLZ der Seite passt.
- (2) homeday leitet still auf einen anderen Ort um: 9 Orte. Jeder genutzte homeday-Pfad ist erneut aufgerufen und die Ziel-URL geprüft. Bloße Schreibvarianten wie Bindestrich, Klammer, Punkt oder ein weggelassener Zusatz zählen als derselbe Ort. Wenn die Seite auf einen anderen Ort umleitet, ist der Wert entfernt, etwa Dahlenburg zu Nahrendorf, Lebus zu Podelzig, Apensen zu Beckdorf oder Rosengarten zu Hamburg.
- (3) Gutachterwert bei nur einem Portalwert: 113 Orte. Neue Regel: Der Gutachter-Kreiswert zählt erst ab zwei Portalwerten. Bei nur einem Portalwert steht er im Beleg mit "nicht gewertet: nur ein Portalwert vorhanden", der Kaufwert ist dann der Portalwert und die Datenbasis gilt als dünn. In Brandenburg, Hessen, Schleswig-Holstein und Niedersachsen nutzt die Pipeline keinen Gutachterwert. Neu Zauche bleibt deshalb bei einer Kaufquelle (miete-aktuell) und dünner Datenbasis.
- (4) Ersatzwert nach gestrichenem Ausreißer: 35 Orte. Auslegung: Bleibt nach dem Streichen eines Ausreißers weniger als eine zweite Auftragsquelle übrig, kommt die Ersatzquelle hinzu, zuerst ohne-makler.net, dann Engel & Völkers, jeweils nur nach Landkreis-Prüfung. Sie wird zum ursprünglichen Wertesatz gelegt, die Ausreißerregel läuft neu. So entscheidet die Ersatzquelle, welcher der beiden abweichenden Werte stehen bleibt. Beispiel Golßen: miete-aktuell 2.265 und homeday 3.900 lagen über 50 % auseinander. ohne-makler.net 2.550 bestätigt miete-aktuell, homeday fällt über die 150-%-Regel heraus. Jeder Fall steht in `offen`.
- Ohne Prognose ist die Ampel höchstens gelb. Das galt schon. Die Prüfung aller Sätze fand keinen grünen Ort ohne Prognose. Der Hinweis in `offen` lautet jetzt "Prognose nicht abrufbar, Ampel höchstens gelb".

## Ampelwechsel

Zusammen 76: gelb zu rot 9, unbewertet zu gelb 22, grün zu gelb 26, rot zu gelb 6, gelb zu grün 11, unbewertet zu rot 2. Grün zu gelb kommt vor allem von Regel (3), bei der ein einzelner Portalwert ohne Gutachterwert die Datenbasis dünn macht. Unbewertet zu gelb kommt von den neu gefundenen miete-aktuell-Werten.

- Boos (09778120, ergebnis6): gelb zu rot, Kauf 3675 zu 3950, Miete 10.23 zu 10.23
- Breitenbrunn (09778121, ergebnis6): unbewertet zu gelb, Kauf None zu 3590, Miete 10.7 zu 10.68
- Oberhausen (09190135, ergebnis6): unbewertet zu gelb, Kauf None zu 3836, Miete 13.56 zu 12.54
- Rettenbach (09774174, ergebnis6): grün zu gelb, Kauf 3044 zu 2988, Miete 10.79 zu 10.79
- Niederrieden (09778177, ergebnis6): gelb zu rot, Kauf 3675 zu 3950, Miete 10.4 zu 10.4
- Waldstetten (09774191, ergebnis6): grün zu gelb, Kauf 2737 zu 2373, Miete 10.25 zu 10.25
- Eisenberg (09777125, ergebnis6): rot zu gelb, Kauf 3993 zu 4060, Miete 11.07 zu 11.29
- Wiesenbach (09774189, ergebnis6): unbewertet zu gelb, Kauf None zu 3294, Miete 10.61 zu 10.27
- Lichtenau (09571175, ergebnis6): gelb zu grün, Kauf 2390 zu 2465, Miete 9.34 zu 9.55
- Schopfloch (09571200, ergebnis6): gelb zu grün, Kauf 2448 zu 2568, Miete 9.48 zu 9.13
- Marktleuthen (09479135, ergebnis6): gelb zu grün, Kauf 1050 zu 2001, Miete 7.29 zu 7.29
- Mönchberg (09676141, ergebnis6): gelb zu rot, Kauf 2966 zu 3332, Miete 9.13 zu 9.13
- Collenberg (09676117, ergebnis6): grün zu gelb, Kauf 2718 zu 2901, Miete 9.72 zu 9.72
- Kirchheim (09679153, ergebnis6): rot zu gelb, Kauf 3194 zu 3098, Miete 8.57 zu 8.67
- Mespelbrunn (09671141, ergebnis6): gelb zu grün, Kauf 1950 zu 1917, Miete 9.77 zu 9.77
- Auerbach (09271113, ergebnis6): unbewertet zu gelb, Kauf None zu 2488, Miete 9.59 zu 8.81
- Kirchensittenbach (09574135, ergebnis6): gelb zu rot, Kauf 3286 zu 3573, Miete 9.2 zu 9.2
- Waffenbrunn (09372168, ergebnis6): gelb zu grün, Kauf 1980 zu 1980, Miete 5.86 zu 7.76
- Haibach (09278129, ergebnis6): unbewertet zu gelb, Kauf None zu 2828, Miete 10.16 zu 9.16
- Feldkirchen (09278121, ergebnis6): unbewertet zu gelb, Kauf None zu 3141, Miete 10.58 zu 9.16
- Kleinrinderfeld (09679155, ergebnis6): rot zu gelb, Kauf 2836 zu 2836, Miete 7.56 zu 9.42
- Berg (09475113, ergebnis6): rot zu gelb, Kauf 11156 zu 2363, Miete 7.75 zu 7.46
- Neukirchen (09278154, ergebnis6): gelb zu rot, Kauf 3079 zu 3358, Miete 9.17 zu 9.17
- Mühlhausen (09572143, ergebnis6): unbewertet zu gelb, Kauf None zu 3244, Miete 9.83 zu 9.43
- Tiefenbach (09372163, ergebnis6): unbewertet zu gelb, Kauf None zu 2155, Miete 6.94 zu 6.47
- Zell (09372167, ergebnis6): grün zu gelb, Kauf 2354 zu 2707, Miete 8.74 zu 8.74
- Rettenbach (09372150, ergebnis6): unbewertet zu gelb, Kauf None zu 1140, Miete 9.97 zu 9.45
- Polsingen (09577162, ergebnis6): grün zu gelb, Kauf 2225 zu 2050, Miete 9.5 zu 9.5
- Schneeberg (09676156, ergebnis6): unbewertet zu rot, Kauf None zu 2947, Miete 7.87 zu 7.83
- Michelsneukirchen (09372142, ergebnis6): gelb zu rot, Kauf 2575 zu 3150, Miete 8.69 zu 8.69
- Velden (09574160, ergebnis6): unbewertet zu gelb, Kauf None zu 2667, Miete 9.32 zu 8.87
- Irchenrieth (09374127, ergebnis6): grün zu gelb, Kauf 1800 zu 1800, Miete 9.89 zu 9.89
- Püchersreuth (09374150, ergebnis6): grün zu gelb, Kauf 1775 zu 1750, Miete 9.47 zu 9.47
- Leutenbach (09474147, ergebnis6): rot zu gelb, Kauf 3669 zu 3401, Miete 9.04 zu 9.68
- Himmelstadt (09677142, ergebnis6): grün zu gelb, Kauf 2300 zu 2100, Miete 10.16 zu 10.16
- Etzenricht (09374119, ergebnis6): grün zu gelb, Kauf 1975 zu 2150, Miete 9.88 zu 9.88
- Flossenbürg (09374122, ergebnis6): grün zu gelb, Kauf 1700 zu 1600, Miete 8.5 zu 8.5
- Wilhelmsdorf (09575181, ergebnis6): unbewertet zu gelb, Kauf None zu 3130, Miete 11.84 zu 9.92
- Neunkirchen (09676143, ergebnis6): unbewertet zu gelb, Kauf None zu 2944, Miete 6.3 zu 9.38
- Urspringen (09677193, ergebnis6): grün zu gelb, Kauf 2275 zu 2050, Miete 10.45 zu 10.45
- Plech (09472177, ergebnis6): grün zu gelb, Kauf 1700 zu 1500, Miete 8.87 zu 8.87
- Trabitz (09374148, ergebnis6): grün zu gelb, Kauf 1825 zu 1850, Miete 9.86 zu 9.86
- Reichenbach (09372149, ergebnis6): grün zu gelb, Kauf 2439 zu 2878, Miete 8.93 zu 8.93
- Glashütten (09472141, ergebnis6): unbewertet zu gelb, Kauf None zu 3001, Miete 10.83 zu 10.2
- Mehlmeisel (09472164, ergebnis6): grün zu gelb, Kauf 1750 zu 1600, Miete 8.24 zu 8.24
- Aufseß (09472115, ergebnis6): grün zu gelb, Kauf 1700 zu 1500, Miete 8.28 zu 8.28
- Bruckberg (09571122, ergebnis6): unbewertet zu gelb, Kauf None zu 2914, Miete 9.58 zu 9.37
- Weigendorf (09371157, ergebnis6): grün zu gelb, Kauf 1925 zu 1650, Miete 9.42 zu 9.42
- Kohlberg (09374131, ergebnis6): unbewertet zu gelb, Kauf None zu 2916, Miete 7.98 zu 8.31
- Leuchtenberg (09374132, ergebnis6): grün zu gelb, Kauf 1875 zu 1950, Miete 9.32 zu 9.32
- Bergen (09577115, ergebnis6): unbewertet zu gelb, Kauf None zu 2859, Miete None zu 8.02
- Schwarzenbach (09374156, ergebnis6): grün zu gelb, Kauf 2173 zu 2545, Miete 7.84 zu 7.84
- Speinshart (09374157, ergebnis6): grün zu gelb, Kauf 1850 zu 1900, Miete 9.36 zu 9.36
- Reuth b.Erbendorf (09377149, ergebnis6): grün zu gelb, Kauf 1775 zu 1650, Miete 8.96 zu 8.96
- Bechtsrieth (09374170, ergebnis6): grün zu gelb, Kauf 1875 zu 1950, Miete 9.52 zu 9.52
- Stockheim (09673170, ergebnis6): unbewertet zu gelb, Kauf None zu 1670, Miete None zu 6.49
- Wettringen (09571222, ergebnis6): unbewertet zu gelb, Kauf None zu 2894, Miete 9.48 zu 9.05
- Holzkirchen (09679149, ergebnis6): unbewertet zu gelb, Kauf None zu 2884, Miete 10.31 zu 9.68
- Haag (09472146, ergebnis6): grün zu gelb, Kauf 2523 zu 3146, Miete 10.5 zu 10.5
- Falkenberg (09377117, ergebnis6): unbewertet zu rot, Kauf None zu 3284, Miete 8.33 zu 8.88
- Adelshofen (09571111, ergebnis6): unbewertet zu gelb, Kauf None zu 2486, Miete 9.6 zu 8.53
- Aura a.d.Saale (09672111, ergebnis6): grün zu gelb, Kauf 1825 zu 1650, Miete 8.45 zu 8.45
- Sulzthal (09672155, ergebnis6): grün zu gelb, Kauf 1825 zu 1650, Miete 8.5 zu 8.5
- Plankenfels (09472176, ergebnis6): grün zu gelb, Kauf 1975 zu 2050, Miete 8.75 zu 8.75
- Ahorn (08128138, ergebnis7): unbewertet zu gelb, Kauf 1950 zu 1950, Miete None zu 9.41
- Rosenberg (08225082, ergebnis7): gelb zu grün, Kauf 2050 zu 2475, Miete 9.21 zu 8.79
- Zwingenberg (08225113, ergebnis7): unbewertet zu gelb, Kauf None zu 2987, Miete 10.41 zu 9.34
- Beeskow (12067036, ergebnis9): gelb zu grün, Kauf 2000 zu 2469, Miete 9.49 zu 9.49
- Rehfelde (12064408, ergebnis9): gelb zu grün, Kauf 2150 zu 2896, Miete 12.86 zu 12.86
- Spreenhagen (12067469, ergebnis9): gelb zu grün, Kauf 2863 zu 2863, Miete 9.19 zu 11.72
- Golßen (12061164, ergebnis9): gelb zu rot, Kauf 2265 zu 2407, Miete 6.57 zu 6.57
- Falkenberg (12064125, ergebnis9): gelb zu rot, Kauf 2512 zu 2743, Miete 7.09 zu 7.22
- Britz (12060036, ergebnis9): gelb zu rot, Kauf 1998 zu 3944, Miete 9.34 zu 9.34
- Scharnebeck (03355033, ergebnis10): gelb zu grün, Kauf 2100 zu 2819, Miete 11.6 zu 11.6
- Calden (06633005, ergebnis11): gelb zu grün, Kauf 1900 zu 1872, Miete 8.95 zu 8.95
- Helsa (06633012, ergebnis11): rot zu gelb, Kauf 2649 zu 2649, Miete 6.17 zu 7.64

## Geänderte Quellen (Muster 1 und 2)

- breitenbrunn (09778121): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Breitenbrunn-Schwaben/Breitenbrunn/ (Wert 3589.77); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Breitenbrunn-Schwaben/Breitenbrunn/ (Wert 10.65)
- oberhausen (09190135): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Oberhausen-Oberbayern/Oberhausen/ (Wert 3836.27); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Oberhausen-Oberbayern/Oberhausen/ (Wert 11.52)
- brunnen (09185123): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/muennerstadt/bruenn+97702 (Wert 1850.0); homeday Miete: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/muennerstadt/bruenn+97702 (Wert 6.0)
- niederbergkirchen (09183130): homeday Miete: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/frontenhausen (Wert 7.9)
- wald (09777179): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Wald-Ostallgaeu/Wald/ (Wert 3588.13); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Wald-Ostallgaeu/Wald/ (Wert 12.53)
- eisenberg (09777125): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Eisenberg-Allgaeu/Eisenberg/ (Wert 4194.32); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Eisenberg-Allgaeu/Eisenberg/ (Wert 10.32)
- wiesenbach (09774189): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Wiesenbach-Schwaben/Wiesenbach/ (Wert 3293.54); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Wiesenbach-Schwaben/Wiesenbach/ (Wert 9.94)
- lichtenau (09571175): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Lichtenau-Mittelfranken/Lichtenau/ (Wert 2616.23); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Lichtenau-Mittelfranken/Lichtenau/ (Wert 9.42)
- schopfloch (09571200): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Schopfloch-Mittelfranken/Schopfloch/ (Wert 2806.75); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Schopfloch-Mittelfranken/Schopfloch/ (Wert 8.99)
- bad-weissenstadt (09479166): homeday Miete: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/weissenstadt (Wert 5.8)
- kirchheim (09679153): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Kirchheim-Unterfranken/Kirchheim/ (Wert 2905.74); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Kirchheim-Unterfranken/Kirchheim/ (Wert 8.21)
- ensdorf (09371120): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Ensdorf-Oberpfalz/Ensdorf/ (Wert 3045.08); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Ensdorf-Oberpfalz/Ensdorf/ (Wert 9.08)
- auerbach (09271113): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Auerbach-Niederbayern/Auerbach/ (Wert 2487.5); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Auerbach-Niederbayern/Auerbach/ (Wert 8.04)
- haibach (09278129): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Haibach-Niederbayern/Haibach/ (Wert 2828.34); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Haibach-Niederbayern/Haibach/ (Wert 8.17)
- feldkirchen (09278121): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Feldkirchen-Niederbayern/Feldkirchen/ (Wert 3141.21); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Feldkirchen-Niederbayern/Feldkirchen/ (Wert 7.75)
- berg (09475113): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Berg-Oberfranken/Berg/ (Wert 2362.99); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Berg-Oberfranken/Berg/ (Wert 7.18)
- muehlhausen (09572143): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Muehlhausen-Mittelfranken/Muehlhausen/ (Wert 3244.2); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Muehlhausen-Mittelfranken/Muehlhausen/ (Wert 9.03)
- tiefenbach (09372163): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Tiefenbach-Oberpfalz/Tiefenbach/ (Wert 2155.32); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Tiefenbach-Oberpfalz/Tiefenbach/ (Wert 6.01)
- rimbach-09372151 (09372151): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Rimbach-Oberpfalz/Rimbach/ (Wert 2698.74); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Rimbach-Oberpfalz/Rimbach/ (Wert 7.44)
- rettenbach-09372150 (09372150): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Rettenbach-Oberpfalz/Rettenbach/ (Wert 1140.37); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Rettenbach-Oberpfalz/Rettenbach/ (Wert 8.92)
- schneeberg (09676156): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Schneeberg-Unterfranken/Schneeberg/ (Wert 2947.37); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Schneeberg-Unterfranken/Schneeberg/ (Wert 7.78)
- velden (09574160): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Velden-Mittelfranken/Velden/ (Wert 2667.33); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Velden-Mittelfranken/Velden/ (Wert 8.41)
- leutenbach (09474147): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Leutenbach-Oberfranken/Leutenbach/ (Wert 2866.4); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Leutenbach-Oberfranken/Leutenbach/ (Wert 8.52)
- laudenbach (09676135): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Laudenbach-Unterfranken/Laudenbach/ (Wert 3257.89); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Laudenbach-Unterfranken/Laudenbach/ (Wert 10.72)
- remlingen (09679177): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Remlingen-Unterfranken/Remlingen/ (Wert 2949.03); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Remlingen-Unterfranken/Remlingen/ (Wert 8.66)
- hartenstein (09574129): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Hartenstein-Mittelfranken/Hartenstein/ (Wert 2673.13); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Hartenstein-Mittelfranken/Hartenstein/ (Wert 7.98)
- wilhelmsdorf (09575181): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Wilhelmsdorf-Mittelfranken/Wilhelmsdorf/ (Wert 3130.38); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Wilhelmsdorf-Mittelfranken/Wilhelmsdorf/ (Wert 9.15)
- neunkirchen (09676143): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Neunkirchen-Unterfranken/Neunkirchen/ (Wert 2943.56); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Neunkirchen-Unterfranken/Neunkirchen/ (Wert 9.29)
- bad-neualbenreuth (09377142): homeday Miete: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/neualbenreuth (Wert 5.3)
- glashuetten (09472141): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Glashuetten-Oberfranken/Glashuetten/ (Wert 3000.96); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Glashuetten-Oberfranken/Glashuetten/ (Wert 9.56)
- bruckberg (09571122): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Bruckberg-Mittelfranken/Bruckberg/ (Wert 2913.51); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Bruckberg-Mittelfranken/Bruckberg/ (Wert 9.16)
- kohlberg (09374131): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Kohlberg-Oberpfalz/Kohlberg/ (Wert 2915.6); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Kohlberg-Oberpfalz/Kohlberg/ (Wert 8.35)
- bergen (09577115): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Bergen-Mittelfranken/Bergen/ (Wert 2859.1); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Bergen-Mittelfranken/Bergen/ (Wert 8.02)
- leonberg (09377137): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Leonberg-Oberpfalz/Leonberg/ (Wert 2578.85); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Leonberg-Oberpfalz/Leonberg/ (Wert 6.01)
- stockheim (09673170): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Stockheim-Unterfranken/Stockheim/ (Wert 1669.64); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Stockheim-Unterfranken/Stockheim/ (Wert 6.49)
- wettringen (09571222): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Wettringen-Mittelfranken/Wettringen/ (Wert 2893.62); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Wettringen-Mittelfranken/Wettringen/ (Wert 8.62)
- holzkirchen (09679149): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Holzkirchen-Unterfranken/Holzkirchen/ (Wert 2884.25); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Holzkirchen-Unterfranken/Holzkirchen/ (Wert 9.04)
- falkenberg (09377117): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Falkenberg-Oberpfalz/Falkenberg/ (Wert 3284.49); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Falkenberg-Oberpfalz/Falkenberg/ (Wert 9.43)
- adelshofen (09571111): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Adelshofen-Mittelfranken/Adelshofen/ (Wert 2486.48); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Adelshofen-Mittelfranken/Adelshofen/ (Wert 7.46)
- rammingen (08425097): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Rammingen-Wuerttemberg/Rammingen/ (Wert 3246.35); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Rammingen-Wuerttemberg/Rammingen/ (Wert 9.71)
- ahorn (08128138): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Ahorn-Baden/Ahorn/ (Wert 3121.76); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Ahorn-Baden/Ahorn/ (Wert 9.41)
- rosenberg-08225082 (08225082): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Rosenberg-Baden/Rosenberg/ (Wert 2899.44); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Rosenberg-Baden/Rosenberg/ (Wert 8.37)
- zwingenberg (08225113): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Zwingenberg-Baden/Zwingenberg/ (Wert 2987.47); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Zwingenberg-Baden/Zwingenberg/ (Wert 8.26)
- lebus (12064268): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/podelzig (Wert 1450.0)
- friedland (12067137): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Friedland-Mark/Friedland/ (Wert 3106.83); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Friedland-Mark/Friedland/ (Wert 9.04)
- falkenberg (12064125): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Falkenberg-Mark/Falkenberg/ (Wert 2973.86); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Falkenberg-Mark/Falkenberg/ (Wert 7.76)
- rosengarten (03353029): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/hamburg (Wert 6000.0); homeday Miete: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/hamburg (Wert 13.2)
- apensen (03359003): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/beckdorf (Wert 4100.0); homeday Miete: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/beckdorf (Wert 8.6)
- deutsch-evern (03355014): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/sehnde/evern,+niedersachsen+31319 (Wert 2950.0)
- dahlenburg (03355013): homeday Kauf: entfernt, stille Umleitung auf https://www.homeday.de/de/preisatlas/nahrendorf (Wert 2000.0)
- staufenberg (06531017): miete-aktuell Kauf: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/immobilienpreise-quadratmeterpreise/Staufenberg-Hessen/Staufenberg/ (Wert 3043.49); miete-aktuell Miete: ergänzt über Pfad mit Zusatz https://www.miete-aktuell.de/mietspiegel/Staufenberg-Hessen/Staufenberg/ (Wert 10.33)

Hinweis: Eching (Landkreis Landshut, 09274124) aus dem Beispiel steht in ergebnis2, nicht in den neuen Sätzen. Für ergebnis2 und ergebnis3 lief diese Nacharbeit noch nicht.

