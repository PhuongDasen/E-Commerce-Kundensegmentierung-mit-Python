<p align="center">
  <img src="https://github.com/user-attachments/assets/b1af0f79-3874-4552-a1de-af99968c8460" width="90%">
</p>
<h1> 📊 E-Commerce Kundensegmentierung mit Python</h1>
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
### Ziel:
## 📖 Was ist dieses Projekt?
- Das Marketingteam möchte während der Weihnachtszeit personalisierte Kampagnen zur Kundenbindung und -gewinnung starten. Aufgrund des großen Datensatzes ist eine manuelle Segmentierung jedoch nicht mehr möglich.<br>
- Um dieses Problem zu lösen, wird das RFM-Modell mit Python (Colab) angewendet, um Kunden basierend auf ihrem Kaufverhalten in verschiedene Segmente einzuteilen.<br>
- Dieses Projekt umfasst Datenaufbereitung, RFM-Score-Berechnung, Segmentierung, Visualisierung und die Bereitstellung umsetzbarer Empfehlungen für die Marketing- und Vertriebsteams zur Optimierung ihrer Strategien.<br>
## 👤 Für wen ist dieses Projekt?
- Das Projekt richtet sich an das Marketing- und CRM-Team eines E-Commerce-Unternehmens.<br>
- Es unterstützt Entscheidungsträger dabei, Kundensegmente besser zu verstehen und gezielte Kampagnen durchzuführen.<br>
## ❓ Geschäftsfrage von dem Projekt?
✔️ Wie können wir Kunden mithilfe des RFM-Modells effektiv segmentieren?<br>
✔️ Welche Kundengruppen sollten bei Kundenbindungs- und Werbekampagnen priorisiert werden?<br>
✔️ Welche umsetzbaren Erkenntnisse können zur Verbesserung von Marketingstrategien und Kundenbindung beitragen?<br>
✔️ Welche Strategien sollten für verschiedene Kundensegmente angewendet werden, um den Wert zu maximieren?<br>

<p><u><strong>1. Über RFM-Analyse</strong></u></p>
   <p><strong>Warum RFM?</strong><br>
    - RFM ist eine Marketinganalysetechnik, die für Recency (Aktualität), Frequency (Häufigkeit) und Monetary Value (Geldwert) steht.<br>
        - <strong>Aktualität</strong>: wie oft ein Kunde in letzter Zeit eingekauft hat.<br>
        - <strong>Häufigkeit</strong>: wie oft ein Kunde eingekauft hat.<br>
        - <strong>Monetärer Wert</strong>: den Gesamtbetrag, den ein Kunde für seine Einkäufe ausgegeben hat.<br>
    - RFM wird verwendet, um Kunden auf der Grundlage ihres Kaufverhaltens zu identifizieren und zu kategorisieren, d. h. wie häufig und kürzlich sie eingekauft haben und wie hoch der Geldwert dieser Einkäufe ist.<br>
	   
**Referenz**
- https://www.putler.com/rfm-analysis

### 📁 Datensatzbeschreibung & Datenstruktur
## 📌 Datenquelle<br>
* Quelle: Bereitgestellter Datensatz für die Analyse des E-Commerce-Einzelhandels<br>
* Umfang: 541.910 Zeilen × 8 Spalten (Tabelle 1: E-Commerce Retail), zusätzliche Segmentierungsdetails in Tabelle 2<br>
* Format: .xlsx (Excel-Datei mit zwei Tabellenblättern)<br>

## 📊 Datenstruktur & Beziehungen
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
## 📌 Bibliotheken importieren
<img width="700" alt="Screenshot 2025-07-01 at 9 04 11 AM" src="https://github.com/user-attachments/assets/eff40e30-91c4-48ff-91a5-0a8303acadb7" />
<img width="700" alt="Screenshot 2025-07-01 at 9 16 29 AM" src="https://github.com/user-attachments/assets/0aa3014d-6080-457b-b787-a95169d5d593" />
<img width="700" alt="Screenshot 2025-07-01 at 9 15 13 AM" src="https://github.com/user-attachments/assets/902a0c25-414a-4fb0-b113-04f3c3db0b2b" />
<img width="700" alt="Screenshot 2025-07-01 at 9 15 23 AM" src="https://github.com/user-attachments/assets/1ce2522d-662c-4c34-a172-f755421e32f9" />

