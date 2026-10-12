# India-Stocks-271-300-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 271 to 300)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-271-300-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (271 to 300)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 271 | `BEML` | BEML Ltd. | `BEML.NS` |
| 272 | `BLS` | BLS International Services Ltd. | `BLS.NS` |
| 273 | `BAGMANE` | Bagmane Prime Office REIT | `BAGMANE.NS` |
| 274 | `BALRAMCHIN` | Balrampur Chini Mills Ltd. | `BALRAMCHIN.NS` |
| 275 | `BANDHANBNK` | Bandhan Bank Ltd. | `BANDHANBNK.NS` |
| 276 | `BATAINDIA` | Bata India Ltd. | `BATAINDIA.NS` |
| 277 | `BELRISE` | Belrise Industries Ltd. | `BELRISE.NS` |
| 278 | `BHARATCOAL` | Bharat Coking Coal Ltd. | `BHARATCOAL.NS` |
| 279 | `BSOFT` | Birlasoft Ltd. | `BSOFT.NS` |
| 280 | `BBOX` | Black Box Ltd. | `BBOX.NS` |
| 281 | `FIRSTCRY` | Brainbees Solutions Ltd. | `FIRSTCRY.NS` |
| 282 | `BRIGADE` | Brigade Enterprises Ltd. | `BRIGADE.NS` |
| 283 | `BIRET` | Brookfield India Real Estate Trust | `BIRET.NS` |
| 284 | `CCL` | CCL Products (I) Ltd. | `CCL.NS` |
| 285 | `CESC` | CESC Ltd. | `CESC.NS` |
| 286 | `CIEINDIA` | CIE Automotive India Ltd. | `CIEINDIA.NS` |
| 287 | `CANFINHOME` | Can Fin Homes Ltd. | `CANFINHOME.NS` |
| 288 | `CANHLIFE` | Canara HSBC Life Insurance Company Ltd. | `CANHLIFE.NS` |
| 289 | `CAPLIPOINT` | Caplin Point Laboratories Ltd. | `CAPLIPOINT.NS` |
| 290 | `CGCL` | Capri Global Capital Ltd. | `CGCL.NS` |
| 291 | `CARBORUNIV` | Carborundum Universal Ltd. | `CARBORUNIV.NS` |
| 292 | `CARTRADE` | Cartrade Tech Ltd. | `CARTRADE.NS` |
| 293 | `CASTROLIND` | Castrol India Ltd. | `CASTROLIND.NS` |
| 294 | `CEATLTD` | Ceat Ltd. | `CEATLTD.NS` |
| 295 | `CEMPRO` | Cemindia Projects Ltd. | `CEMPRO.NS` |
| 296 | `CENTRALBK` | Central Bank of India | `CENTRALBK.NS` |
| 297 | `CDSL` | Central Depository Services (India) Ltd. | `CDSL.NS` |
| 298 | `CMPDI` | Central Mine Planning & Design Institute Ltd. | `CMPDI.NS` |
| 299 | `CHAMBLFERT` | Chambal Fertilizers & Chemicals Ltd. | `CHAMBLFERT.NS` |
| 300 | `CHENNPETRO` | Chennai Petroleum Corporation Ltd. | `CHENNPETRO.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream BEML 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-271-300-Historical-Data/main/BEML/1m/2026/10/BEML_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
