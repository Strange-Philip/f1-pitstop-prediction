# 🏎️ F1 Pit Stop Prediction — Kaggle Playground Series 2026

Predicting whether a Formula 1 driver will pit on the next lap using tabular race data.

---

## 🧠 Why this project exists

I didn’t start this project because it was “just another Kaggle competition”.

I started it because F1 strategy feels a lot like real-world decision systems — noisy signals, incomplete information, and decisions that depend heavily on context over time.

A pit stop is never just a number in a table.
It’s a response to degradation, pressure, race position, timing windows, and intuition built over hundreds of laps.

That’s the kind of structure I want to learn how to model.

This project is part of my broader exploration into:

* sequential decision systems
* real-world ML signals hidden in tabular data
* and building intuition for time-dependent prediction problems

---

## 🎯 Goal

Given race state information at a specific lap:

> Predict the probability that a driver will pit on the next lap.

Evaluation metric:

* ROC-AUC score

Competition: [Kaggle Competition Page](https://www.kaggle.com/competitions?utm_source=chatgpt.com)

---

## 📊 Dataset Overview

Each row represents a driver’s state at a given lap.

Key features include:

* Driver identity and race context
* Tire compound and tire life
* Lap number and stint progression
* Lap time and degradation signals
* Position and race dynamics

Target:

* `PitNextLap` (0 or 1)

---

## 🧩 Feature intuition (early thinking)

Some of the signals that immediately stand out:

* **TyreLife** → how close a driver is to degradation limits
* **LapTime_Delta** → pace deterioration over time
* **RaceProgress** → global race timing context
* **Position & Position_Change** → strategic pressure signals
* **Cumulative_Degradation** → engineered wear signal

What makes this interesting is that many features already encode partial “strategy understanding”, so the challenge becomes combining them correctly rather than just predicting from scratch.

---

## ⚙️ Approach (current stage)

Right now the workflow is intentionally simple:

1. Load and inspect dataset
2. Understand feature meanings in race context
3. Identify predictive vs potentially leaky signals
4. Build baseline models (starting with gradient boosting)
5. Iterate through feature engineering based on intuition

Models being explored:

* Logistic Regression (baseline)
* Random Forest (sanity check)
* LightGBM / XGBoost (main model)

Libraries:

* pandas
* scikit-learn
* LightGBM / XGBoost

---

## 🧪 Current status

* [x] Dataset loaded and explored
* [x] Feature meanings interpreted
* [x] Target distribution analyzed
* [x] Baseline model training — CatBoost Val AUC: **0.9434**
* [x] Feature importance analyzed (top signal: LapTime_Delta, Stint, TyreLife)
* [x] First Kaggle submission
* [ ] Feature engineering iteration loop

---

## 🔭 What I’m trying to learn from this

Beyond Kaggle performance, this project is a testbed for:

* thinking in temporal patterns instead of static features
* understanding decision-making under constraints
* building intuition for degradation and resource optimization
* practicing real-world ML iteration cycles

Eventually, I want to connect these ideas to:

* healthcare decision systems
* assistive AI
* and sequential prediction in vision science contexts

---

## 🚀 Next steps

* Engineer lag + rolling features
* Document experiments properly (like a research log)

---

## 📌 Links

* Kaggle Competition: [F1 Pit Stop Prediction](https://www.kaggle.com/competitions?utm_source=chatgpt.com)
* Portfolio: [Philip Abakah Portfolio](https://philip-abakah-portfolio.vercel.app/?utm_source=chatgpt.com)
* GitHub: [GitHub Profile](https://github.com/?utm_source=chatgpt.com)

---

## 🧭 Closing thought

The interesting part of this project isn’t the model.

It’s learning how to translate a messy, dynamic system (a race) into something a model can reason about — without losing the structure that makes the system meaningful.

That’s the skill I’m trying to build here.
