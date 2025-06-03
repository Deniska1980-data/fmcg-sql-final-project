# FMCG SQL Finální Projekt: Analýza prodeje Leda vs. Tesa

Tento datový projekt analyzuje fiktivní FMCG data ze dvou obchodních řetězců – Leda a Tesa, působících v Česku a Slovensku. 
Cílem bylo pomocí SQL a Pythonu získat a vizualizovat klíčové obchodní poznatky z transakčních dat.

## Cíle analýzy
Porovnání tržeb mezi státy a měnami (CZK vs. EUR)
Analýza množství prodaného zboží
Dopad slev na zákaznické chování
Zjištění rozdílů v nákupních zvyklostech (časově i geograficky)
Identifikace nejprodávanějších produktů (dle tržeb a kusů)

## Použité nástroje
**SQL (MySQL)** – získávání dat z relační databáze  
**Python** – analýza a vizualizace dat  
**Excel (Power Query)** – doplňkové filtrování a exporty  
**ERD** – model relační databáze vytvořený v [dbdiagram.io](https://dbdiagram.io)

---
## 📁Struktura složky
FMCG-Projekt/
│
├── images/           # Grafy + ERD diagram
├── data/             # Exporty z SQL (XML soubory)
├── FMCG_Power Queri.xlsx  # Power Query transformace
└── README.md         # Popis projektu (tento soubor)

---
## ERD Diagram
![ERD Diagram](images/ERD_diagram.jpg)
---

## Vizualizace

### Počet nákupů podle dne v týdnu a státu
![Denní nákupy](počet%20nákupu%20podle%20dne%20v%20týdnu%20a%20státu.jpg)

### Počet nákupů podle hodin (celkově)
![Celkové časy](počet%20nákupu%20podle%20hodiny_FMCG.jpg)

### Počet nákupů podle hodin – Tesa vs. Leda
![Hodiny Tesa vs. Leda](počet%20nákupu%20podle%20hodin%20-%20Tesa%20vs.%20Leda.jpg)

---
## 📂Soubory ve složce `/data`

| Soubor                        | Popis                                              |
|------------------------------|-----------------------------------------------------|
| `currency_revenue.xml`       | Tržby podle měn (CZK, EUR)                          |
| `product_quantity.xml`       | Počet prodaných kusů podle produktů                |
| `discount_avg.xml`           | Průměrná sleva podle typu slevy                    |
| `product_revenue_sorted.xml` | Produkty podle výše tržeb                          |
| `city_purchases.xml`         | Počet nákupů v jednotlivých městech                |

---
## SQL ukázka

SELECT currency, SUM(unit_price * quantity) AS total_revenue
FROM transactions t
JOIN transaction_items ti ON t.id = ti.transaction_id
GROUP BY currency;

----
## Co jsem se naučila

Samostatně jsem psala a ladila SQL dotazy na reálných FMCG datech
Opravovala jsem nesprávně přiřazené měny k obchodům (CZ = CZK, SK = EUR)
Přizpůsobila jsem DPH sazby dle země a náležitých produktů (CZ: 2 sazby, SK: 3 sazby)
Porovnávala jsem nákupní časy v různých městech a státech
Vytvářela jsem grafy a vizualizace v Pythonu pro lepší interpretaci výsledků
Používala jsem ChatGPT pouze jako pomocníka při kontrole syntaxe a návrhu promptů
Všechny výstupy jsem ručně ověřila a logicky interpretovala

📌 Tento projekt je součástí mého portfolia jako Junior Data Analyst a představuje důkaz mé schopnosti:
- pracovat s databázemi,
- analyzovat reálná data,
- interpretovat obchodní kontext a vizuálně prezentovat výsledky.

🔍 Neustále si kladu nové otázky, hledám souvislosti a vidím, jak data pomáhají pochopit zákaznické chování.
Tento projekt mi pomohl propojit technické dovednosti se smysluplnou analytikou.
