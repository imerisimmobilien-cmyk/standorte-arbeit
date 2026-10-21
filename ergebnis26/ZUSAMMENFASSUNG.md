# ergebnis26: Klumpenrisiko je Ort

## Vorgehen

- Bezugsgröße: sozialversicherungspflichtig Beschäftigte am Arbeitsort je Gemeinde, Bundesagentur für Arbeit, Stichtag 30.06.2025 (amtlich, alle Gemeinden).
- Arbeitgeberzahlen: (1) Primärquellen-Recherche für 40 Verdachtsfälle (Unternehmensseiten, Geschäftsberichte, Presse); (2) Wirtschaftsabschnitte der Wikipedia-Artikel aller 706 Städte ab 20.000 Einwohnern, Treffer von Hand geprüft (Konzern- und Weltzahlen, Kammern, historische Zahlen verworfen); (3) Feld arbeitgeber aus meinen eigenen Lieferungen (Orte mit einem Arbeitgeber ab 20 % der SvB am Arbeitsort).
- Anteil in Prozent nur bei Belegstufe belegt (Standortzahl ab 2022 aus Unternehmens- oder Pressequelle). Sonst Feld leer und "Anteil geschätzt, grob" als Spanne (70 bis 100 % des rechnerischen Werts, weil Beschäftigtenzahlen oft Leiharbeit, Partnerfirmen oder ältere Stände enthalten). Konzern- oder Regionszahlen ergeben keinen Anteil.
- Einstufung: hoch ab 25 %, mittel 10 bis 25 %, gering unter 10 % der SvB am Arbeitsort.
- Belegstufen: belegt (Standortzahl ab 2022, Primär- oder Pressequelle), plausibel (Standortzahl ohne Jahr oder älter, oder nur Wikipedia), unsicher (keine Standortzahl).

## Ergebnis

- 122 Orte mit Klumpenbefund, davon 87 in Bayern und Baden-Württemberg. Belegstufen: belegt 14, plausibel 98, unsicher 10.
- Klumpenrisiko hoch (66), unter anderem: Schwieberdingen, Rettenbach, Weissach, Manching, Adelberg, Roigheim, Hergensweiler, Alfdorf, Dingolfing, Bad Rodach, Rust, Michelau i.OFr., Siegelsbach, Gaggenau, Großwallstadt, Sindelfingen, Schaufling, Ettringen, Amstetten, Monheim, Reichenbach, Kirchheim i.Schw., Sontheim an der Brenz, Aldersbach, Röslau, Herrieden, Zell im Wiesental, Teublitz, Burghausen, Tacherting und weitere.
- 662 Städte ab 20.000 Einwohnern geprüft ohne erkennbares Klumpenrisiko (Liste `geprueft_ohne_klumpenrisiko`, mit Grundlage je Ort). Bei Städten über 100.000 SvB am Arbeitsort Belegstufe plausibel, sonst unsicher, weil dort nur Wikipedia und eigene Lieferungen geprüft wurden.

Datei: `patch-klumpenrisiko-01.json` mit `klumpen` (Felder: ags, id, name, svb_arbeitsort, arbeitgeber1, branche, beschaeftigte, beschaeftigte_jahr, anteil_svb_prozent oder anteil_schaetzung, arbeitgeber2, arbeitgeber3, quelle, belegstufe, einschaetzung) und `geprueft_ohne_klumpenrisiko`.

### Bayern und Baden-Württemberg

