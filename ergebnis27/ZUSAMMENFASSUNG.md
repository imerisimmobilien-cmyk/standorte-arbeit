# ergebnis27: Praxismiete gegen Mietspiegel

## Umfang

Die 40 größten Städte nach Einwohnern (Destatis, 31.12.2024) plus Heidelberg, Ulm, Regensburg und Würzburg, zusammen 44 Städte. Der Süden ist vollständig dabei. Keine Neubewertung der Standorte, nur die Zusatztabelle `patch-praxismiete-01.json`.

## Vorgehen

- Mietspiegel: Art, Stand und der von Stadt, Mietspiegel-Dokumentation, Mieterverein oder Presse veröffentlichte Durchschnitt (Mittelwert oder Median) nettokalt, je mit Link. Wo nur Tabellenfelder veröffentlicht sind, bleibt der Durchschnitt leer und es gibt keinen Aufschlag.
- Angebotsmieten Neuvermietung (10/2026): miete-aktuell nach Wohnflächenklassen (30 bis 39 m² halb, 40 bis 69 m² voll gewichtet, also etwa 35 bis 70 m²) und immoportal Klasse 41 bis 60 m². Hat nur ein Portal eine ortsgeprüfte Größenklasse, kommt miet-check (alle Größen) als zweites Portal dazu. homeday steht nur daneben. Nur Portale, deren Stadtwert im Prüflauf ergebnis24 über PLZ, Landkreis oder Nachbarorte bestätigt wurde (strenge Ortsprüfung wie bisher).
- Aufschlag = Angebotsmiete 35 bis 70 m² gegenüber dem Mietspiegeldurchschnitt in Prozent.
- Mietpreisbremse aus den bisherigen Lieferungen, für Hamburg, Bremen, Rostock, Magdeburg und Halle neu recherchiert.

## Ergebnis

