# Zusammenfassung ergebnis18: Berliner Umland, Ausbau

Branch: `claude/laughing-sagan-q2wyfw`. Format wie ergebnis6. Die beiden Teile stehen in getrennten Dateien.

Regeln wie ergebnis14 bis 16:
- Ausreißer werden nur unter den Portalwerten bestimmt.
- Es gilt die Zwei-Werte-Regel.
- Der Gutachterwert zählt erst ab zwei Portalwerten.
- Ohne Prognose ist die Ampel höchstens gelb.
- Strenge Ortsprüfung über PLZ und Landkreis.

Mietpreisbremse und Kappung: Brandenburgische Mietpreisbegrenzungsverordnung bzw. Kappungsgrenzenverordnung. Abgeglichen wird nur gegen die 36 Gemeinden der amtlichen Liste, über den Gemeindeschlüssel. Keine der 242 Gemeinden aus Teil 1 steht auf der Liste. Die Ortsteile von Potsdam liegen in einer gelisteten Gemeinde.

## Teil 1: 242 Brandenburger Gemeinden

Dateien:
- `lieferung-01.json` bis `lieferung-05.json`, je 50 Orte, die letzte mit 42.
- Reihenfolge: erst die 75 nahen Gemeinden, dann die 167 fernen, jeweils nach Einwohnern absteigend.
- Die nahen stehen in lieferung-01 und am Anfang von lieferung-02.

Abgrenzung:
- **NAH:** Die 76 genannten Schlüssel. Golzow (12069216, Potsdam-Mittelmark) steht schon in ergebnis9 und ist übersprungen, damit bleiben 75.
- **FERN:** Alle Gemeinden in Elbe-Elster, Oberspreewald-Lausitz, Ostprignitz-Ruppin, Prignitz, Spree-Neiße, Uckermark und Cottbus laut Destatis-Gemeindeverzeichnis, die in ergebnis1 bis ergebnis12 nicht vorkommen. Das sind 167, nicht 161. Wahrscheinlich stehen 6 davon lokal schon aus anderer Quelle in der Datenbank; bitte lokal aussortieren.
- **Namen:** Zweisprachige sorbische Namen sind auf den deutschen Namen gekürzt, zum Beispiel „Cottbus“ statt „Cottbus/Chóśebuz“. Echte Doppelnamen bleiben, zum Beispiel „Schwedt/Oder“, „Legde/Quitzöbel“.

| Bereich | Kreis | Orte | grün | gelb | rot | unbewertet |
|---|---|---|---|---|---|---|
| NAH | Barnim | 8 | 3 | 5 | 0 | 0 |
| NAH | Dahme-Spreewald | 15 | 2 | 10 | 3 | 0 |
| NAH | Havelland | 11 | 4 | 5 | 2 | 0 |
| NAH | Märkisch-Oderland | 17 | 1 | 14 | 2 | 0 |
| NAH | Oberhavel | 3 | 1 | 2 | 0 | 0 |
| NAH | Oder-Spree | 7 | 1 | 6 | 0 | 0 |
| NAH | Potsdam-Mittelmark | 12 | 4 | 3 | 3 | 2 |
| NAH | Teltow-Fläming | 2 | 0 | 1 | 1 | 0 |
| FERN | Elbe-Elster | 33 | 0 | 23 | 7 | 3 |
| FERN | Oberspreewald-Lausitz | 25 | 3 | 18 | 3 | 1 |
| FERN | Ostprignitz-Ruppin | 23 | 2 | 19 | 1 | 1 |
| FERN | Prignitz | 26 | 2 | 21 | 2 | 1 |
| FERN | Spree-Neiße | 29 | 3 | 17 | 9 | 0 |
| FERN | Uckermark | 30 | 2 | 23 | 3 | 2 |
| FERN | Cottbus | 1 | 0 | 1 | 0 | 0 |
| **Summe** | | **242** | **28** | **168** | **36** | **10** |

### Prognose

- LBV Brandenburg, Bevölkerungsvorausschätzung 2024 bis 2040, Tabellenanhang, Basis 2023.
- Für amtsangehörige Gemeinden ist nur der Amtswert veröffentlicht. Er ist als solcher gekennzeichnet: 195 Gemeinden mit Amtswert, 2 mit Wert der Mitverwaltung (Schwedt), 45 mit eigenem Gemeindewert.
- Bei 117 Orten greift der Prognose-Deckel, weil der Wert bei -8 % oder darunter liegt.

### Korrektur gegenüber ergebnis9