| Ort | größter Arbeitgeber | Beschäftigte | Jahr | SvB am Arbeitsort 2025 | Anteil | Belegstufe |
|---|---|---|---|---|---|---|
| Tschirn | Franz Schneider GmbH | 160 | Jahr im Artikel nicht genannt | 18 | grob 100 bis 100 % | unsicher |
| Freudenberg, Stadt | Rauch Möbelwerke | 1.300 | Jahr im Artikel nicht genannt | 1.161 | grob 78 bis 100 % | unsicher |
| Mulfingen | ebm-papst | 3.800 | undatiert (Freitag-Reportage) | 4.419 | nicht bezifferbar | unsicher |
| Schwieberdingen | Bosch (Entwicklungsstandort) | 6.500 | 2018 (veraltet) | 8.390 | grob 54 bis 78 % | plausibel |
| Rettenbach | Reflexa-Werke Albrecht GmbH | 280 | Jahr im Artikel nicht genannt | 378 | grob 52 bis 74 % | plausibel |
| Weissach | Porsche Entwicklungszentrum Weissach | 6.500 | aktuelle Standortseite (Jahr nicht ausgewiesen); 2021: 6.700 | 8.853 | grob 51 bis 73 % | plausibel |
| Manching, Markt | Airbus Defence and Space | 7.000 | 2026 (Stellenanzeige Mai 2026, nur ungefähr, keine offizielle Statistik) | 9.638 | grob 51 bis 73 % | plausibel |
| Adelberg | ERNI Electronics | 650 | Jahr im Artikel nicht genannt | 913 | grob 50 bis 71 % | plausibel |
| Roigheim | Pucaro Elektro-Isolierstoffe | 250 | Jahr im Artikel nicht genannt | 374 | grob 47 bis 67 % | plausibel |
| Hergensweiler | Rose Plastic AG | 400 | Jahr im Artikel nicht genannt | 643 | grob 44 bis 62 % | plausibel |
| Alfdorf | ZF Friedrichshafen AG | 1.800 | Jahr im Artikel nicht genannt | 2.931 | grob 43 bis 61 % | plausibel |
| Dingolfing, Stadt | BMW Group Werk Dingolfing | 18.000 | 2026 (Standortportrait PR 2604); 2024/2025 Pressetexte: ca. 18.500 | 29.385 | 61,3 % | belegt |
| Bad Rodach, Stadt | HABA Firmengruppe | 1.800 | 2023 | 3.013 | grob 42 bis 60 % | plausibel |
| Rust | Europa-Park | 3.600 | Jahr im Artikel nicht genannt | 6.153 | grob 41 bis 58 % | plausibel |
| Michelau i.OFr. | SMIA | 1.500 | 2025 | 2.610 | grob 40 bis 58 % | plausibel |
| Siegelsbach | Mann & Schröder GmbH | 700 | Jahr im Artikel nicht genannt | 1.225 | grob 40 bis 57 % | plausibel |
| Gaggenau, Stadt | Mercedes-Benz Werk Gaggenau | 6.500 | Jahr im Artikel nicht genannt | 11.430 | grob 40 bis 57 % | plausibel |
| Großwallstadt | Ciba Vision/Alcon | 2.200 | Jahr im Artikel nicht genannt | 4.001 | grob 38 bis 55 % | plausibel |
| Sindelfingen, Stadt | Mercedes-Benz Werk Sindelfingen | 30.500 | unklar (Stand der Werksseite nicht angegeben) | 55.900 | grob 38 bis 55 % | plausibel |
| Schaufling | Asklepios Klinik Schaufling | 300 | 2012 | 552 | grob 38 bis 54 % | plausibel |
| Ettringen | UPM Ettringen | 470 | Jahr im Artikel nicht genannt | 872 | grob 38 bis 54 % | plausibel |
| Amstetten | Heidelberger Druckmaschinen AG, Gießerei | 870 | Jahr im Artikel nicht genannt | 1.692 | grob 36 bis 51 % | plausibel |
| Monheim, Stadt | Hama | 1.500 | Jahr im Artikel nicht genannt | 3.014 | grob 35 bis 50 % | plausibel |
| Reichenbach | Barmherzige Brüder Reichenbach | 500 | Jahr im Artikel nicht genannt | 1.023 | grob 34 bis 49 % | plausibel |
| Kirchheim i.Schw., Markt | Wanzl Metallwarenfabrik GmbH, Werk Kirchheim | 600 | Jahr im Artikel nicht genannt | 1.239 | grob 34 bis 48 % | plausibel |
| Sontheim an der Brenz | Röhm GmbH | 870 | Jahr im Artikel nicht genannt | 1.817 | grob 34 bis 48 % | plausibel |
| Aldersbach | Knorr-Bremse AG, Werk Aldersbach | 1.000 | Jahr im Artikel nicht genannt | 2.116 | grob 33 bis 47 % | plausibel |
| Röslau | Scherdel GmbH, Niederlassung Röslau | 200 | Jahr im Artikel nicht genannt | 437 | grob 32 bis 46 % | plausibel |
| Herrieden, Stadt | Schüller | 2.300 | 2023 | 5.266 | grob 31 bis 44 % | plausibel |
| Zell im Wiesental, Stadt | Mahle GmbH | 530 | Jahr im Artikel nicht genannt | 1.229 | grob 30 bis 43 % | plausibel |
| Teublitz, Stadt | Läpple AG | 800 | Jahr im Artikel nicht genannt | 1.866 | grob 30 bis 43 % | plausibel |
| Burghausen, Stadt | Wacker Chemie | 8.000 | 2020 (Umweltbericht, 'über 8.000') | 19.226 | grob 29 bis 42 % | plausibel |
| Tacherting | Linde AG, Werk Schalchen | 800 | Jahr im Artikel nicht genannt | 1.925 | grob 29 bis 42 % | plausibel |
| Biessenhofen | Nestlé, Werk Biessenhofen | 670 | 2021 | 1.646 | grob 28 bis 41 % | plausibel |
| Kuppenheim, Stadt | Mercedes-Benz, Werk Kuppenheim | 950 | 2024 | 2.335 | grob 28 bis 41 % | plausibel |
| Leipheim, Stadt | Wanzl | 1.600 | Jahr im Artikel nicht genannt | 4.050 | grob 28 bis 40 % | plausibel |
| Ingolstadt | Audi AG | 40.000 | 2024 (Stand 31.12.2023 laut Audi-Faktenblatt) | 102.392 | 39,1 % | belegt |
| Neutraubling, Stadt | Krones AG | 6.600 | Jahr im Artikel nicht genannt | 17.004 | grob 27 bis 39 % | plausibel |
| Hirschaid, Markt | INA (Schaeffler-Gruppe) | 1.500 | Jahr im Artikel nicht genannt | 3.977 | grob 26 bis 38 % | plausibel |
| Unterföhring | Allianz SE | 10.000 | Jahr im Artikel nicht genannt | 26.641 | grob 26 bis 38 % | plausibel |
| Ehingen (Donau), Stadt | Liebherr-Werk Ehingen | 5.100 | undatiert (Liebherr-Standortseite) | 13.811 | grob 26 bis 37 % | plausibel |
| Amorbach, Stadt | Odenwald Faserplattenwerk | 470 | Jahr im Artikel nicht genannt | 1.274 | grob 26 bis 37 % | plausibel |
| Neuenstein, Stadt | Magna PT | 1.000 | Jahr im Artikel nicht genannt | 2.734 | grob 26 bis 37 % | plausibel |
| Ebensfeld, Markt | Bezirksklinikum Obermain | 700 | Jahr im Artikel nicht genannt | 1.928 | grob 25 bis 36 % | plausibel |
| Wemding, Stadt | Valeo | 1.200 | Jahr im Artikel nicht genannt | 3.309 | grob 25 bis 36 % | plausibel |
| Bad Wiessee | Medical Park AG | 600 | Jahr im Artikel nicht genannt | 1.667 | grob 25 bis 36 % | plausibel |
| Lohr a.Main, Stadt | Bosch Rexroth AG | 5.400 | 2017 | 15.768 | grob 24 bis 34 % | plausibel |
| Ochsenhausen, Stadt | Liebherr-Hausgeräte Ochsenhausen GmbH | 1.775 | Jahr im Artikel nicht genannt | 5.389 | grob 23 bis 33 % | plausibel |
| Ebersdorf b.Coburg | Mondi, Werk Ebersdorf | 800 | Jahr im Artikel nicht genannt | 2.460 | grob 23 bis 32 % | plausibel |
| Grassau, Markt | Katek | 600 | Jahr im Artikel nicht genannt | 1.903 | grob 22 bis 32 % | plausibel |
| Neckarsulm, Stadt | Audi AG | 13.370 | undatiert (Liste Region Heilbronn-Franken); Werk laut anderer Quelle 15.509, Jahr unbekannt | 42.958 | grob 22 bis 31 % | plausibel |
| Niederwinkling | Dichtungstechnik Wallstabe & Schneider | 700 | Jahr im Artikel nicht genannt | 2.296 | grob 21 bis 30 % | plausibel |
| Redwitz a.d.Rodach | Johnson Matthey | 450 | 2024 | 1.518 | grob 21 bis 30 % | plausibel |
| Vöhrenbach, Stadt | Walor Vöhrenbach GmbH | 240 | 2018 | 825 | grob 20 bis 29 % | plausibel |
| Mindelheim, Stadt | GROB-WERKE | 4.000 | undatiert (Firmenmeldung 'über 4.000'; Broschüre über 4.100; produktion.de 3.600) | 13.906 | grob 20 bis 29 % | plausibel |
| Runding | AZ Formenbau | 200 | Jahr im Artikel nicht genannt | 796 | grob 18 bis 25 % | plausibel |
| Kemnath, Stadt | Siemens Healthineers | 1.000 | Jahr im Artikel nicht genannt | 4.003 | grob 18 bis 25 % | plausibel |
| Markt Bibart, Markt | EGGER Spanplattenwerk Fuchsau | 170 | Jahr im Artikel nicht genannt | 684 | grob 17 bis 25 % | plausibel |
| Hallstadt, Stadt | Brose Fahrzeugteile | 1.240 | 2010 | 5.265 | grob 17 bis 24 % | plausibel |
| Asbach-Bäumenheim | AGCO Fendt, Werk 3 | 1.000 | Jahr im Artikel nicht genannt | 4.249 | grob 16 bis 24 % | plausibel |
| Gundelsheim, Stadt | Kwasny-Unternehmensgruppe (am Ort) | 300 | Jahr im Artikel nicht genannt | 1.295 | grob 16 bis 23 % | plausibel |
| Wehringen | Interquell GmbH | 200 | Jahr im Artikel nicht genannt | 865 | grob 16 bis 23 % | plausibel |
| Neunburg vorm Wald, Stadt | Fleischmann Elektrotech Engineering (F.EE) | 1.000 | Jahr im Artikel nicht genannt | 4.417 | grob 16 bis 23 % | plausibel |
| Altenstadt | Vincorion | 230 | Jahr im Artikel nicht genannt | 1.020 | grob 16 bis 22 % | plausibel |
| Buchenbach | Dold Holzwerke GmbH | 200 | Jahr im Artikel nicht genannt | 889 | grob 16 bis 22 % | plausibel |
| Erlangen | Siemens (gesamt, ohne Healthineers separat) | 21.500 | Ende September 2023 | 96.696 | 22,2 % | belegt |
| Walldürn, Stadt | Braun, Werk Walldürn (Abbau auf 750 angekündigt) | 1.000 | 2014 | 4.508 | grob 16 bis 22 % | plausibel |
| Biberach an der Riß, Stadt | Boehringer Ingelheim | 6.800 | undatiert (Stadt nennt ca. 6.500) | 31.174 | grob 15 bis 22 % | plausibel |
| Schwaigern, Stadt | iwis mechatronics GmbH | 700 | Jahr im Artikel nicht genannt | 3.239 | grob 15 bis 22 % | plausibel |
| Kirchberg i.Wald | Mesutronic Gerätebau GmbH | 220 | 2020 | 1.022 | grob 15 bis 22 % | plausibel |
| Niederlauer | Ganshorn Medizin Electronic | 200 | Jahr im Artikel nicht genannt | 930 | grob 15 bis 22 % | plausibel |
| Mühlheim an der Donau, Stadt | Karl Leibinger Medizintechnik | 335 | Jahr im Artikel nicht genannt | 1.597 | grob 15 bis 21 % | plausibel |
| Meeder | Hamuel Maschinenbau | 200 | Jahr im Artikel nicht genannt | 969 | grob 14 bis 21 % | plausibel |
| Köngen | DHL Paketzentrum | 700 | Jahr im Artikel nicht genannt | 3.402 | grob 14 bis 21 % | plausibel |
| Rastatt, Stadt | Mercedes-Benz Werk Rastatt | 6.000 | Dezember 2025 (mehr als 6.000) | 29.314 | 20,5 % | belegt |
| Kammlach | Mang-Käsewerk | 100 | Jahr im Artikel nicht genannt | 499 | grob 14 bis 20 % | plausibel |
| Forchheim, Stadt | Siemens Healthineers | 3.000 | Jahr im Artikel nicht genannt | 19.502 | grob 11 bis 15 % | plausibel |
| Schwäbisch Gmünd, Stadt | Bosch (Automotive Steering) | 3.600 | Herbst 2024 | 28.485 | 12,6 % | belegt |
| Neu-Ulm, Stadt | Daimler Buses, Werk Neu-Ulm | 3.650 | Jahr im Artikel nicht genannt | 29.940 | grob 9 bis 12 % | plausibel |
| Bamberg | Bosch, Werk Bamberg | 6.300 | 2022 | 57.747 | grob 8 bis 11 % | plausibel |
| Ellwangen (Jagst), Stadt | VARTA | 1.300 | Jahr im Artikel nicht genannt | 14.158 | grob 6 bis 9 % | plausibel |
| Wangen im Allgäu, Stadt | Waldner Firmengruppe | 1.000 | Jahr im Artikel nicht genannt | 13.155 | grob 5 bis 8 % | plausibel |
| Herzogenaurach, Stadt | nicht belegbar (adidas, Puma, Schaeffler als Hauptarbeitgeber genannt) |  | nicht belegbar | 24.669 | nicht bezifferbar | unsicher |
| Schweinfurt | nicht belegbar (ZF, Schaeffler, SKF, Bosch Rexroth genannt) |  | nicht belegbar | 54.018 | nicht bezifferbar | unsicher |
| Friedrichshafen, Stadt | nicht belegbar (ZF Friedrichshafen vermutet) |  | nicht belegbar | 39.471 | nicht bezifferbar | unsicher |
| Walldorf, Stadt | nicht belegbar (SAP vermutet) |  | nicht belegbar | 26.876 | nicht bezifferbar | unsicher |
| Regensburg | BMW Group Werk Regensburg |  | nicht belegbar | 134.109 | nicht bezifferbar | unsicher |

