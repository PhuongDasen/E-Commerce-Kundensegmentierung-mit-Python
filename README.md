<p align="center">
  <img " width="100%">
</p>
<h1> 📊 E-Commerce Kundensegmentierung</h1>
Author: Phuong Dasen<br>
Tool: Python<br>

## 📑 Inhaltsverzeichnis

- [📌 Hintergrund & Überblick](#hintergrund--überblick)  
- [📁 Datensatzbeschreibung & Datenstruktur](#datensatzbeschreibung--datenstruktur)  
- [🧠 Design-Thinking-Prozess](#design-thinking-prozess)  
- [📊 Zentrale Erkenntnisse & Visualisierungen](#zentrale-erkenntnisse--visualisierungen)  
- [🔍 Abschließende Schlussfolgerung & Empfehlungen](#abschließende-schlussfolgerung--empfehlungen)  

---
## 📌 Hintergrund und Überblick 
<p><u><strong>1. Über RFM-Analyse</strong></u></p>
   <p><strong>Warum RFM?</strong><br>
    - RFM ist eine Marketinganalysetechnik, die für Recency (Aktualität), Frequency (Häufigkeit) und Monetary Value (Geldwert) steht.<br>
        - <strong>Aktualität</strong>: wie oft ein Kunde in letzter Zeit eingekauft hat.<br>
        - <strong>Häufigkeit</strong>: wie oft ein Kunde eingekauft hat.<br>
        - <strong>Monetärer Wert</strong>: den Gesamtbetrag, den ein Kunde für seine Einkäufe ausgegeben hat.<br>
    - RFM wird verwendet, um Kunden auf der Grundlage ihres Kaufverhaltens zu identifizieren und zu kategorisieren, d. h. wie häufig und kürzlich sie eingekauft haben und wie hoch der Geldwert dieser Einkäufe ist.<br>
     
<strong>Wie?</strong><br>
Bei der RFM-Analyse werden die Kunden anhand von drei Faktoren bewertet (Aktualität, Häufigkeit - wie oft, Geldwert - wie viel) und dann auf der Grundlage der Kombination der RFM-Werte eingestuft<br>

**Referenz**
- https://www.putler.com/rfm-analysis

### Ziel:
## 📖 Was ist dieses Projekt?
- Dieses Projekt analysiert Kundenverhalten im E-Commerce mithilfe von RFM-Segmentierung und Churn-Prediction.
- Ziel ist es, datengestützte Maßnahmen zur Kundenbindung und Umsatzsteigerung zu entwickeln.

## 👤 Für wen ist dieses Projekt?
- Das Projekt richtet sich an das Marketing- und CRM-Team eines E-Commerce-Unternehmens.
- Es unterstützt Entscheidungsträger dabei, Kundensegmente besser zu verstehen und gezielte Kampagnen durchzuführen.

## ❓ Geschäftsfrage von dem Projekt?
- Welche Kundengruppen sind besonders wertvoll oder gefährdet, zur Konkurrenz abzuwandern?
- Wie können Unternehmen datenbasiert reagieren, um Kunden zu halten oder zurückzugewinnen?

### 📁 Datensatzbeschreibung & Datenstruktur
📌 Datenquelle<br>
Quelle: Bereitgestellter Datensatz für die Analyse des E-Commerce-Einzelhandels<br>
Umfang: 541.910 Zeilen × 8 Spalten (Tabelle 1: E-Commerce Retail), zusätzliche Segmentierungsdetails in Tabelle 2<br>
Format: .xlsx (Excel-Datei mit zwei Tabellenblättern)<br>

📊 Datenstruktur & Beziehungen
#### 1️⃣ Verwendete Tabellen:
Der Datensatz besteht aus zwei Tabellen:<br>

<strong>Tabelle 1: Ecommerce Retail</strong><br>
Diese Tabelle enthält Transaktionsdaten eines britischen Onlinehändlers im Zeitraum von Dezember 2010 bis Dezember 2011. Sie eignet sich besonders gut zur Analyse des Kaufverhaltens und der Kundensegmentierung, da viele Kunden Großhändler sind.<br>

<strong>Tabelle 2: Segmentation</strong><br>
Diese Tabelle enthält RFM-Scores zur Klassifizierung von Kunden in Segmente. Jeder Score wird einem Kundenprofil wie „Loyaler Kunde“ oder „Gefährdeter Kunde“ zugeordnet.<br>

#### 2️⃣ Tabellenschema & Datenvorschau
<details>
<summary>🔽 Tabelle 1: Tabellenbeschreibung anzeigen</summary>

<br>

| **Spaltenname** | **Datentyp**     | **Beschreibung**                                                                 |
|------------------|------------------|----------------------------------------------------------------------------------|
| InvoiceNo        | object           | Eindeutige Rechnungsnummer für jede Transaktion (6-stellig). Beginnt sie mit „C“, handelt es sich um eine Stornierung. |
| StockCode        | object           | Eindeutiger Produktcode (5-stellig).                                             |
| Description      | object           | Produktname.                                                                     |
| Quantity         | int64            | Anzahl der gekauften Einheiten pro Transaktion.                                  |
| InvoiceDate      | datetime64[ns]   | Datum und Uhrzeit der Transaktion.                                               |
| UnitPrice        | float64          | Preis pro Produkteinheit in britischen Pfund.                                    |
| CustomerID       | float64          | Eindeutige 5-stellige Kennung für jeden Kunden.                                  |
| Country          | object           | Name des Landes, in dem der Kunde wohnt.                                         |

</details>

<details>
<summary>🔽 Tabelle 2: RFM-Segmentierung anzeigen</summary>

<br>

| **Segment**              | **RFM Scores**                                                                                                                                                    |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Champions                | 555, 554, 544, 545, 454, 455, 445                                                                                                                                    |
| Loyale Kunden            | 543, 444, 435, 355, 354, 345, 344, 335                                                                                                                              |
| Potenzielle Loyale       | 553, 551, 552, 541, 542, 533, 532, 531, 452, 451, 442, 441, 431, 453, 433, 432, 423, 353, 352, 351, 342, 341, 333, 323                                                 |
| Neue Kunden              | 512, 511, 422, 421, 412, 411, 311                                                                                                                                   |
| Vielversprechend         | 525, 524, 523, 522, 521, 515, 514, 513, 425, 424, 413, 414, 415, 315, 314, 313                                                                                      |
| Braucht Aufmerksamkeit   | 535, 534, 443, 434, 343, 334, 325, 324                                                                                                                              |
| Einschlafend             | 331, 321, 312, 221, 213, 231, 241, 251                                                                                                                              |
| Gefährdet                | 255, 254, 245, 244, 253, 252, 243, 242, 235, 234, 225, 224, 153, 152, 145, 143, 142, 135, 134, 133, 125, 124                                                          |
| Nicht verlieren!         | 155, 154, 144, 214, 215, 115, 114, 113                                                                                                                              |
| Winterschlafend          | 332, 322, 233, 232, 223, 222, 132, 123, 122, 212, 211                                                                                                                |
| Verlorene Kunden         | 111, 112, 121, 131, 141, 151                                                                                                                                         |

</details>

## ⚒️ Hauptprozess
# 📌 Bibliotheken importieren
<img width="700" alt="Screenshot 2025-07-01 at 9 04 11 AM" src="https://github.com/user-attachments/assets/eff40e30-91c4-48ff-91a5-0a8303acadb7" />
<img width="700" alt="Screenshot 2025-07-01 at 9 16 29 AM" src="https://github.com/user-attachments/assets/0aa3014d-6080-457b-b787-a95169d5d593" />
<img width="700" alt="Screenshot 2025-07-01 at 9 15 13 AM" src="https://github.com/user-attachments/assets/902a0c25-414a-4fb0-b113-04f3c3db0b2b" />
<img width="700" alt="Screenshot 2025-07-01 at 9 15 23 AM" src="https://github.com/user-attachments/assets/1ce2522d-662c-4c34-a172-f755421e32f9" />

# 📌 Explorative Datenanalyse (EDA) <br> 
<img width="700" alt="Screenshot 2025-07-01 at 9 17 08 AM" src="https://github.com/user-attachments/assets/5119454c-5231-40a6-899d-af6b81bc56ad" /><br>

🎯 **Ergebnisanalyse:**  
	1. Die Daten haben 541.909 Zeilen und 8 Spalten<br>
	2. Die Spalte CustomerID: fehlen rund 135.000 Einträge (541.909 - 406.829) --> entfernen <br>
	3. Die Spalte Description: fehlen etwa 1.454 Beschreibungen --> kann halten, weil sie nicht auf RFM beeinflusst.<br>
	4. Die Datentypen sind größtenteils korrekt zugeordnet, z. B. InvoiceDate als datetime64, Quantity als int64, und UnitPrice als float64.<br>
 	5. Inkorrekte Werte: <br>
      * Bestandscode: 54487 Zeilen -> Zeilen mit fehlerhaften Daten löschen, da die anderen Codes Geschenke sein können, wenn der Produktcode nicht aus fünf Ganzzahlen besteht.<br>
      * Menge: 10587 Zeilen -> Zeilen mit fehlerhaften Daten löschen, da dies das RFM-Modell beeinflusst (Menge darf nicht <= 0 sein).<br>
      * Einzelpreis: 2512 Zeilen -> Zeilen mit fehlerhaften Daten löschen, da dies das RFM-Modell beeinflusst (Preis darf nicht <= 0 sein).<br>
      * Bestellungen mit Rechnungsnummern, die mit „C“ beginnen, entfernen.<br>
<img width="700" alt="Screenshot 2025-07-01 at 9 57 26 AM" src="https://github.com/user-attachments/assets/59b5812f-7226-4d04-b8cd-39c0d9aae183" />
<img width="700" alt="Screenshot 2025-07-01 at 9 57 40 AM" src="https://github.com/user-attachments/assets/466ac77d-6747-413b-b105-087b493d976e" />
<img width="700" alt="Screenshot 2025-07-01 at 9 57 52 AM" src="https://github.com/user-attachments/assets/c23d772f-d253-4b75-a06a-b9cea020f87d" />

# 📌 RFM <br> 
<img width="700" alt="Screenshot 2025-07-01 at 9 58 03 AM" src="https://github.com/user-attachments/assets/c0f308fc-140b-4961-ae98-636da60b6628" />
<img width="700" alt="Screenshot 2025-07-01 at 10 01 21 AM" src="https://github.com/user-attachments/assets/6ed79069-f06f-4421-9be0-bc6cf00c1797" />
<img width="700" alt="Screenshot 2025-07-01 at 10 01 29 AM" src="https://github.com/user-attachments/assets/ca372425-9f27-47d5-a3ec-51fdbc0a505e" />
<img width="700" alt="Screenshot 2025-07-01 at 10 06 15 AM" src="https://github.com/user-attachments/assets/d0fcab37-7958-4ff8-a44b-a954e7683f34" />
<img width="700" alt="Screenshot 2025-07-01 at 10 06 20 AM" src="https://github.com/user-attachments/assets/d143e8e8-bec4-47f9-9fde-59101fbc3e06" />
<img width="700" alt="Screenshot 2025-07-01 at 10 06 30 AM" src="https://github.com/user-attachments/assets/87a61e4a-3afa-4532-ac2a-bc975b9b4fe7" />
<img width="700" alt="Screenshot 2025-07-01 at 10 06 37 AM" src="https://github.com/user-attachments/assets/be5fd83f-4460-4905-bd0e-3aecf3b7a52e" />
<img width="599" alt="Screenshot 2025-07-01 at 10 14 15 AM" src="https://github.com/user-attachments/assets/e0f50a6d-451d-41f9-9330-1a61803471bc" />
<img width="354" alt="Screenshot 2025-07-01 at 10 14 26 AM" src="https://github.com/user-attachments/assets/6f43f1c6-eae8-43e4-9684-dffe65505538" /><br>

🎯 **Ergebnisanalyse:**
Die aktuelle Segmentstruktur zeigt, dass nur <strong>~1 von 10 Kunden</strong> hochprofitabel ist, während fast die Hälfte gefährdet ist, komplett verloren zu gehen. Ziel sollte sein, die „Potenzial“-Gruppe zu aktivieren und die „Risiko“-Gruppe zu analysieren oder selektiv zu bearbeiten.









🎯 **Ergebnisanalyse:**  

## 3. 



🎯 **Ergebnisanalyse:**  


## 4.


🎯 **Ergebnisanalyse:**  

## 5. 


🎯 **Ergebnisanalyse:**  


## 📊 Zentrale Erkenntnisse & Visualisierungen 

### 🔍 Dashboard Vorschau  
<img width="3500" />

📊 Haupterkenntnisse  


## 🔎 Abschließende Schlussfolgerung & Empfehlungen 

📌 Zentrale Erkenntnisse:

✔️ 

✔️ 

✔️ 









# [PYTHON] RFM-Analysis 
<h2>I. Einleitung</h2>
 

**2. Geschäftliche Fragen**<br>
        <u>**Kontext**</u>
  - SuperStore Company ist ein globales Einzelhandelsunternehmen. Das Unternehmen hat also viele Kunden. Anlässlich von Weihnachten und Neujahr möchte die Marketingabteilung Marketingkampagnen durchführen, um den Kunden zu danken, die das Unternehmen in der vergangenen Zeit unterstützt haben. Und Sie gewinnen Kunden, die das Potenzial haben, zu Stammkunden zu werden.
  - Die Marketingabteilung muss die Segmente der einzelnen Kunden klassifizieren, um für jede Kundengruppe das passende Marketingprogramm zu entwickeln.
  - Der Marketing-Direktor schlug außerdem vor, das RFM-Modell in Python zu verwenden, um die Kunden zu segmentieren und dann Marketingkampagnen zu starten, um den Kunden für ihre Unterstützung des Unternehmens in der Vergangenheit zu danken. Außerdem sollten potenzielle Kunden dazu gebracht werden, treue Kunden zu werden.
  - Welcher der drei Indikatoren R, F und M sollte für das Marketing- und Vertriebsteam im Rahmen des Einzelhandelsmodells des Unternehmens am interessantesten sein?

<h2>II.Datenvisualisierung mit Python</h2>
  - **Seaborn Countplot der Häufigkeit**<br>
    ![image](https://github.com/user-attachments/assets/5673c76a-8673-4ade-bf32-ad5ef6ed3057)
 - **Baumstruktur der Kundensegmentierung**<br>
    ![image](https://github.com/user-attachments/assets/aa185721-0cd0-41c8-8e63-84d0df14c428)
 - **Seaborn Counplot der Kundensegmentierung**<br>
    ![image](https://github.com/user-attachments/assets/a73d36c6-1803-43bb-bb60-bad5d0cc4837)
 - **Kreisdiagramm des Kanals**<br>
     ![image](https://github.com/user-attachments/assets/9ec0ec49-154b-4558-a145-230b820dc6d9)
 - **Kreisdiagramm des Schiffsmodus**<br>
  ![image](https://github.com/user-attachments/assets/42b54d26-42b6-4bbb-ba4c-85a312da0f9e)
 - **Kreisdiagramm der Kategorie**<br>
 ![image](https://github.com/user-attachments/assets/32748b8e-c870-4122-aaef-4186a28e1394)
 - **Kreisdiagramm der Sub-Kategorie**<br>
 ![image](https://github.com/user-attachments/assets/b05781ef-8f8d-4dea-a2df-ed84cb437a87)
- **Balkendiagramm: Gesamtumsatz nach Segmentierung**<br>
![image](https://github.com/user-attachments/assets/60caae7e-6083-40df-a003-90f4a9561c5f)
- **Balkendiagramm: Gesamtgewinn nach Segmentierung**<br>
![image](https://github.com/user-attachments/assets/773bd944-2c29-439b-9ef0-8d427c0f7e6d)
- **Balkendiagramm: Gesamtumsazt nach Region**<br>
![image](https://github.com/user-attachments/assets/cb2e5436-9716-423a-a8b4-20a3e7cb06f2)
- **Treemap des Staates nach Aufträgen**<br>
![image](https://github.com/user-attachments/assets/0639ac22-470b-47fa-a39c-0c41a588fdb6)

<h2>III.Insights</h2>
1. Der wichtigste Index der drei Indikatoren, auf die SuperStore achten sollte, ist F, gefolgt von R: Der Anteil der Kunden, die ein- und zweimalkaufen, ist sehr hoch. Nur sehr wenige Kunden tätigen langfristige Käufe, z.B: 8-9 Mal oder öfter. Das zeigt, dass die Kundenbindungsrate des Unternehmens weiterhin niedrig ist.
2. Zur Kundensegmentierung: Das Unternehmen besteht hauptsächlich aus "Neukunden" > "Kunden im Ruhestand" > "Verlorene Kunden". Das zeigt erneut, dass wir dem Index F Aufmerksamkeit schenken sollte.
3. Umsatzt und Gewinn aus "Neukunden" sind am höchsten.
4. Der Umsatz in der Region Ost ist im Vergleich zu den anderen drei Regionen am niedrigsten.
5. Kalifornien, Texas, Illinois und Floria sind die Bundesstaaten mit den meisten Bestellungen.
6. Die Hauptkunden des Unternehmens sind Privatkunden (52%), Unternehmen (30%) und schliesslich Homeoffice-Kunden.
7. Die bestellstärksten Kategorien sind "Bürobedarf" (bis zu 60%), gefolgt von "Möbeln".
8. Die wichtigsten Unterkategorien sind: Papier (14%), Ordner(15%), Kunst (9%), Telefone und Aufbewahrung (8 %).

<h2>IV. Vorschläge</h2>
Das Unternehmen benötigt Richtlinie für: <br>
**Neukundenbindung:**<br>
Senden Sie Neukunden, die kürzlich einen Einkauf getätigt haben, eine personalisierte Willkommens-E-Mail oder ein Angebot, in dem Sie sich für ihren Einkauf bedanken und sie zur Rückkehr animieren.



 





