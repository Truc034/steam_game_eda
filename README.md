# 🎮 Steam Games Data Analysis

## 🎯 1. Objectives

This project analyzes the Steam game market to understand characteristics that contribute to game success. Key objectives include:

- Understanding the Steam market landscape (size, genre diversity, pricing strategies)
- Identifying trends in game releases, user engagement, and success patterns over time
- Uncovering relationships between game attributes (price, genre, reviews, DLC) and success metrics
- Formulating strategic recommendations for optimal game development and marketing on Steam

## 📂 2. Dataset sources

- **Source:** [Kaggle - Steam Games Dataset by Fronkongames](https://www.kaggle.com/datasets/fronkongames/steam-games-dataset/data)
- **Backup Path**: Data used in this project is backed up in [`250718_Steam_dataset.rar`](https://drive.google.com/drive/u/3/folders/1VLbq0dcjlP0BuyW57s3NYV9kpxDQ10i4))

This dataset has been created with [this code](https://github.com/FronkonGames/Steam-Games-Scraper) (MIT) and use the API provided by Steam, the largest gaming platform on PC. Data is also collected from Steam Spy.

## 🔍 3. Dataset overview
- **Original Size:** 111,452 games × 40 columns
- **Cleaned Size**: 85,268 games × 54 features (after cleaning and feature engineering)
- **Analysis Period:** 2004 to May 2025

### Key Original Columns:
| Column | Description |
|--------|-------------|
| AppID | Unique Steam game identifier |
| Name | Game title |
| Release date | Game launch date |
| Estimated owners | Range of estimated game owners |
| Price | Game price in USD |
| Positive | Number of positive reviews |
| Negative | Number of negative reviews |
| Recommendations | User recommendations count |
| Genres | Game genres (e.g., Action, RPG, Indie) |
| Publishers | Game creators |
| Developers | Game distributors |
| DLC count | Number of downloadable content packages |

## 🛠️ 4. Methodology

### 🔄 4.1. Data Preprocessing:
- Correct misalignment columns
- Remove irrelevant columns
- Check data consistency and convert `estimated owner` ranges to numeric midpoints
- Handled missing values and check duplicates
- Removed non-game entries (beta, demo, SDK, tools)
- Filtered games from 2004 - 2024
- Applied outlier capping at 99th percentile

### ❇️ 4.2. Feature Engineering:
- **Total Review:** Positive + Negative
- **Review Ratio:** Positive reviews / Total reviews
- **Popularity Score:** Time-normalized composite metric (owners: 50%, reviews: 30%, recommendations: 20%)
- **Value Score:** (Popularity × Review Ratio) ÷ (Price + 1)
- **Game age:** `current_year` - Release year
- **Popularity quintile:** Bottom 20%, Low, Medium, High, Top 20%
- **Price Categories:** Free, Under $10, $10-30, $30-60, Over $60
- **Popularity per Dollar:** Popularity score / Price
- **Genre Encoding:** One-hot encoded 33 genres for analysis

### ⚙️ 4.3. Tools and Technologies Applied

- **Python Libraries:**
  - `pandas`, `numpy` - Data manipulation and analysis
  - `matplotlib`, `seaborn` - Data visualization  
  - `sklearn` - Machine learning preprocessing
  - `kagglehub` - Dataset acquisition
- **Development Environment:** Jupyter Notebook

## 💡 5. Key Insights

### 🏗️ 5.1. Market Structure
- **Paid games dominate**
- **Rich genre mix**: 33 genres
- **Indie-friendly pricing**

### 🍂 5.2. Trends Overtime
- Explosive Growth in Game Releases from 2017 to 2024.
- Fall is peak season.
- Niche genres show no seasonality.

### 💸 5.3. Pricing & Positioning Strategy
- Quality matters more than price
- **$30–60** games for high-quality, well-marketed titles.
- Avoid low pricing unless have strong visibility.
- Success comes from polish, marketing, and player engagement, not discounts.

### 🕹️ 5.4. Genre Distribution
- Quality > Genre
- Design for retention
- F2P & niche are strong bets
- Mix genres smartly
- Avoid genre traps

### 🏷️ 5.5. Publisher & Developer Strategy
- Focus on quality, not volume
- Leverage the indie edge
- Market is open, new players can break in.
- Choose a fit strategy:  
  • Broad-scale = high titles, wide reach  
  • Quality-focus = fewer titles, stronger brand impact
- Build community early

### 👑 5.6. Legendary Game Strategy
- Timeless design lasts, invest in quality
- High review ratios = staying power
- No lifecycle drop-off
- Think portfolio: Mix classic, current, and future-focused titles for lasting impact.

### 🤖 5.7. Data-Driven Success Factors
- Value is king
- Early popularity scales
- Long-term wins
- High price works — if justified
- DLC boosts after success
- Focus on players, not just reviews

## 🧠 6. Hypotheses test

| No. | Research Question / Hypothesis                                                               | Status                                                                                                            |
| --- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| 1   | **Do indie games receive better user satisfaction (review ratio) than AAA titles?**          | ✅ Supported – Indie games have consistently higher average review ratios                                          |
| 2   | **Do Fall season releases perform better in terms of popularity score?**                     | ✅ Supported – Fall is the top-performing release window                                                           |
| 3   | **Are games priced above \$30 more likely to be popular or highly reviewed?**                | ❌ Not supported – Mid-range games (\$5–\$10) show better engagement                                               |
| 4   | **Do free-to-play games attract more players (higher estimated owners)?**                    | ✅ Supported – Free games tend to have significantly higher player base                                            |
| 5   | **Does the popularity-to-price ratio (value score) reliably identify top-performing games?** | ✅ Supported – Strong positive correlation found                                                                   |
| 6   | **Do games with more DLCs tend to achieve higher popularity scores?**                        | ⚠️ Partially supported – Some correlation in top genres, but not universal                                        |
| 7   | **Are newer games (under 1 year old) more popular than older titles?**                       | ❌ Not supported – Many older games retain high popularity due to updates and IP value                             |
| 8   | **Do certain genres (e.g., Strategy, RPG, Simulation) show stronger long-term engagement?**  | ✅ Supported – These genres have higher average scores and longevity                                               |
| 9   | **Does higher required age (e.g., 18+) correlate with better performance?**                  | ❌ Not supported – No significant relationship found between age restriction and popularity or reviews             |
| 10  | **Do games released in recent years (2023–2024) outperform earlier releases?**               | ❌ Not supported – While release volume increased, popularity is still concentrated in a small set of older titles |


## ✨ 7. Recommendations

### 7.1. For Indie Developers & New Studios
* Leverage **indie credibility** and higher review ratios (0.64).
* Identify and fill **niche market gaps** (92.5% success rate).
* Focus on **early community building** to drive engagement loops.
* Align pricing with actual value delivered, not competitor benchmarks.
  
### 7.2. For Established Studios
* Use **pricing power** effectively (avg. \$9.73 vs. \$7.17 for indies).
* Maximize **visibility and reach** through robust marketing pipelines.
* Avoid high-volume, low-quality strategies
* Invest in **IP longevity and brand equity** for scalable success.
  
### 7.3. For Publishers & Investors
* Take a **portfolio approach**, combining niche gems with high-polish mainstream titles.
* Target **long-term returns** by investing in games with multi-year update potential.
* Use **quality KPIs** like retention, engagement, and community participation to evaluate teams.
* Develop **internal F2P capabilities** for live-ops and monetization efficiency.

## 📌 8. **Conclusion**

Steam dominates PC gaming with **132M+ users** per month, but in a market over **85,000+ titles**, success no longer comes from luck — it’s driven by strategic choices.

### 🚨 **Avoid These Mistakes**

* Prioritizing reviews over player satisfaction
* Launching DLC too early
* Underpricing out of fear
* Ignoring the adult market
* Treating virality as luck, not strategy

### 🔑 **Top success drivers:**

* **Value wins:** Games offering better value (content vs. price) perform best (r = 0.90).
* **Community scales success:** The more players and fan support, the faster a game grows.
* **Attention is concentrated:** A few top games dominate player engagement.
* **Satisfaction drives reviews:** Focus on making players happy - reviews will follow.


---

> _“In the crowded world of Steam, insight beats instinct.”_