### übrige Länder

| Ort | größter Arbeitgeber | Beschäftigte | Jahr | SvB am Arbeitsort 2025 | Anteil | Belegstufe |
|---|---|---|---|---|---|---|
| Wörth am Rhein, Stadt | Daimler Truck Werk Wörth | 10.000 | undatiert (Rheinpfalz, 'rund 10.000'), Jahr vermutlich 2025/2026 | 15.393 | 65,0 % | belegt |
| Baunatal, Stadt | Volkswagen Werk Kassel | 15.500 | undatiert (Pressezahlen 15.500 bis 17.000 inkl. Zeitarbeit) | 25.190 | grob 43 bis 62 % | plausibel |
| Wolfsburg, Stadt | Volkswagen AG (Stammwerk) | 70.000 | 2024 (Stand 01.03.2024) | 114.571 | 61,1 % | belegt |
| Meyenburg, Stadt | Meyenburger Möbel Werk | 450 | Jahr im Artikel nicht genannt | 807 | grob 39 bis 56 % | plausibel |
| Salzgitter, Stadt | Salzgitter AG | 24.000 | undatiert (Jobportal), Anzeige nennt knapp 25.000 | 49.473 | nicht bezifferbar | unsicher |
| Kutenholz | RPC Verpackung Kutenholz | 300 | Jahr im Artikel nicht genannt | 784 | grob 27 bis 38 % | plausibel |
| Ludwigshafen am Rhein, Stadt | BASF SE (Stammwerk) | 39.000 | 2024 (Pressezahl Nov. 2024, sekundär) | 103.479 | 37,7 % | belegt |
| Dillingen/ Saar, Stadt | Dillinger Hütte | 5.296 | 31.12.2009 (veraltet) | 14.052 | grob 26 bis 38 % | plausibel |
| Marl, Stadt | Chemiepark Marl (Betreiber Evonik, alle Firmen im Park) | 10.000 | 2016 (Evonik Pressetexte), Standortbroschüre undatiert 'knapp 10.000' | 27.754 | grob 25 bis 36 % | plausibel |
| Dahlenburg, Flecken | Döhler Dahlenburg GmbH | 450 | Jahr im Artikel nicht genannt | 1.355 | grob 23 bis 33 % | plausibel |
| Rüsselsheim am Main, Stadt | Stellantis/Opel | 9.000 | Ende 2022 | 27.169 | grob 23 bis 33 % | plausibel |
| Ober-Ramstadt, Stadt | Deutsche Amphibolin-Werke (DAW), Standort Ober-Ramstadt | 1.400 | Jahr im Artikel nicht genannt | 4.610 | grob 21 bis 30 % | plausibel |
| Weilmünster, Marktflecken | Vitos Klinikum Weilmünster | 680 | Jahr im Artikel nicht genannt | 2.286 | grob 21 bis 30 % | plausibel |
| Tröbitz | TST Tröbitzer Systemtechnik | 70 | Jahr im Artikel nicht genannt | 283 | grob 17 bis 25 % | plausibel |
| Emden, Stadt | Volkswagen Werk Emden | 7.700 | 2026 (dpa, September 2026) | 31.328 | 24,6 % | belegt |
| Eisenhüttenstadt, Stadt | ArcelorMittal Eisenhüttenstadt | 2.600 | undatiert, vermutlich über 10 Jahre alt | 11.488 | grob 16 bis 23 % | plausibel |
| Uebigau-Wahrenbrück, Stadt | uesa GmbH | 350 | Jahr im Artikel nicht genannt | 1.548 | grob 16 bis 23 % | plausibel |
| Espenau | Waldhotel Schäferberg | 100 | Jahr im Artikel nicht genannt | 443 | grob 16 bis 23 % | plausibel |
| Sankt Augustin, Stadt | Bundespolizeidirektion Sankt Augustin | 3.500 | 2023 | 16.896 | grob 14 bis 21 % | plausibel |
| Ortrand, Stadt | PolymerTechnik Ortrand GmbH | 179 | 2023 | 884 | grob 14 bis 20 % | plausibel |
| Rheinberg, Stadt | Amazon Logistikzentrum | 1.500 | 2024 | 8.166 | grob 13 bis 18 % | plausibel |
| Gifhorn, Stadt | IAV GmbH | 3.500 | 2016 | 20.299 | grob 12 bis 17 % | plausibel |
| Wiehl, Stadt | BPW Bergische Achsen | 1.900 | Jahr im Artikel nicht genannt | 11.352 | grob 12 bis 17 % | plausibel |
| Riedstadt, Büchnerstadt | Philippshospital (Vitos) | 950 | Jahr im Artikel nicht genannt | 5.745 | grob 12 bis 16 % | plausibel |
| Zwickau, Hochschulstadt | Volkswagen Sachsen (Werk Zwickau-Mosel) | 8.000 | 2026 (Unternehmenspräsentation Feb. 2026, inkl. Azubis/Duale) | 50.688 | 15,8 % | belegt |
| Radebeul, Stadt | Koenig & Bauer, Werk Radebeul | 2.300 | Jahr im Artikel nicht genannt | 14.730 | grob 11 bis 16 % | plausibel |
| Northeim, Stadt | ContiTech Elastomer-Beschichtungen | 1.800 | Jahr im Artikel nicht genannt | 13.011 | grob 10 bis 14 % | plausibel |
| Saarlouis, Stadt | Ford-Werke Saarlouis | 2.700 | Oktober 2025 (2022: 4.600) | 23.828 | 11,3 % | belegt |
| Darmstadt, Wissenschaftsstadt | Merck KGaA | 12.500 | 2023 (Hauptsitz Darmstadt, Meldung März 2023) | 110.695 | 11,3 % | belegt |
| Emsdetten, Stadt | Tece | 1.500 | 2017 | 14.614 | grob 7 bis 10 % | plausibel |
| Attendorn, Hansestadt | Viega | 1.366 | Jahr im Artikel nicht genannt | 14.705 | grob 7 bis 9 % | plausibel |
| Schwedt/Oder, Stadt | PCK Raffinerie | 1.200 | zuletzt (Berliner Zeitung/dpa, Jahr nicht ausgewiesen, nach 2022) | 13.577 | 8,8 % | belegt |
| Eisenach, Stadt | Robert Bosch Fahrzeugelektrik Eisenach | 1.650 | Jahr im Artikel nicht genannt | 20.727 | grob 6 bis 8 % | plausibel |
| Leverkusen, Stadt | Bayer AG | 5.000 | 2025 | 66.292 | 7,5 % | belegt |
| Homburg, Stadt | Universitätsklinikum des Saarlandes |  | nicht belegbar | 29.816 | nicht bezifferbar | unsicher |