- Die Prognose für amtsangehörige Gemeinden war dort als „Gemeinde (amtsfrei)“ beschriftet, obwohl der Wert der Amtswert ist.
- Ursache war ein Fehler in der Prüfung: Das Textkennzeichen 64 steht für jede kreisangehörige Gemeinde, nicht für amtsfreie.
- Wert und Ampel waren richtig, nur die Beschriftung im Feld prognose.ebene war falsch. Sie betrifft rund 60 Orte in ergebnis9, zum Beispiel Bad Saarow (Amt Scharmützelsee), Rehfelde und Chorin.
- In ergebnis18 ist das korrigiert. Für ergebnis9 kann ich bei Bedarf eine Korrekturdatei nur für dieses Feld liefern.

### Orte ohne belastbare Werte (unbewertet, 10)

Mühlenfließ, Rabenstein/Fläming, Massen-Niederlausitz, Rückersdorf, Märkisch Linden, Hermsdorf, Fichtwald, Schönfeld, Lenzerwische und Mittenwalde (Uckermark). Das sind kleine Dörfer, für die die Portale zu Kauf oder Miete keinen ortsgenauen Wert haben. Die Werte sind leer gelassen, mit Grund im Feld offen; nichts ist aus Landkreis- oder Nachbarwerten eingesetzt.

Bei Mittenwalde (Uckermark) gehören die Portalseiten „mittenwalde“ zur Stadt Mittenwalde in Dahme-Spreewald und sind über die strenge Ortsprüfung entfernt.

### Dünne Datenbasis und Arbeitgeber

- 118 Orte haben bei Kauf oder Miete nur eine Quelle; die Ampel dort ist höchstens gelb.
- Arbeitgeber aus Wikipedia (Firma mit Beschäftigtenzahl am Ort) sind bei 10 Orten belegt, zum Beispiel Lübbenau, Senftenberg, Perleberg, Uebigau-Wahrenbrück und Meyenburg.
- Nicht übernommen ist die Ortrander Eisenhütte, die im Dezember 2024 insolvent wurde.

## Teil 2: Ortsteile mit eigener Portalseite (`teil2-ortsteile-01.json`)

14 Einträge:
- 13 Potsdamer Stadtteile: Am Stern, Berliner Vorstadt, Bornim, Bornstedt, Brandenburger Vorstadt, Drewitz, Eiche, Fahrland, Jägervorstadt, Kirchsteigfeld, Nauener Vorstadt, Potsdam West, Teltower Vorstadt.
- Döbbrick (Cottbus).

Felder je Eintrag:
- id: zum Beispiel potsdam-babelsberg.
- ags: die der Muttergemeinde.
- Koordinate: Schwerpunkt der OSM-Ortsteilgrenze.
- PLZ.
- Einwohner zum 31.12.2025, Quelle Stadt Potsdam bzw. Stadt Cottbus. Döbbrick zählt die Stadt gemeinsam mit Maiberg.

| Ampel | Anzahl | Ortsteile |
|---|---|---|
| gelb | 4 | Am Stern, Fahrland, Jägervorstadt, Kirchsteigfeld |
| rot | 8 | Faktor über 30 |
| unbewertet | 2 | Drewitz und Döbbrick: keine ortsgenaue Miete |

Alle Einträge haben nur eine gewertete Kaufquelle (immoportal), die Datenbasis ist also dünn.

### Nicht angelegt

- **homeday:** Die Ortsteilseiten zeigen in Potsdam durchweg den Stadtwert von 5.050 €/m². Sie sind deshalb nicht ortsgenau und nicht gewertet.
- **immoportal mit Doppelwerten:** Babelsberg Nord und Süd haben je 5.017 €/m², was auch dem Stadtwert entspricht. Waldstadt I und II haben je 3.957 €/m². Ohne ortsgenauen Wert sind diese Ortsteile nicht einzeln angelegt.
- **Ohne eigene immoportal-Seite:** Golm, Groß Glienicke, Marquardt, Zentrum Ost und weitere. Dort gibt es nur homeday mit Stadtwert, deshalb nicht angelegt.
- **Übriges Umland:** Geprüft sind Oranienburg, Bernau, Falkensee, Königs Wusterhausen, Eberswalde, Teltow, Blankenfelde-Mahlow, Hennigsdorf, Ludwigsfelde, Fürstenwalde, Strausberg, Hohen Neuendorf, Kleinmachnow, Werder, Neuenhagen, Brandenburg an der Havel, Frankfurt (Oder), Cottbus, Panketal und Wandlitz.
  - Eigene Ortsteilseiten haben nur Blankenfelde und Mahlow, Glindow (Werder), Döbbrick (Cottbus) und Zepernick (Panketal).
  - Bis auf Döbbrick gleichen ihre Werte dem Wert der Gemeinde, deshalb sind sie nicht angelegt.
