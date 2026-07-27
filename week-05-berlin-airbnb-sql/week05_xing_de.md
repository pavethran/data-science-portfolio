# Week 5 — Xing Post (German)

**Post on:** Same day as LinkedIn
**Attach:** `chart_availability.png`
**Tone:** Business-formal, more analytical than LinkedIn (Xing DACH audience).

---

## Post body (German)

Berliner Airbnb-Markt in Zahlen - drei Erkenntnisse aus reiner SQL-Analyse.

Ich habe die aktuelle Berlin-Datenbasis von Inside Airbnb (12.855 Inserate, 12 Bezirke, 138 Kieze) mit zehn progressiven SQL-Abfragen ausgewertet - von einfachen Aggregaten bis Window Functions und CTEs. Die Ergebnisse:

▶ Der Markt ist zu 46 % gewerblich.
Nur 53,6 % der Inserate stammen von Einzelhost-Anbietern. 11 % kommen von Betreibern mit mehr als 20 Inseraten - Blueground allein verwaltet 261 Wohnungen. Der Anteil professioneller Betreiber ist deutlich höher, als das Image der Plattform suggeriert.

▶ Verfügbarkeits-Paradox: Höhere Preise korrelieren mit geringerer Nachfrage.
Ausgebuchte Wohnungen: 103 € Ø Preis. Ganzjährig verfügbare Wohnungen: 169 € Ø Preis - ein Aufschlag von 64 %. 23,5 % aller Inserate stehen faktisch leer. Entweder Überpreisung oder gewerbliche Holding-Strategie.

▶ Massive Marktkonzentration in wenigen Bezirken.
Mitte und Friedrichshain-Kreuzberg vereinen 43 % des Gesamtmarktes. Mit Pankow steigt der Anteil auf 58 % in nur drei von zwölf Bezirken. Reinickendorf, Spandau und Marzahn-Hellersdorf zusammen: unter 4 %.

Das komplette Notebook mit allen SQL-Queries (WITH-CTEs, RANK() OVER, self-JOIN, GROUP BY + HAVING) und Visualisierungen ist reproduzierbar mit dem Code auf GitHub.

Woche 5 meines wöchentlichen Data-Science-Portfolios - Fokus SQL.

Tools: SQL (SQLite), Python, pandas, matplotlib
Datenquelle: Inside Airbnb Berlin (August 2025)

GitHub-Repo: https://github.com/pavethran/data-science-portfolio/tree/main/week-05-berlin-airbnb-sql

Ich bin aktuell offen für Data-Analyst- und Data-Scientist-Positionen in Berlin und der DACH-Region.

#DataScience #SQL #Datenanalyse #BusinessIntelligence #BerlinJobs #InsideAirbnb
