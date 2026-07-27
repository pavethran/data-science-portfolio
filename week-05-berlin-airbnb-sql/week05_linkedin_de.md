# Week 5 — LinkedIn Post (German)

**Post on:** Sunday ~10 AM CET, or Tuesday 8:30 AM
**Attach:** `chart_availability.png` (the "availability paradox" chart - most scroll-stopping)
**Links go in the FIRST COMMENT, not the post body.**

---

## Post body (German)

Was 12.855 Berliner Airbnbs über den Markt verraten - drei Erkenntnisse mit reinem SQL 👇

Ich habe die Berlin-Daten von Inside Airbnb (Stand August 2025) analysiert. 12 Bezirke, 138 Kieze, ~13.000 Inserate. Mit 10 SQL-Abfragen - von einfachem GROUP BY bis zu Window Functions und CTEs - kommen drei Ergebnisse raus, die man beim Blick auf die Startseite von Airbnb nicht sieht:

1) Nur 54 % der Inserate stammen von "echten" Einzel-Hosts.

Der Rest sind Mehrfach-Anbieter: 22 % Nebengewerbe (2-5 Wohnungen), 13 % kommerziell (6-20), 11 % Groß-Betreiber mit über 20 Inseraten. Blueground allein hat 261 Wohnungen. Das Bild vom "Berliner, der sein Gästezimmer vermietet" gilt kaum noch für die Hälfte des Marktes.

2) Das Verfügbarkeits-Paradox: Teure Inserate stehen leer.

Ausgebuchte Wohnungen (0 Tage verfügbar): 103 € pro Nacht im Schnitt.
Immer verfügbare Wohnungen (301-365 Tage): 169 € pro Nacht - 64 % teurer.
Und das sind keine Randfälle: 23,5 % aller Inserate hängen ganzjährig leer. Entweder Überpreisung oder gewerbliche Anbieter, die Preise unabhängig von Nachfrage setzen.

3) Zwei Bezirke dominieren alles.

Mitte + Friedrichshain-Kreuzberg = 43 % des Gesamtmarktes (5.523 Inserate). Mit Pankow dazu sind es 58 % in nur 3 von 12 Bezirken. Reinickendorf, Spandau und Marzahn-Hellersdorf zusammen: unter 4 %.

Das war Woche 5 meines wöchentlichen Data-Science-Portfolios - diesmal mit Fokus auf SQL. Von einfachen Aggregaten bis zu RANK() OVER (PARTITION BY ...). Alles reproduzierbar mit dem Notebook auf GitHub.

🛠 Tools: SQL (SQLite), Python, pandas, matplotlib
📊 Datenquelle: Inside Airbnb Berlin (öffentlich)

Welches Ergebnis überrascht euch am meisten - der kommerzielle Anteil oder das Verfügbarkeits-Paradox?

#DataScience #SQL #Datenanalyse #BerlinJobs #DataStorytelling #InsideAirbnb #OpenToWork #LearningInPublic

---

## First comment (post immediately after)

Notebook + SQL-Queries: https://github.com/pavethran/data-science-portfolio/tree/main/week-05-berlin-airbnb-sql | Portfolio-Übersicht: https://github.com/pavethran/data-science-portfolio | Daten: Inside Airbnb Berlin (insideairbnb.com/berlin) | Offen für Data-Analyst- und Data-Scientist-Stellen in Berlin & DACH: pavethranmuthukumaran@gmail.com

---

## Numbers reference

- 12.855 Inserate · 8.182 einzigartige Hosts · 138 Kieze in 12 Bezirken
- Median-Preis: 131 € · Durchschnitt: 161 € (Ausreißer bis 10.025 €)
- Zimmertypen: Entire home 6.138 (Ø 181 €), Private room 2.209 (Ø 105 €), Hotel 84 (Ø 194 €), Shared 84 (Ø 57 €)
- Bezirks-Anteil: Mitte 22,3 % · F-Kreuzberg 20,7 % · Pankow 15,2 % · Charlottenburg 11,3 % · Neukölln 10,2 %
- Median-Preis top: Pankow 153 € · Mitte 152 € · F-Kreuzberg 139 € | bottom: Reinickendorf 83 € · Marzahn 98 €
- Host-Verteilung: 1 Wohnung 53,6 % · 2-5 Wohnungen 22,0 % · 6-20 Wohnungen 13,3 % · 20+ Wohnungen 10,5 %
- Top-Betreiber: Blueground (261 Inserate) · Tenitt (199) · Limehome (103) · Vonder (96)
- Aufschlag Ganzhaus vs. Privatzimmer: Spandau +238 % · Steglitz +167 % · Mitte nur +37 %
- Verfügbarkeit: 27,2 % ausgebucht · 12,1 % 1-60 Tage · 17,5 % 61-180 · 19,7 % 181-300 · 23,5 % immer verfügbar