## 📌 Explorative Datenanalyse (EDA)
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

## 📌 RFM <br> 
<img width="700" alt="Screenshot 2025-07-01 at 9 58 03 AM" src="https://github.com/user-attachments/assets/c0f308fc-140b-4961-ae98-636da60b6628" />
<img width="700" alt="Screenshot 2025-07-01 at 10 01 21 AM" src="https://github.com/user-attachments/assets/6ed79069-f06f-4421-9be0-bc6cf00c1797" />
<img width="700" alt="Screenshot 2025-07-01 at 10 01 29 AM" src="https://github.com/user-attachments/assets/ca372425-9f27-47d5-a3ec-51fdbc0a505e" /><br>

---

👉 Das RFM-Modell zeigt für jeden Kunden, wie kürzlich (Recency), wie häufig (Frequency) und mit welchem Geldwert (Monetary) er eingekauft hat. Zum Beispiel hat der Kunde mit der ID 12347.0 vor nur 2 Tagen zuletzt gekauft, insgesamt 7 Bestellungen getätigt und dabei 4310 £ ausgegeben – ein wertvoller und aktiver Kunde.<br>
<img width="700" alt="Screenshot 2025-07-01 at 10 06 15 AM" src="https://github.com/user-attachments/assets/d0fcab37-7958-4ff8-a44b-a954e7683f34" />
<img width="700" alt="Screenshot 2025-07-01 at 10 06 20 AM" src="https://github.com/user-attachments/assets/d143e8e8-bec4-47f9-9fde-59101fbc3e06" />.<br>

---

👉 Ein hoher RFM_Score wie „555“ signalisiert einen besonders wertvollen Kunden: kürzlich aktiv, sehr kauffreudig und mit hohem Umsatz.<br>

<img width="700" alt="Screenshot 2025-07-01 at 10 06 30 AM" src="https://github.com/user-attachments/assets/87a61e4a-3afa-4532-ac2a-bc975b9b4fe7" />
<img width="700" alt="Screenshot 2025-07-01 at 10 06 37 AM" src="https://github.com/user-attachments/assets/be5fd83f-4460-4905-bd0e-3aecf3b7a52e" />
<img width="700" alt="Screenshot 2025-07-01 at 10 14 15 AM" src="https://github.com/user-attachments/assets/e0f50a6d-451d-41f9-9330-1a61803471bc" /><br>
<img width="700" alt="Screenshot 2025-07-01 at 10 14 26 AM" src="https://github.com/user-attachments/assets/6f43f1c6-eae8-43e4-9684-dffe65505538" /><br>

**🎯 Ergebnisanalyse:**
Die aktuelle Segmentstruktur zeigt, dass nur <strong>~1 von 10 Kunden</strong> hochprofitabel ist, während fast die Hälfte gefährdet ist, komplett verloren zu gehen. Ziel sollte sein, die „Potenzial“-Gruppe zu aktivieren und die „Risiko“-Gruppe zu analysieren oder selektiv zu bearbeiten.

## 📊 Visualisierungen der RFM-Werte (Histogramme)
1. Boxplots zur Erkennung von Ausreissern
<img width="700" alt="Screenshot 2025-07-01 at 9 05 27 PM" src="https://github.com/user-attachments/assets/18e856ef-2a4e-4fbc-a89e-c44fc88c99fd" />
<img width="700" alt="Screenshot 2025-07-01 at 9 06 12 PM" src="https://github.com/user-attachments/assets/fafdb176-1b8c-404a-9309-04b8749b6631" />
<img width="700" alt="Screenshot 2025-07-01 at 9 06 22 PM" src="https://github.com/user-attachments/assets/12df803b-d741-4efe-86df-dae7e2d91704" /><br>

---

👉 In allen drei Fällen zeigen die Diagramme, dass es einige wenige Kunden mit sehr hohen Werten gibt – diese Ausreißer könnten besonders interessante oder atypische Kundenprofile darstellen.<br>

