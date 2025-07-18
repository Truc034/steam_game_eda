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

### Data Preprocessing:
- Removed non-game entries (beta, demo, SDK, tools)
- Filtered games from 2004-2024 (complete years only)
- Converted estimated owner ranges to numeric midpoints
- Handled missing values with appropriate defaults
- Applied outlier capping at 99th percentile

### Feature Engineering:
- **Popularity Score:** Time-normalized composite metric (owners: 50%, reviews: 30%, recommendations: 20%)
- **Value Score:** (Popularity × Review Ratio) ÷ (Price + 1)
- **Review Ratio:** Positive reviews / Total reviews
- **Price Categories:** Free, Under $10, $10-30, $30-60, Over $60
- **Genre Encoding:** One-hot encoded 33 genres for analysis

## 🛠️ Tools and Technologies Applied

- **Python Libraries:**
  - `pandas`, `numpy` - Data manipulation and analysis
  - `matplotlib`, `seaborn` - Data visualization  
  - `sklearn` - Machine learning preprocessing
  - `kagglehub` - Dataset acquisition
- **Development Environment:** Jupyter Notebook
- **Data Processing:** Feature engineering, outlier treatment, normalization

## 💡 Key Insights Discovered

### Market Structure
- **Massive Scale:** Over 85,000 games across 33 genres
- **Rapid Growth:** 650% increase in yearly releases from 2014-2024
- **Pricing:** Median price $4.99, with most games affordably priced
- **Market Concentration:** Few hits dominate; most games have moderate engagement

### Genre Performance
- **Mainstream Genres** (Indie, Action, Adventure): High volume but intense competition
- **Strategic Genres** (Strategy, RPG, Simulation): Strong engagement with loyal audiences
- **Professional Tools:** Low engagement but higher price tolerance

### Success Patterns
- **Quality Drives Success:** Higher review ratios correlate with popularity
- **Sweet Spot Pricing:** $10-30 range balances accessibility and perceived value
- **Mature Market:** Adult-oriented games show higher price tolerance and engagement
- **DLC Effectiveness:** Most successful as post-launch extensions, not initial drivers

### Developer Insights
- **Indie Advantage:** Independent developers achieve better review ratios (0.64 vs 0.57)
- **Market Opportunity:** Top 10 publishers hold only 2.7% market share

## 🧠 Hypotheses Based on Insights

1. **Quality-First Hypothesis:** Games with higher review ratios will achieve greater popularity regardless of genre or price
2. **Strategic Pricing Hypothesis:** Games priced in the $10-30 range will show optimal value scores and sales performance
3. **Niche Focus Hypothesis:** High-quality niche content can yield higher ROI despite lower overall engagement
4. **Post-Launch DLC Hypothesis:** DLC developed after establishing a strong player base significantly extends profitability
5. **Mature Audience Hypothesis:** Games targeting adult audiences can command higher prices and achieve stable returns

## ✅ Recommendations Based on Analysis Results

### For Developers
**Focus on Quality Over Quantity** 🏆
- Prioritize 10-20 high-quality titles rather than mass production
- Target review ratios of 0.4-0.6 or higher for sustained success
- Consider niche genres (Strategy, RPG, Simulation) for less competition

**Optimize Pricing Strategy** 💰
- Use $10-30 as the sweet spot for balancing accessibility and value perception
- Avoid underpricing; higher prices work when value is clearly justified
- Consider tiered pricing and demo offerings

### For Publishers
**Strategic Market Approach** 🎯
- Embrace quality over quantity in portfolio development
- Target mature audiences (age 25-45) for stable, valuable demographics
- Use early review patterns to monitor and adjust title performance

**DLC Strategy** 🚀
- Launch DLC after core game proves successful
- Base DLC development on player feedback
- Ensure DLC quality matches core experience

### For Investors
**Market Intelligence** 📊
- Track normalized value scores to identify long-term performers  
- Invest in developers with consistent review quality across titles
- Monitor genre trends and emerging niches

### Common Pitfalls to Avoid ⚠️
- Optimizing for review scores instead of genuine player satisfaction
- Launching DLC too early in game lifecycle
- Underpricing due to fear of low sales
- Ignoring the valuable adult market segment

---

*This analysis reveals that in Steam's competitive landscape, success comes from delivering quality experiences at strategic price points, with sustained engagement through post-launch support rather than relying on initial viral success.*