| Stadt | Mietspiegel | Art, Stand | Angebot 35 bis 70 m² | Portale | Aufschlag | Mietpreisbremse |
|---|---|---|---|---|---|---|
| Berlin | 7,71 (Median) | qualifiziert, Mietspiegel 2026, in Kraft seit 28.05.20 | 15,98 | 2 (1 mit Größenklasse) | 107,3 % | gilt |
| Hamburg | 9,94 (Median) | qualifiziert, Mietenspiegel 2025, Stichtag 01.04.2025 | 16,11 | 2 (1 mit Größenklasse) | 62,1 % | gilt |
| München | 15,38 | qualifiziert, Mietspiegel 2025 | 24,01 | 2 (2 mit Größenklasse) | 56,1 % | gilt |
| Köln | kein Durchschnitt | einfach, Kölner Mietspiegel, Stand 01.04.2025 | 14,95 | 2 (2 mit Größenklasse) |  | gilt |
| Frankfurt am Main | 12,28 | qualifiziert, Mietspiegel 2026; Magistrat hat anerkann | 17,92 | 2 (1 mit Größenklasse) | 45,9 % | gilt |
| Düsseldorf | kein Durchschnitt | unklar, Mietspiegeltabelle von Haus & Grund und  | 14,88 | 2 (2 mit Größenklasse) |  | gilt |
| Stuttgart | 11,15 | qualifiziert, Mietspiegel 2025/2026, Januar 2025 bis D | 18,09 | 2 (2 mit Größenklasse) | 62,2 % | gilt |
| Leipzig | 6,56 | qualifiziert, Mietspiegel 2025 bis 2027, gültig 01.07. | 10,21 | 2 (2 mit Größenklasse) | 55,6 % | gilt |
| Dortmund | 7,10 | qualifiziert, Mietspiegel 2025/26, ab Januar 2025 | 10,03 | 2 (2 mit Größenklasse) | 41,3 % | gilt |
| Bremen | 7,69 (Median) | qualifiziert, Bremer Mietspiegel, erste Fassung 01.01. | 12,20 | 2 (1 mit Größenklasse) | 58,6 % | gilt |
| Essen | 7,41 | qualifiziert, Mietspiegel 2024, laut Drittquelle gülti | 10,57 | 2 (1 mit Größenklasse) | 42,6 % | nein |
| Dresden | 7,33 | qualifiziert, Mietspiegel 2025, gültig 01.01.2025 bis  | 10,16 | 2 (2 mit Größenklasse) | 38,6 % | gilt |
| Nürnberg | 10,33 | qualifiziert, Mietenspiegel 2026 (Vorgänger 2024) | 13,44 | 2 (2 mit Größenklasse) | 30,1 % | gilt |
| Hannover | 8,73 | qualifiziert, Mietspiegel 2025, Stichtag 01.04.2025, g | 11,93 | 2 (2 mit Größenklasse) | 36,7 % | gilt |
| Duisburg | kein Durchschnitt | unklar, unklar | 8,56 | 2 (2 mit Größenklasse) |  | nein |
| Bochum | 6,90 | qualifiziert, Mietspiegel 2025, Pressemeldung 04/2025 | 9,77 | 2 (2 mit Größenklasse) | 41,6 % | nein |
| Wuppertal | kein Durchschnitt | qualifiziert, Mietspiegel 2024, Stichtag 01.12.2024 | 9,10 | 2 (2 mit Größenklasse) |  | nein |
| Bielefeld | kein Durchschnitt | qualifiziert, Mietspiegel 2024 (Methodenbericht); ein  | 10,18 | 2 (2 mit Größenklasse) |  | gilt |
| Bonn | kein Durchschnitt | qualifiziert, Fortschreibung des Mietspiegels 2024 zum | 13,80 | 2 (2 mit Größenklasse) |  | gilt |
| Mannheim | 9,19 | qualifiziert, Mietspiegel 2025/2026, gültig ab 16.12.2 | 13,43 | 2 (1 mit Größenklasse) | 46,1 % | nein |
| Karlsruhe | 9,63 | qualifiziert, Mietspiegel 2025, in Kraft ab 01.01.2025 | 14,11 | 2 (2 mit Größenklasse) | 46,5 % | gilt |
| Münster | 9,85 | qualifiziert, Mietspiegel 2025, gültig 01.04.2025 bis  | 13,81 | 2 (1 mit Größenklasse) | 40,2 % | gilt |
| Augsburg | 9,80 | qualifiziert, Mietspiegel 2025, gilt laut Stadt zwei J | 15,01 | 2 (2 mit Größenklasse) | 53,2 % | gilt |
| Wiesbaden | kein Durchschnitt | einfach, 14. Fortschreibung, Stichtag 01.01.2025 | 14,14 | 2 (2 mit Größenklasse) |  | gilt |
| Gelsenkirchen | kein Durchschnitt | einfach, Mietspiegel 2026 des Gutachterausschusse | 7,55 | 2 (2 mit Größenklasse) |  | nein |
| Mönchengladbach | 7,01 | einfach, Mietspiegel 2026 des Gutachterausschusse | 10,12 | 2 (2 mit Größenklasse) |  | nein |
| Aachen | kein Durchschnitt | qualifiziert, Mietspiegel 2024 (Stichtag 01.06.2023);  | 12,11 | 2 (2 mit Größenklasse) |  | gilt |
| Braunschweig | 7,60 | qualifiziert, Mietspiegel 2025, im Amtsblatt April 202 | 10,23 | 2 (2 mit Größenklasse) | 34,6 % | gilt |
| Kiel | 8,41 | qualifiziert, Mietspiegel 2025, gültig ab 01.04.2025,  | 11,23 | 2 (2 mit Größenklasse) | 33,5 % | nein |
| Chemnitz | kein Durchschnitt | qualifiziert, Mietspiegel, gültig ab 01.07.2025 | 6,22 | 2 (2 mit Größenklasse) |  | nein |
| Magdeburg | kein Durchschnitt | qualifiziert, Mietspiegel 2024, anerkannt 18.01.2024,  | 7,72 | 2 (2 mit Größenklasse) |  | nein |
| Freiburg im Breisgau | 10,81 | qualifiziert, Mietspiegel 2025/2026, gültig 01.01.2025 | 15,12 | 1 (1 mit Größenklasse) | 39,9 % | gilt |
| Krefeld | 9,29 | einfach, Mietspiegel 2025 | 10,24 | 2 (2 mit Größenklasse) | 10,2 % | gilt |
| Halle (Saale) | kein Durchschnitt | unklar, Mietspiegel 2026 bis 2027 | 8,57 | 2 (1 mit Größenklasse) |  | nein |
| Mainz | kein Durchschnitt (Median) | qualifiziert, Mietspiegel 2025, Fortschreibung des Mie | 15,49 | 2 (1 mit Größenklasse) |  | gilt |
| Erfurt | kein Durchschnitt | unklar, Mietspiegel Fassung 01.07.2025 | 10,43 | 2 (2 mit Größenklasse) |  | gilt |
| Lübeck | 8,69 | qualifiziert, Mietspiegel 2025, gültig seit 01.02.2026 | 12,32 | 2 (2 mit Größenklasse) | 41,8 % | nein |
| Oberhausen | kein Durchschnitt | qualifiziert, Mietspiegel 2025, Amtsblatt 16.06.2025,  | 9,29 | 2 (1 mit Größenklasse) |  | nein |
| Rostock | 7,72 | qualifiziert, Mietspiegel 2026, gültig 01.05.2026 bis  | 10,98 | 2 (2 mit Größenklasse) | 42,2 % | gilt |
| Kassel | kein Durchschnitt | qualifiziert, Mietspiegel 2024 (bis 31.12.2025), Forts | 9,77 | 2 (2 mit Größenklasse) |  | nein |
| Heidelberg | 11,14 | qualifiziert, Mietspiegel 2025, gültig 01.10.2025 bis  | 15,83 | 2 (2 mit Größenklasse) | 42,1 % | gilt |
| Ulm | 9,82 | qualifiziert, Gemeinsamer Mietspiegel Ulm und Neu-Ulm  | 13,98 | 2 (2 mit Größenklasse) | 42,4 % | gilt |
| Regensburg | 10,92 | qualifiziert, Mietspiegel 2026, in Kraft seit 01.03.20 | 14,85 | 2 (2 mit Größenklasse) | 36,0 % | gilt |
| Würzburg | 9,89 | qualifiziert, Qualifizierter Mietspiegel, Fortschreibu | 13,75 | 2 (2 mit Größenklasse) | 39,0 % | gilt |

