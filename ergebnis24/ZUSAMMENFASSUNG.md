# Zusammenfassung ergebnis24: Prüflauf Kauf und Miete, Städte ab 50.000 Einwohnern

Branch: `claude/laughing-sagan-q2wyfw`, kein Pull Request. Datei: `patch-01.json`, nur für Städte mit mehr als 15 % Abweichung. Die id ist die CRM-Kennung aus der Liste.

## Umfang und Vorgehen

- **Geprüft:** alle 168 Städte der Liste, per Skript mit der bestehenden Pipeline. Abruf am 21.10.2026 bei immoportal, homeday, miete-aktuell und miet-check. Dazu kamen Ortsprüfung, strenge Prüfung gleichnamiger Orte, Prüfung der homeday-Umleitungen und Ersatzquellen nur nach Regel.
- **Regeln** wie ergebnis14 bis 21:
  - Kauf ist das Mittel aus immoportal, homeday und miete-aktuell.
  - Miete ist das Mittel aus immoportal, miete-aktuell und miet-check; homeday zählt nur daneben.
  - Ausreißer werden nur unter Portalwerten bestimmt.
  - Es gilt die Zwei-Werte-Regel.
  - miet-check wird jetzt in beiden Seitenlayouts gelesen.
- **Stadtwert:** Es zählen nur Seiten der Gesamtstadt, keine Stadtteilseiten.
- **miete-aktuell, neu:**
  - Je Stadt wird geprüft, ob der gelesene Wert dem Jahr 2026 der Verlaufstabelle entspricht; sonst wird der 2026er Wert genommen.
  - Liegt 2026 gegenüber 2025 mehr als 50 % daneben, ist die Seite als Portalfehler nicht gewertet.
  - Ergebnis: bei allen 168 Städten war der gelesene Wert der 2026er, kein Sprung über 50 %.
- **Nicht neu erhoben:** Prognose, Mietpreisbremse und Stufe-2-Felder.
  - Die Prognose ist nur als Grundlage der Ampel im Patch abgerufen (Bayern: Demographie-Spiegel, Brandenburg: LBV, sonst Wegweiser Kommune).
  - Für Hamburg, Bremen, das Saarland, Mecklenburg-Vorpommern und Sachsen-Anhalt steht im Patch „Mietpreisbremse laut bisherigen Daten“.

## Städte mit Abweichung über 15 % (1)

| Stadt | Kauf alt | Kauf neu | Abw. | Miete alt | Miete neu | Abw. | Grund |
|---|---|---|---|---|---|---|---|
| Hamm | 2.083 | 2.515 | +20,7 % | 8,03 | 8,24 | +2,6 % | Kauf +20,7 %: neu aus miete-aktuell 2.157, ohne-makler.net 2.872 (Ersatz) |

Hamm: immoportal und homeday bestehen die strenge Ortsprüfung nicht. Es gibt mehrere Orte namens Hamm, und die Seiten sind nicht eindeutig der kreisfreien Stadt Hamm zuzuordnen. Deshalb kam nach der Regel die Ersatzquelle ohne-makler.net dazu. Der neue Kaufwert stützt sich also auf miete-aktuell und eine Ersatzquelle und sollte lokal geprüft werden.

## Städte unter 15 % (167, ohne Patch)

Die meisten Werte sind gleich oder nahezu gleich: Die Portale haben seit dem Abruf vom 18.10.2026 kaum neue Stände. Die größten Abweichungen haben Leverkusen (Kauf -12,6 %) und Langenfeld (Miete +11,6 %).

