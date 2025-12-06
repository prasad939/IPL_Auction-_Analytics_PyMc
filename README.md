### IPL Auction Analytics using Bayesian Modeling (PyMC)
### A probabilistic decision system for selecting the optimal Death-Overs Specialist in the IPL auction.

### Project Overview

#### This project builds a BAYESIAN  Generalized Linear Model (GLM) using PyMC to quantify the hidden “Pressure Effect” (Killer Instinct) of bowlers during IPL death overs (17–20).

- Traditional stats like economy rate or bowling average fail to capture clutch behavior under extreme match pressure.
This model solves exactly that problem.

- We estimate:

- Wicket probability under pressure

- Ball-level posterior predictive distributions

- Bowler-specific random effects

-  How pitch, pressure, and match state influence performance

- Final auction recommendation: Bowler A vs Bowler B

## Used by analysts to evaluate who should be purchased as the team's Death-Overs Specialist.

### Key Features

- 1.Bayesian Hierarchical Logistic Regression

- 2.94% High Density Interval (HDI)–based decision framework

- 3.Posterior predictive simulation (ppc) for each ball

- 4.Random effects for bowlers + pitch types

- 5.Inference using NUTS sampler (PyMC)

### Model explainability with ArviZ

#### Why Bayesian Modeling?

- Death overs are rare events → small sample size → high uncertainty.
Bayesian modeling quantifies uncertainty, instead of hiding it.

### This project:

- 1.Shows full posterior distribution

- 2.Computes HDI for true wicket-taking ability

- 3.Removes overfitting with partial pooling

- 4.Produces robust decisions for recruitment


### Model Summary
Hierarchical Logistic Model
logit(p) = β₀​ +β (pitch)​+ β(pressure)+ u(bowler​)

Where:

- β₀ → global intercept

- u_bowler → random intercept per bowler

- β_pitch → pitch-level effect

- β_pressure → pressure-level effect

- Posterior sampling: pm.sample() using NUTS
- Posterior predictive: pm.sample_posterior_predictive()

## Final Recommendation (From Model)

## Bowler A has a higher posterior wicket probability in death overs.

##--> The 94% HDI of pressure-effect posterior for Bowler B
does not overlap with that of Bowler A.

- This means:

- Bowler A is more likely to convert pressure into wickets

- Bowler A is a better buy for the "Death Overs Specialist" role

- Bowler B's performance drops under high-pressure, high-leverage situations

###  Visual Outputs

- Trace plots

- HDI intervals for pressure effect

- Posterior predictive wicket curves

- Random effects distribution per bowler

- Bowler comparison using Bayesian decision rule

#### Technologies Used

- 1.PyMC (Bayesian modeling)

- 2.ArviZ (diagnostics + visualization)

- 3.Python

- 4.NumPy / Pandas / Matplotlib / Seaborn

- 5.Jupyter Lab

### Future Improvements

- Add ball-by-ball win probability modeling

- Use Gaussian Process priors for non-linearity

- Include batter quality effects

- Extend model for T20 leagues beyond IPL

- Build a web dashboard (Streamlit) for analysts
