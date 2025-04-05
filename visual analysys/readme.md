# 🏀 NBA Player Stats EDA & Feature Engineering

This project explores NBA player career statistics from 1946 to 2018 using historical data from three sources.

## 📦 Data Sources

- `Players.csv` — player names, height, weight, and college
- `player_data.csv` — extended biographical info
- `Seasons_Stats.csv` — per-season performance stats

All tables were merged using player names and birth year after preprocessing.

---

## 🧪 Tasks Completed

✅ Merged 3 raw datasets into 1 unified DataFrame  
✅ Fixed duplicates and inconsistent birth year logic  
✅ Created **5+ new features**, including:
- `age_end` – player age when career ended
- `carrier_start` – age when career started
- `years_played` – career length
- `ibm` – body mass index
- `goals_per_season` – sum of FG and FT  
✅ Generated **15+ plots**, including:
- Career length distributions
- College with most NBA players
- Age of peak performance
- Height/Weight/IBM distributions
- Correlation matrix of performance metrics
- Top 10 scorers and most efficient players

---

## 📊 Sample Visuals

*(Insert 2–3 images of your favorite graphs)*

---

## 🔍 Key Findings

- Most players start careers around **22–24** and finish by **33**
- **UCLA**, **Kentucky**, and **North Carolina** produce most NBA talent
- Players born in the **60s–80s** tend to have longer careers
- **Michael Jordan**, **Wilt Chamberlain**, and **LeBron James** dominate by both average points and total goals

---

## 🧠 Next Steps

- Add clustering by player position or era
- Predict career length using regression
- Explore injury data or salary impact (if available)

---

## 🧑‍💻 Author

**Serhii Kolotukhin**, Feedmill Engineer & Data Scientist  
🏀 Passionate about sports analytics and process intelligence  
📍 [www.linkedin.com/in/serhii-kolotuhkin-25648a166](#) | [GitHub](https://github.com/xxxsergxxx)

