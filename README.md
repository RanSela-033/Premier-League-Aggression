# Premier-League-Aggression
⚽ Aggression Analysis in the Premier League Using Time Series Models

**Final Project – Advanced Time Series Analysis**  
**Technion – Faculty of Data Science and Engineering**  
**By: Ran Sela (207757022) & David Gersh (207796996)**

---

## 📌 Project Overview

This project investigates **aggression trends in Premier League football matches**, with a focus on the impact of **VAR implementation** and **referee behavior**. Using various time series models, we analyze the evolution of aggression over multiple seasons and explore how referee characteristics correlate with in-game aggression levels.

---

## 🎯 Research Questions

1. How has aggression in the Premier League evolved over recent seasons?
2. Can referee-specific behavior (e.g., prior aggression levels) predict aggression in future matches?
3. Do key events (like VAR introduction or the COVID-19 period) correspond to significant shifts in aggression trends?

---

## 🧮 Methodology

We used the following time series modeling techniques:

- **SARIMA** – for capturing seasonality and linear trends
- **Prophet** – for automatic changepoint detection and holiday effects (e.g., Boxing Day)
- **LSTM** – to model nonlinear temporal dependencies
- **Change Point Detection**:
  - **PELT Algorithm**
  - **Shewhart Control Chart**

We also examined the effect of **exogenous referee variables**, such as:
- Average red/yellow cards issued by referee in last 3 matches
- Referee seniority
- Aggression tendency score

---

## 📊 Aggression Metric

We defined a match aggression score based on UEFA Fair Play guidelines:

- Yellow card = 1 point  
- Red card (direct or 2 yellows) = 3–4 points depending on context

This composite score served as the target variable across all models.

---

## 🔍 Key Findings

- **Aggression levels peaked** following the introduction of VAR and declined during COVID-affected seasons.
- **Referee behavior has a measurable influence** on match aggression (correlation ≈ 0.36).
- The **LSTM model outperformed** SARIMA and Prophet in terms of RMSE:
  - `SARIMA`: 1.293  
  - `Prophet`: 1.281  
  - `LSTM`: **0.951**

Adding referee data as exogenous variables further improved predictive accuracy in the LSTM model.

---

## 📈 Change Point Detection

We identified two statistically significant breakpoints:
- Start of the 2015/16 season (likely tied to the Premier League's disciplinary overhaul)
- January 2023 (coinciding with the post-World Cup phase and increased scrutiny of refereeing)

---

## 📚 Data Sources

- [Premier League Kaggle Dataset](https://www.kaggle.com/datasets/ajaxianazarenka/premier-league?resource=download)
- [RU.NI: VAR impact study](https://www.runi.ac.il/media/lbinqckt/2024-football-referees-issue-more-yellow-cards-following-var-interventions.pdf)
- [Premier League Tactical Review](https://www.premierleague.com/news/693455)

---

## 📦 Repo Structure
