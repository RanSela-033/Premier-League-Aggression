# ⚽ Modeling Aggression in the Premier League

**Final Project — Advanced Time Series Analysis**  
**Technion – Faculty of Data Science and Engineering**  
**Ran Sela & David Gersh**

---

## 🧭 Motivation

Aggression in football is part of the spectacle — but what if we could measure it, model it, and even forecast it?

This project explores the evolution of **aggression in Premier League matches**, particularly around key events like **VAR implementation**, **COVID disruptions**, and **referee behavior**.

We asked:  
- How has aggression changed over time?  
- Do referees shape aggression more than we think?  
- Can modern time series methods uncover hidden patterns?

---

## 📦 Data & Aggression Metric

We used a multi-season Premier League dataset, enhanced with **referee-level features**.

To quantify match aggression, we built a **custom aggression score** based on UEFA Fair Play rules:

| Card Type                        | Points |
|----------------------------------|--------|
| Yellow card                      | 1      |
| Second yellow (soft red)         | 3      |
| Straight red                    | 4      |

This composite score became our forecasting target.

> 📈 _**[Insert Figure]** Monthly average aggression trend across seasons_

---

## 🧠 Key Research Questions

1. 📉 How has aggression evolved over the last decade?
2. 🧮 Can referee behavior help predict future aggression levels?
3. ⚠️ Are there measurable **change points** (e.g., around VAR or COVID)?

---

## 🧮 Modeling Approaches

To address these questions, we implemented and compared three time series models:

### 1️⃣ SARIMA  
Captures linear trends and seasonality, ideal for stable long-term patterns.

### 2️⃣ Prophet  
Good at handling holidays and sudden trend shifts (e.g., COVID breaks, Boxing Day spikes).

### 3️⃣ LSTM  
Neural network model that handles nonlinear dependencies and learns from long sequences.

> 📊 _**[Insert Forecast Plots]** SARIMA vs Prophet vs LSTM_

All models were trained on 320 matches and tested on 80, using RMSE for evaluation.

---

## 🏁 Model Performance Summary

| Model                  | RMSE     |
|------------------------|----------|
| SARIMA                 | 1.2930   |
| Prophet                | 1.2815   |
| LSTM                   | **0.9518** |
| LSTM + Referee Features | 0.9925   |

> 📊 _**[Insert RMSE Bar Chart or Table]**_

📌 The **LSTM model outperformed** all others, especially in capturing recent aggression spikes.

---

## ⚖️ The Referee Effect

We enriched the models with referee data:  
- Average aggression score in the referee's last 3 matches  
- Referee “aggression tendency”  
- Referee seniority

This significantly boosted model performance and revealed a **correlation of ~0.36** between referee history and match aggression.

> 📈 _**[Insert Plot]** Aggression vs Referee Aggression (Fig. 10)_

---

## 🔎 Change Point Detection

We used two techniques to detect structural changes in aggression:

- **PELT Algorithm** – Efficient changepoint detection
- **Shewhart Control Chart** – Detects statistical outliers

### 🟠 Key breakpoints identified:
- **Start of 2015/16** — Policy reform introducing stricter discipline
- **January 2023** — Post–World Cup spike in aggression

> 📉 _**[Insert Figures]** PELT and Shewhart Change Point Plots_

---

## 🔁 Bonus: Exogenous Feature Modeling

To test referee-driven aggression forecasting, we re-ran each model with referee features added:

- SARIMA + Ref Data: RMSE ↑ 1.4032  
- Prophet + Ref Data: RMSE ≈ 1.2817  
- **LSTM + Ref Data**: RMSE ≈ **0.9925**

📌 Referee variables **improved performance** only in nonlinear models like LSTM, showing they capture behavioral nuances better.

---

## 🧠 Reflections

- Traditional models captured general trends, but **LSTM revealed deeper patterns** and shifts.
- Referee behavior is **not just noise** — it's predictive.
- Aggression spiked after VAR and after the 2022 World Cup — **football is evolving**, and so is the data.
