# Zusammenfassung ergebnis14: zweiter unabhängiger Durchlauf Bayern und Hessen

Branch: `claude/laughing-sagan-q2wyfw`. Die Felder je Ort sind wie in ergebnis6 und ergebnis11. Dateien:
- Bayern: `zweitlauf-bayern-01.json` bis `zweitlauf-bayern-20.json`, 993 Orte
- Hessen: `zweitlauf-hessen-01.json` bis `zweitlauf-hessen-06.json`, 265 Orte
- `oelsnitz-vogtl.json`: Oelsnitz/Vogtl. (ags 14523300) mit Kauffällen aus dem Grundstücksmarktbericht Vogtlandkreis 2025

Die Ländernamen stehen im Dateinamen, damit sich die Nummern von Bayern und Hessen nicht überschneiden.

## Unabhängigkeit

- Neue Datenordner. Alle Portalseiten, die Ortsprüfung und die Prognosen sind neu abgerufen: 993 Gemeindeprofile des Bayerischen Landesamts und Wegweiser Kommune für Hessen. Werte aus ergebnis6, ergebnis11 und ergebnis12 sind weder gelesen noch übernommen. Grundlage sind nur die Gemeindeschlüssel-Listen der beiden Blöcke.
- Übernommen sind nur feste Verzeichnisse: der Ortsindex von miet-check, die immoportal-Sitemap, das Gemeindeverzeichnis, die amtlichen Listen zur Mietpreisbremse und die einmal geprüfte Arbeitgeberliste aus Wikipedia.

## Angewendete Regeln

- Alle Verbesserungen aus der Nacharbeit: miete-aktuell-Pfade mit Zusatz, homeday-Umleitung über die Ziel-URL geprüft, strenge Ortsprüfung bei gleichnamigen Orten, Gutachterwert erst ab zwei Portalwerten und nur bis 40 % Abweichung, ohne Prognose höchstens gelb.
- Korrigierte Ausreißerregel: Ausreißer nur unter den Portalwerten, ohne Gutachterwert, Kriterium "mehr als 50 % über der nächsten Portalquelle". Zu niedrige Werte: unter 60 % des Medians der übrigen Portalwerte. Ersatz nach gestrichenem Ausreißer: zuerst ohne-makler.net, dann Engel & Völkers.

## Ampel

- Bayern (993 Orte): grün 257, gelb 680, rot 40, unbewertet 16
- Hessen (265 Orte): grün 191, gelb 74, rot 0, unbewertet 0

## Wirkung der Korrektur der Ausreißerregel

Gleiche Abrufe, einmal mit der alten und einmal mit der korrigierten Regel gerechnet. Kauf, Miete oder Ampel ändern sich in Bayern bei 78 Orten, Ampelwechsel: rot zu gelb 4, grün zu gelb 23, gelb zu rot 2, gelb zu grün 4. In Hessen ändern sie sich bei 6 Orten, Ampelwechsel: gelb zu grün 1.

Hinweis zur Auslegung: Die meisten Wechsel von grün zu gelb in Bayern betreffen Orte mit genau zwei Portalwerten, die mehr als 50 % auseinanderliegen, meist homeday niedrig und miete-aktuell hoch, zum Beispiel Münsterhausen, Mickhausen, Burghaslach und Wiesenttal. Nach der korrigierten Regel fällt der höhere Wert heraus. Gibt es keine Ersatzquelle, bleibt ein Portalwert, der Gutachterwert zählt dann nicht, und die Ampel ist höchstens gelb. Nach der alten Regel hatte der Gutachterwert als dritter Vergleichswert den höheren Portalwert gehalten. Diese Fälle sollte die lokale Prüfung gezielt ansehen. Wenn bei zwei Portalwerten ohne Ersatz eine andere Auslegung gelten soll, rechne ich sie schnell neu.