---

2. Heatmap der durchschnittlichen Monetärwertr je R/F-Score
<img width="700" alt="Screenshot 2025-07-01 at 9 09 10 PM" src="https://github.com/user-attachments/assets/fb1f8bc7-b36f-4a9a-b36b-b9b5d5e9aa07" />
<img width="700" alt="Screenshot 2025-07-01 at 9 09 17 PM" src="https://github.com/user-attachments/assets/775114cb-5a03-4bd4-b6e1-9ac211dee6b2" />
<br>

---

👉 Kunden mit einem hohen R- und F-Score (z. B. R=5, F=5) haben tendenziell auch einen höheren Umsatz, was sie zu besonders wertvollen Zielgruppen macht.
<br>

---

4. Kundensegmentierung auf Basis von RFM
<img width="700" alt="Screenshot 2025-07-01 at 9 10 07 PM" src="https://github.com/user-attachments/assets/5eb4d7d3-082b-4919-af23-a9e31108e570" />
<img width="700" alt="Screenshot 2025-07-01 at 9 10 14 PM" src="https://github.com/user-attachments/assets/d5029356-46ac-4d2f-89ee-72851d6b6191" />
<br>
👉 Diese Segmentierung ermöglicht es Unternehmen, gezielte Marketingstrategien für jede Gruppe zu entwickeln und dadurch Kundenbindung sowie Umsatz zu optimieren.
<br>
## 🔎 Kundenanalyse nach Segmenten – Erkenntnisse & Vorschläge
### 1. 💡 **Potenzielle Loyalität**
Dieses Segment ist mit Abstand das größte, was zeigt, dass viele Kunden aktiv, aber noch nicht fest gebunden sind.  
👉 Um ihre Loyalität zu stärken, sollten gezielte Treueprogramme, personalisierte Angebote und Kundenbindungskampagnen eingesetzt werden.

---

### 2. ⚠️ **Abwanderungsgefährdet**
Ein großer Teil der Kunden zeigt Anzeichen von Abwanderung, was ein klares Warnsignal darstellt.  
👉 Um diesen Verlust zu vermeiden, sollten proaktiv Anreize, gezielte Reaktivierungskampagnen und persönliche Kontaktaufnahmen erfolgen.

---

### 3. 🔍 **Benötigt Aufmerksamkeit**
Diese Kunden stehen kurz davor, sich zu entfernen oder vergessen zu werden, obwohl sie noch Potenzial zeigen.  
👉 Durch gezielte Kommunikation, z. B. E-Mails, Umfragen oder Service-Interaktionen, kann ihre Aktivität und Zufriedenheit wieder erhöht werden.

---

### 4. 🧡 **Treue Kunden**
Diese Gruppe ist wertvoll, aber im Vergleich eher klein – es besteht Wachstumspotenzial.  
👉 Durch gezielte Wertschätzung (z. B. Bonuspunkte, Early Access) kann ihre Loyalität weiter gestärkt und langfristig gesichert werden.

---

### 5. 🌀 **Andere**
Diese nicht näher definierten Kunden zeigen ein mittleres Aktivitätsniveau, was auf heterogene Verhaltensmuster hinweist.  
👉 Eine tiefergehende Segmentierung und Analyse dieser Gruppe kann verstecktes Potenzial aufdecken oder Problemfelder identifizieren.

---

### 6. 🏆 **Champions**
Obwohl sie die besten und loyalsten Kunden darstellen, ist ihr Anteil sehr gering.  
👉 Um diese Kunden zu halten und als Markenbotschafter zu nutzen, sollten exklusive Vorteile, VIP-Programme und Empfehlungsaktionen angeboten werden.

---

### 7. 🚪 **Abgewandert**
Dieses Segment ist aktuell klein, aber es zeigt, dass gewisse Kunden bereits verloren gingen.  
👉 Eine Reaktivierung könnte über gezielte Rückgewinnungskampagnen erfolgen, während gleichzeitig Ursachen für die Abwanderung analysiert und zukünftig verhindert werden sollten.






