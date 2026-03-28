# Bayesian Proof-of-Concept Trial Design

> Course project: Foundations of Bayesian Methodology (Spring 2024) · University of Zurich · Malgorzata Roos, PD Dr.

Bayesian analysis of a Phase 2 clinical trial evaluating the efficacy of 
Secukinumab (anti-IL-17A) versus placebo in patients with ankylosing spondylitis.

## Overview

This project covers the full pipeline of a Bayesian clinical trial analysis:

- **Prior elicitation**: Random-effects meta-analysis of 8 historical placebo studies using MCMC (JAGS) to derive a predictive placebo response distribution
- **Sample size calculation**: Simulation-based approach targeting >90% Proof of Concept (POC) under a 4:1 treatment-to-placebo allocation
- **Prior specification**: Beta-Binomial conjugate priors (informative for placebo, conservative for treatment)
- **Posterior updating**: Conjugate Beta posteriors after observing trial data
- **Decision criterion**: Posterior Probability of Superiority (PPS = 99.7%) exceeding the pre-defined 95% threshold

## Results

| Group | n | Responders | Posterior Response Rate | Difference S-P | 95% CrI | PPS | MCse(PPS) |
|---|---|---|---|---|---|---|---|
| Secukinumab | 23 | 14 (60.9%) | 59.2% | 34.7% | 11.8–56.1% | 99.7% | 0.0017 |
| Placebo | 6 | 1 (16.7%) | 24.5% | — | — | — | — |

The PPS of 99.7% exceeds the pre-defined 95% threshold, with MCse = 0.0017. 
Even at the conservative estimate (PPS − 3×MCse = 99.2%), we remain well above 
the threshold, providing strong evidence that Secukinumab is superior to placebo.

## Tools

- R, JAGS, rjags, coda
