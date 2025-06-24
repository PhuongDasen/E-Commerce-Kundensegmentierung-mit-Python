# [PYTHON] RFM-Analysis 
**I. Einleitung**<br>
**1. Über RFM-Analyse**<br>
**Warum RFM?**<br>
    - RFM ist eine Marketinganalysetechnik, die für Recency (Aktualität), Frequency (Häufigkeit) und Monetary Value (Geldwert) steht.<br>
        - Aktualität: wie oft ein Kunde in letzter Zeit eingekauft hat.<br>
        - Häufigkeit: wie oft ein Kunde eingekauft hat.<br>
        - Monetärer Wert: den Gesamtbetrag, den ein Kunde für seine Einkäufe ausgegeben hat.<br>
    - RFM wird verwendet, um Kunden auf der Grundlage ihres Kaufverhaltens zu identifizieren und zu kategorisieren, d. h. wie häufig und kürzlich sie eingekauft haben und wie hoch der Geldwert dieser Einkäufe ist.

**Wie?**<br>
Bei der RFM-Analyse werden die Kunden anhand von drei Faktoren bewertet (Aktualität, Häufigkeit - wie oft, Geldwert - wie viel) und dann auf der Grundlage der Kombination der RFM-Werte eingestuft

**Referenz**
- https://www.putler.com/rfm-analysis

**2. Geschäftliche Fragen**<br>
        <u>**Kontext**</u>
  - SuperStore Company ist ein globales Einzelhandelsunternehmen. Das Unternehmen hat also viele Kunden. Anlässlich von Weihnachten und Neujahr möchte die Marketingabteilung Marketingkampagnen durchführen, um den Kunden zu danken, die das Unternehmen in der vergangenen Zeit unterstützt haben. Und Sie gewinnen Kunden, die das Potenzial haben, zu Stammkunden zu werden.
  - Die Marketingabteilung muss die Segmente der einzelnen Kunden klassifizieren, um für jede Kundengruppe das passende Marketingprogramm zu entwickeln.
  - Der Marketing-Direktor schlug außerdem vor, das RFM-Modell in Python zu verwenden, um die Kunden zu segmentieren und dann Marketingkampagnen zu starten, um den Kunden für ihre Unterstützung des Unternehmens in der Vergangenheit zu danken. Außerdem sollten potenzielle Kunden dazu gebracht werden, treue Kunden zu werden.
  - Welcher der drei Indikatoren R, F und M sollte für das Marketing- und Vertriebsteam im Rahmen des Einzelhandelsmodells des Unternehmens am interessantesten sein?

**II.Datenvisualisierung mit Python**
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

**III.Insights**
1. Der wichtigste Index der drei Indikatoren, auf die SuperStore achten sollte, ist F, gefolgt von R: Der Anteil der Kunden, die ein- und zweimalkaufen, ist sehr hoch. Nur sehr wenige Kunden tätigen langfristige Käufe, z.B: 8-9 Mal oder öfter. Das zeigt, dass die Kundenbindungsrate des Unternehmens weiterhin niedrig ist.
2. Zur Kundensegmentierung: Das Unternehmen besteht hauptsächlich aus "Neukunden" > "Kunden im Ruhestand" > "Verlorene Kunden". Das zeigt erneut, dass wir dem Index F Aufmerksamkeit schenken sollte.
3. Umsatzt und Gewinn aus "Neukunden" sind am höchsten.
4. Der Umsatz in der Region Ost ist im Vergleich zu den anderen drei Regionen am niedrigsten.
5. Kalifornien, Texas, Illinois und Floria sind die Bundesstaaten mit den meisten Bestellungen.
6. Die Hauptkunden des Unternehmens sind Privatkunden (52%), Unternehmen (30%) und schliesslich Homeoffice-Kunden.
7. Die bestellstärksten Kategorien sind "Bürobedarf" (bis zu 60%), gefolgt von "Möbeln".
8. Die wichtigsten Unterkategorien sind: Papier (14%), Ordner(15%), Kunst (9%), Telefone und Aufbewahrung (8 %).




 