| Stadt | Kauf CRM | Kauf neu | Abw. | Miete CRM | Miete neu | Abw. |
|---|---|---|---|---|---|---|
| Berlin | 5.416 | 5.567 | 2,8 % | 15,65 | 15,55 | -0,6 % |
| Hamburg | 6.094 | 6.145 | 0,8 % | 15,51 | 15,68 | 1,1 % |
| München | 7.985 | 7.985 | 0,0 % | 21,89 | 21,89 | 0,0 % |
| Köln | 4.790 | 4.948 | 3,3 % | 14,91 | 14,91 | 0,0 % |
| Frankfurt am Main | 5.670 | 5.403 | -4,7 % | 17,68 | 17,43 | -1,4 % |
| Düsseldorf | 4.629 | 4.638 | 0,2 % | 15,01 | 15,02 | 0,1 % |
| Leipzig | 3.032 | 2.903 | -4,3 % | 10,47 | 10,47 | 0,0 % |
| Stuttgart | 4.349 | 4.414 | 1,5 % | 17,08 | 17,08 | 0,0 % |
| Dortmund | 2.468 | 2.523 | 2,2 % | 9,96 | 9,96 | 0,0 % |
| Bremen | 2.813 | 2.915 | 3,6 % | 11,65 | 11,89 | 2,1 % |
| Essen | 2.503 | 2.508 | 0,2 % | 10,02 | 10,30 | 2,8 % |
| Dresden | 2.897 | 2.959 | 2,1 % | 10,48 | 10,48 | 0,0 % |
| Nürnberg | 3.887 | 3.621 | -6,8 % | 13,53 | 13,53 | 0,0 % |
| Hannover | 3.262 | 3.349 | 2,7 % | 11,67 | 12,00 | 2,8 % |
| Duisburg | 1.725 | 1.713 | -0,7 % | 8,51 | 8,51 | 0,0 % |
| Bochum | 2.261 | 2.323 | 2,7 % | 9,85 | 9,85 | 0,0 % |
| Wuppertal | 2.016 | 2.091 | 3,7 % | 9,18 | 9,18 | 0,0 % |
| Bielefeld | 2.532 | 2.585 | 2,1 % | 10,03 | 10,03 | 0,0 % |
| Bonn | 3.867 | 3.932 | 1,7 % | 13,69 | 13,69 | 0,0 % |
| Mannheim | 3.883 | 3.743 | -3,6 % | 13,06 | 13,06 | 0,0 % |
| Karlsruhe | 3.960 | 4.004 | 1,1 % | 13,70 | 13,70 | 0,0 % |
| Münster | 4.377 | 4.374 | -0,1 % | 13,35 | 13,45 | 0,7 % |
| Augsburg | 4.411 | 4.229 | -4,1 % | 14,72 | 14,72 | 0,0 % |
| Wiesbaden | 4.146 | 4.247 | 2,4 % | 14,07 | 14,06 | -0,1 % |
| Mönchengladbach | 2.178 | 2.220 | 1,9 % | 10,09 | 10,09 | 0,0 % |
| Gelsenkirchen | 1.634 | 1.523 | -6,8 % | 7,50 | 7,50 | 0,0 % |
| Aachen | 3.189 | 3.190 | 0,0 % | 12,01 | 12,01 | 0,0 % |
| Braunschweig | 2.774 | 2.895 | 4,4 % | 10,31 | 10,31 | 0,0 % |
| Kiel | 3.229 | 3.351 | 3,8 % | 11,35 | 11,35 | 0,0 % |
| Chemnitz | 1.252 | 1.258 | 0,5 % | 6,25 | 6,25 | 0,0 % |
| Magdeburg | 2.103 | 1.984 | -5,7 % | 7,89 | 7,89 | 0,0 % |
| Freiburg im Breisgau | 5.179 | 5.189 | 0,2 % | 14,19 | 14,34 | 1,1 % |
| Krefeld | 2.275 | 2.355 | 3,5 % | 10,14 | 10,15 | 0,1 % |
| Halle (Saale) | 2.532 | 2.420 | -4,4 % | 8,10 | 8,36 | 3,2 % |
| Mainz | 4.047 | 4.187 | 3,5 % | 15,12 | 15,12 | 0,0 % |
| Erfurt | 2.663 | 2.717 | 2,0 % | 10,63 | 10,63 | 0,0 % |
| Lübeck | 3.868 | 3.934 | 1,7 % | 12,40 | 12,40 | 0,0 % |
| Oberhausen | 2.101 | 2.016 | -4,0 % | 8,87 | 9,05 | 2,0 % |
| Rostock | 3.566 | 3.766 | 5,6 % | 11,41 | 11,40 | -0,1 % |
| Kassel | 2.704 | 2.761 | 2,1 % | 9,94 | 9,94 | 0,0 % |
| Hagen | 1.694 | 1.639 | -3,2 % | 7,51 | 7,67 | 2,1 % |
| Potsdam | 5.058 | 4.720 | -6,7 % | 13,64 | 13,64 | 0,0 % |
| Saarbrücken | 2.192 | 2.195 | 0,1 % | 10,55 | 10,55 | 0,0 % |
| Ludwigshafen am Rhein | 2.911 | 2.715 | -6,7 % | 11,96 | 11,80 | -1,3 % |
| Oldenburg (Oldb) | 3.172 | 3.289 | 3,7 % | 11,73 | 11,73 | 0,0 % |
| Mülheim an der Ruhr | 2.450 | 2.566 | 4,7 % | 9,72 | 9,49 | -2,4 % |
| Leverkusen | 3.097 | 2.708 | -12,6 % | 11,66 | 11,66 | 0,0 % |
| Darmstadt | 4.405 | 4.411 | 0,1 % | 15,02 | 15,02 | 0,0 % |
| Osnabrück | 2.855 | 2.988 | 4,7 % | 11,22 | 11,22 | 0,0 % |
| Solingen | 2.446 | 2.514 | 2,8 % | 9,84 | 9,84 | 0,0 % |
| Herne | 1.746 | 1.781 | 2,0 % | 7,97 | 7,97 | 0,0 % |
| Heidelberg | 4.837 | 4.982 | 3,0 % | 15,58 | 15,58 | 0,0 % |
| Paderborn | 2.906 | 2.974 | 2,3 % | 10,50 | 10,50 | 0,0 % |
| Neuss | 3.083 | 3.162 | 2,6 % | 12,31 | 12,31 | 0,0 % |
| Regensburg | 4.606 | 4.606 | 0,0 % | 14,45 | 14,45 | 0,0 % |
| Ingolstadt | 4.156 | 4.155 | -0,0 % | 13,75 | 13,76 | 0,1 % |
| Pforzheim | 2.894 | 3.003 | 3,8 % | 11,01 | 11,01 | 0,0 % |
| Würzburg | 3.827 | 3.857 | 0,8 % | 13,45 | 13,45 | 0,0 % |
| Offenbach am Main | 3.727 | 3.923 | 5,3 % | 14,42 | 14,13 | -2,0 % |
| Fürth | 3.727 | 3.454 | -7,3 % | 12,90 | 12,91 | 0,1 % |
| Göttingen | 3.211 | 3.036 | -5,5 % | 12,11 | 12,10 | -0,1 % |
| Ulm | 4.207 | 4.207 | 0,0 % | 13,69 | 13,70 | 0,1 % |
| Wolfsburg | 2.344 | 2.368 | 1,0 % | 9,25 | 9,24 | -0,1 % |
| Bremerhaven | 1.696 | 1.763 | 4,0 % | 8,00 | 8,29 | 3,6 % |
| Bottrop | 2.227 | 2.268 | 1,8 % | 9,14 | 9,13 | -0,1 % |
| Erlangen | 4.013 | 4.012 | -0,0 % | 14,50 | 14,50 | 0,0 % |
| Recklinghausen | 2.170 | 2.246 | 3,5 % | 8,23 | 8,23 | 0,0 % |
| Remscheid | 1.962 | 2.050 | 4,5 % | 7,99 | 8,00 | 0,1 % |
| Koblenz | 3.011 | 3.092 | 2,7 % | 11,10 | 11,10 | 0,0 % |
| Bergisch Gladbach | 3.130 | 3.192 | 2,0 % | 12,51 | 12,52 | 0,1 % |
| Jena | 3.275 | 3.370 | 2,9 % | 12,53 | 12,54 | 0,1 % |
| Trier | 3.326 | 3.554 | 6,9 % | 12,26 | 12,25 | -0,1 % |
| Salzgitter | 1.423 | 1.487 | 4,5 % | 7,17 | 7,17 | 0,0 % |
| Siegen | 2.287 | 2.402 | 5,0 % | 8,86 | 8,86 | 0,0 % |
| Moers | 2.268 | 2.270 | 0,1 % | 9,78 | 9,79 | 0,1 % |
| Kaiserslautern | 2.434 | 2.435 | 0,0 % | 10,86 | 10,86 | 0,0 % |
| Gütersloh | 2.600 | 2.664 | 2,5 % | 10,14 | 10,13 | -0,1 % |
| Hanau | 2.988 | 3.069 | 2,7 % | 12,76 | 12,76 | 0,0 % |
| Hildesheim | 2.171 | 2.266 | 4,4 % | 9,40 | 9,41 | 0,1 % |
| Schwerin | 2.217 | 2.407 | 8,6 % | 10,12 | 10,20 | 0,8 % |
| Flensburg | 2.563 | 2.558 | -0,2 % | 9,90 | 9,89 | -0,1 % |
| Gera | 1.192 | 1.254 | 5,2 % | 6,64 | 6,64 | 0,0 % |
| Düren | 2.043 | 2.115 | 3,5 % | 9,96 | 9,96 | 0,0 % |
| Tübingen | 4.739 | 4.739 | 0,0 % | 15,53 | 15,53 | 0,0 % |
| Witten | 2.344 | 2.441 | 4,1 % | 8,68 | 8,67 | -0,1 % |
| Iserlohn | 1.710 | 1.718 | 0,5 % | 7,91 | 7,90 | -0,1 % |
| Ratingen | 3.152 | 3.259 | 3,4 % | 12,63 | 12,63 | 0,0 % |
| Gießen | 3.424 | 3.492 | 2,0 % | 12,03 | 12,04 | 0,1 % |
| Worms | 2.724 | 2.724 | 0,0 % | 10,99 | 10,99 | 0,0 % |
| Marl | 1.907 | 1.939 | 1,7 % | 8,18 | 8,18 | 0,0 % |
| Konstanz | 5.299 | 5.299 | 0,0 % | 16,58 | 16,58 | 0,0 % |
| Lünen | 2.302 | 2.417 | 5,0 % | 8,38 | 8,38 | 0,0 % |
| Minden | 2.042 | 2.094 | 2,5 % | 9,84 | 9,84 | 0,0 % |
| Norderstedt | 3.976 | 3.987 | 0,3 % | 14,51 | 14,52 | 0,1 % |
| Velbert | 2.232 | 2.368 | 6,1 % | 8,69 | 8,69 | 0,0 % |
| Delmenhorst | 2.066 | 2.114 | 2,3 % | 9,66 | 9,66 | 0,0 % |
| Neumünster | 2.026 | 2.026 | 0,0 % | 9,85 | 9,85 | 0,0 % |
| Viersen | 2.293 | 2.309 | 0,7 % | 9,75 | 9,74 | -0,1 % |
| Rheine | 2.406 | 2.470 | 2,7 % | 10,54 | 10,52 | -0,2 % |
| Bamberg | 3.600 | 3.613 | 0,4 % | 13,24 | 13,24 | 0,0 % |
| Troisdorf | 3.112 | 3.178 | 2,1 % | 12,21 | 12,21 | 0,0 % |
| Gladbeck | 1.988 | 2.057 | 3,5 % | 8,06 | 8,06 | 0,0 % |
| Wilhelmshaven | 1.533 | 1.618 | 5,5 % | 7,41 | 7,41 | 0,0 % |
| Dessau-Roßlau | 1.300 | 1.341 | 3,2 % | 7,28 | 7,19 | -1,2 % |
| Dorsten | 2.046 | 2.085 | 1,9 % | 8,01 | 8,01 | 0,0 % |
| Lüneburg | 3.580 | 3.779 | 5,6 % | 12,45 | 12,45 | 0,0 % |
| Arnsberg | 1.928 | 1.968 | 2,1 % | 7,92 | 7,92 | 0,0 % |
| Detmold | 1.907 | 1.955 | 2,5 % | 9,14 | 9,14 | 0,0 % |
| Marburg | 3.331 | 3.487 | 4,7 % | 12,57 | 12,56 | -0,1 % |
| Bocholt | 2.735 | 2.842 | 3,9 % | 10,33 | 10,33 | 0,0 % |
| Castrop-Rauxel | 2.068 | 1.953 | -5,6 % | 8,32 | 8,32 | 0,0 % |
| Lüdenscheid | 1.842 | 1.899 | 3,1 % | 7,35 | 7,34 | -0,1 % |
| Lippstadt | 2.466 | 2.552 | 3,5 % | 9,41 | 9,23 | -1,9 % |
| Neuwied | 2.550 | 2.639 | 3,5 % | 9,49 | 9,50 | 0,1 % |
| Herford | 2.127 | 2.173 | 2,2 % | 8,81 | 8,81 | 0,0 % |
| Celle | 1.953 | 2.051 | 5,0 % | 9,52 | 9,52 | 0,0 % |
| Dinslaken | 2.456 | 2.510 | 2,2 % | 9,30 | 9,30 | 0,0 % |
| Kerpen | 2.514 | 2.497 | -0,7 % | 11,44 | 11,43 | -0,1 % |
| Rüsselsheim am Main | 3.261 | 3.324 | 1,9 % | 13,32 | 12,90 | -3,2 % |
| Fulda | 3.142 | 3.269 | 4,0 % | 10,30 | 10,30 | 0,0 % |
| Grevenbroich | 2.467 | 2.531 | 2,6 % | 10,53 | 10,53 | 0,0 % |
| Schwäbisch Gmünd | 2.812 | 2.916 | 3,7 % | 11,41 | 11,41 | 0,0 % |
| Dormagen | 2.779 | 2.803 | 0,9 % | 11,63 | 11,65 | 0,2 % |
| Offenburg | 3.107 | 3.214 | 3,4 % | 11,69 | 11,69 | 0,0 % |
| Neu-Ulm | 3.466 | 3.469 | 0,1 % | 13,76 | 13,78 | 0,1 % |
| Bergheim | 2.023 | 1.931 | -4,5 % | 11,15 | 11,15 | 0,0 % |
| Hürth | 3.791 | 3.787 | -0,1 % | 13,51 | 13,51 | 0,0 % |
| Wesel | 1.813 | 1.833 | 1,1 % | 9,24 | 9,24 | 0,0 % |
| Herten | 1.932 | 1.969 | 1,9 % | 8,20 | 8,20 | 0,0 % |
| Garbsen | 2.651 | 2.792 | 5,3 % | 10,32 | 10,33 | 0,1 % |
| Euskirchen | 2.411 | 2.501 | 3,7 % | 10,80 | 10,80 | 0,0 % |
| Langenfeld (Rheinland) | 3.587 | 3.340 | -6,9 % | 11,08 | 12,37 | 11,6 % |
| Neubrandenburg | 2.009 | 2.009 | 0,0 % | 6,90 | 6,90 | 0,0 % |
| Hameln | 1.646 | 1.647 | 0,1 % | 8,54 | 8,54 | 0,0 % |
| Unna | 2.186 | 2.279 | 4,3 % | 8,97 | 8,98 | 0,1 % |
| Stolberg (Rhld.) | 2.091 | 2.175 | 4,0 % | 9,03 | 9,03 | 0,0 % |
| Eschweiler | 2.278 | 2.343 | 2,9 % | 9,25 | 9,25 | 0,0 % |
| Nordhorn | 2.270 | 2.302 | 1,4 % | 10,17 | 10,10 | -0,7 % |
| Baden-Baden | 3.777 | 3.737 | -1,1 % | 12,38 | 12,37 | -0,1 % |
| Meerbusch | 3.826 | 3.968 | 3,7 % | 13,88 | 13,88 | 0,0 % |
| Bad Homburg v. d. Höhe | 4.289 | 4.464 | 4,1 % | 15,41 | 15,26 | -1,0 % |
| Frankfurt (Oder) | 2.361 | 2.355 | -0,3 % | 8,06 | 7,66 | -5,0 % |
| Lingen (Ems) | 2.507 | 2.516 | 0,4 % | 10,82 | 10,79 | -0,3 % |
| Greifswald | 2.754 | 2.746 | -0,3 % | 11,19 | 11,18 | -0,1 % |
| Sankt Augustin | 2.702 | 2.828 | 4,7 % | 11,96 | 11,97 | 0,1 % |
| Pulheim | 3.499 | 3.571 | 2,1 % | 13,46 | 13,46 | 0,0 % |
| Stralsund | 2.613 | 2.613 | 0,0 % | 9,23 | 9,22 | -0,1 % |
| Wetzlar | 2.754 | 2.743 | -0,4 % | 10,18 | 10,18 | 0,0 % |
| Hilden | 3.343 | 3.404 | 1,8 % | 12,43 | 12,43 | 0,0 % |
| Schweinfurt | 2.495 | 2.494 | -0,0 % | 9,90 | 9,90 | 0,0 % |
| Bad Kreuznach | 2.801 | 2.799 | -0,1 % | 10,92 | 10,92 | 0,0 % |
| Langenhagen | 3.069 | 3.065 | -0,1 % | 11,16 | 11,20 | 0,4 % |
| Bad Salzuflen | 2.156 | 1.955 | -9,3 % | 9,33 | 9,34 | 0,1 % |
| Kleve | 2.413 | 2.521 | 4,5 % | 9,75 | 9,75 | 0,0 % |
| Hattingen | 2.316 | 2.367 | 2,2 % | 9,31 | 9,31 | 0,0 % |
| Neustadt an der Weinstraße | 2.814 | 2.632 | -6,5 % | 10,86 | 11,14 | 2,6 % |
| Wolfenbüttel | 2.031 | 2.031 | 0,0 % | 9,30 | 9,30 | 0,0 % |
| Ahlen | 2.050 | 2.079 | 1,4 % | 9,03 | 9,03 | 0,0 % |
| Menden (Sauerland) | 1.973 | 2.061 | 4,5 % | 7,83 | 7,82 | -0,1 % |
| Frechen | 3.668 | 3.666 | -0,1 % | 13,71 | 13,71 | 0,0 % |
| Ibbenbüren | 2.668 | 2.743 | 2,8 % | 10,20 | 10,20 | 0,0 % |
| Elmshorn | 2.797 | 2.686 | -4,0 % | 11,43 | 11,43 | 0,0 % |
| Gummersbach | 2.220 | 2.226 | 0,3 % | 9,39 | 9,40 | 0,1 % |
| Lahr | 2.929 | 2.884 | -1,5 % | 11,54 | 11,53 | -0,1 % |
| Peine | 1.835 | 1.833 | -0,1 % | 9,56 | 9,57 | 0,1 % |
| Bad Oeynhausen | 2.230 | 2.232 | 0,1 % | 9,33 | 9,31 | -0,2 % |
| Gronau (Westf.) | 2.612 | 2.612 | 0,0 % | 10,36 | 10,36 | 0,0 % |

## Kosten

Die Kosten sehe ich in dieser Sitzung nicht genau. Der Lauf bestand aus wenigen Skripten (Abruf, Prognose, Neuberechnung, Vergleich), ohne Einzelrecherche und ohne Hilfsagenten. Grob geschätzt einige Dollar.