- Aufschlag berechenbar für 27 Städte, Spanne 10 bis 107 %, Median 42 %.
- Ohne belegten Mietspiegeldurchschnitt (kein Aufschlag): Köln, Düsseldorf, Duisburg, Wuppertal, Bielefeld, Bonn, Wiesbaden, Gelsenkirchen, Mönchengladbach, Aachen, Chemnitz, Magdeburg, Halle (Saale), Mainz, Erfurt, Oberhausen, Kassel.
- Frankfurt: Mietspiegel 2026 Mittelwert 12,28 €/m², Angebot 35 bis 70 m² 17,92 €/m², Aufschlag rund 46 %. Die Mietpreisbremse gilt; die hessische Verordnung läuft laut bisherigen Daten bis 25.11.2026, eine Verlängerung ist geplant.

## Einordnung

- Der Mietspiegel bildet Bestandsmieten der letzten sechs Jahre über alle Größen und Baujahre ab, die Angebotsmiete nur aktuelle Inserate. Ein großer Abstand ist deshalb normal und kein Beleg für erzielbare Abschlussmieten.
- Wo die Mietpreisbremse gilt, ist bei Wiedervermietung höchstens die ortsübliche Vergleichsmiete der konkreten Wohnung plus 10 % zulässig. Ausnahmen: Erstvermietung nach dem 01.10.2014 gebauter Wohnungen, Erstvermietung nach umfassender Modernisierung, höhere Vormiete. Der Mietspiegeldurchschnitt ist nicht die Vergleichsmiete einer bestimmten Wohnung. Für die Kalkulation zählt der Mietspiegelwert der Wohnung (Lage, Baujahr, Größe, Ausstattung).
- Berlin, Hamburg und Bremen veröffentlichen einen Median. Der Aufschlag fällt dort höher aus als gegenüber einem Mittelwert.
- Abschlussmieten sind nicht öffentlich belegt. Deshalb steht in `praxis` keine Zahl für tatsächlich erzielte Mieten.

## Kosten und Offenes

- Ungefährer Verbrauch: rund 4 US-Dollar (eine Mietspiegel-Recherche über 44 Städte, vier Suchen zur Mietpreisbremse, Auswertung per Skript aus vorhandenen Portalseiten).
- Offen: Mietspiegeldurchschnitte für die oben genannten Städte ohne veröffentlichten Durchschnitt. Mietspiegelstände einzelner Städte (Essen, Aachen, Bielefeld, Kassel, Düsseldorf) sind nicht abschließend bestätigt (siehe hinweis). Die Mietpreisbremse in Rostock beruht auf Sekundärquellen.