## Hinweise

- Nicht bezifferbar trotz Verdacht: Herzogenaurach (adidas, Puma, Schaeffler), Schweinfurt (ZF, Schaeffler, SKF), Friedrichshafen (ZF), Walldorf (SAP), Regensburg (BMW), Homburg (Uniklinik, Bosch), Salzgitter (nur Konzernzahl), Mulfingen (nur Regionszahl). Dort fehlt eine öffentliche Standortzahl.
- Laufende Abbau- oder Schließungsmeldungen (Ford Saarlouis, Audi Neckarsulm, VW Emden und Zwickau, BASF Ludwigshafen, Bosch Schwäbisch Gmünd, Schwieberdingen und Homburg) stehen im Feld hinweis.
- Kleine Orte aus eigenen Lieferungen beruhen meist auf Wikipedia-Zahlen ohne Jahr (plausibel). Ist die Zahl größer als die SvB am Arbeitsort, ist sie nicht ortsgenau (unsicher).
- Keine amtliche Zahl je Arbeitgeber vorhanden. Die Anteile sind Näherungen, keine Statistik.

## Kosten und Offenes

- Ungefährer Verbrauch: rund 5 US-Dollar (eine Primärquellen-Recherche über 40 Orte, Wikipedia-Abruf per Skript, Auswertung).
- Offen: Primärquellen für die rund 100 plausibel eingestuften Orte, Branchenanteile je Gemeinde (Industrie-Schwerpunkt) nicht erhoben, da je Gemeinde nicht frei verfügbar.
