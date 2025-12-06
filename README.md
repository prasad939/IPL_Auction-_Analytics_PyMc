# IPL_Auction-_Analytics_PyMc
🏏 IPL Auction Analytics using Bayesian Modeling (PyMC)
A probabilistic decision system for selecting the optimal Death-Overs Specialist in the IPL auction.
⭐ Project Overview

This project builds a Bayesian Hierarchical Model (BHM) using PyMC to quantify the hidden “Pressure Effect” (Killer Instinct) of bowlers during IPL death overs (17–20).

Traditional stats like economy rate or bowling average fail to capture clutch behavior under extreme match pressure.
This model solves exactly that problem.

We estimate:

🔥 Wicket probability under pressure

🎯 Ball-level posterior predictive distributions

📈 Bowler-specific random effects

⚡ How pitch, pressure, and match state influence performance

👑 Final auction recommendation: Bowler A vs Bowler B

Used by analysts to evaluate who should be purchased as the team's Death-Overs Specialist.

📊 Key Features

Bayesian Hierarchical Logistic Regression

94% High Density Interval (HDI)–based decision framework

Posterior predictive simulation (ppc) for each ball

Random effects for bowlers + pitch types

Inference using NUTS sampler (PyMC)

Model explainability with ArviZ

🧠 Why Bayesian Modeling?

Death overs are rare events → small sample size → high uncertainty.
Bayesian modeling quantifies uncertainty, instead of hiding it.

This project:

Shows full posterior distribution

Computes HDI for true wicket-taking ability

Removes overfitting with partial pooling

Produces robust decisions for recruitment

📁 Repository Structure
IPL_Auction-Analytics-PyMC/
│
├── data/
│   └── cleaned_deathovers.csv
│
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Bayesian_Model.ipynb
│   ├── 03_Posterior_Predictive.ipynb
│   └── 04_Final_Recommendation.ipynb
│
├── src/
│   ├── modeling.py
│   ├── loader.py
│   └── metrics.py
│
├── plots/
│   ├── trace_plots.png
│   ├── hdi_plots.png
│   └── pressure_curves.png
│
├── README.md
└── requirements.txt

🧮 Model Summary
Hierarchical Logistic Model
logit
(
𝑝
)
=
𝛽
0
+
𝛽
pitch
+
𝛽
pressure
+
𝑢
bowler
logit(p)=β
0
	​

+β
pitch
	​

+β
pressure
	​

+u
bowler
	​


Where:

β₀ → global intercept

u_bowler → random intercept per bowler

β_pitch → pitch-level effect

β_pressure → pressure-level effect

Posterior sampling: pm.sample() using NUTS
Posterior predictive: pm.sample_posterior_predictive()

🏆 Final Recommendation (From Model)

👉 Bowler B has a higher posterior wicket probability in death overs.

📌 The 94% HDI of pressure-effect posterior for Bowler B
does not overlap with that of Bowler A.

This means:

Bowler B is more likely to convert pressure into wickets

Bowler B is a better buy for the "Death Overs Specialist" role

Bowler A's performance drops under high-pressure, high-leverage situations

📈 Visual Outputs

Trace plots

HDI intervals for pressure effect

Posterior predictive wicket curves

Random effects distribution per bowler

Bowler comparison using Bayesian decision rule

🔍 Installation
Create environment
conda create -n pymc_env python=3.10 -y
conda activate pymc_env

Install dependencies
pip install -r requirements.txt

▶️ How to Run the Project
jupyter lab


Open:

notebooks/02_Bayesian_Model.ipynb

notebooks/04_Final_Recommendation.ipynb

🛠 Technologies Used

PyMC (Bayesian modeling)

ArviZ (diagnostics + visualization)

Python

NumPy / Pandas / Matplotlib / Seaborn

Jupyter Lab

🚀 Future Improvements

Add ball-by-ball win probability modeling

Use Gaussian Process priors for non-linearity

Include batter quality effects

Extend model for T20 leagues beyond IPL

Build a web dashboard (Streamlit) for analysts
