# Dynamic Credit Risk and Loan Pricing Using Interest-Rate Monte Carlo Simulation

## Introduction

Credit risk modeling is traditionally centered on estimating the probability that a borrower will default and the resulting financial loss. Key measures such as **Probability of Default (PD)**, **Loss Given Default (LGD)**, and **Exposure at Default (EAD)** provide a foundation for estimating expected credit losses. However, a loan portfolio is exposed to more than borrower-specific characteristics. Changes in the broader interest-rate environment can affect funding costs, loan payments, borrower affordability, default probabilities, and ultimately the profitability of lending products.

This project develops a **Monte Carlo-based credit-risk and loan-pricing framework** that combines machine learning, stochastic interest-rate modeling, and portfolio loss simulation. Synthetic loan data are first generated to represent borrower characteristics such as income, credit score, debt-to-income ratio, loan amount, and maturity. A logistic regression model is then used to estimate borrower-level Probability of Default (PD).

To incorporate uncertainty in future interest rates, the project uses the **Vasicek interest-rate model**, a stochastic process that represents interest rates through mean reversion and random shocks:

$$
dr_t = \kappa(\theta-r_t)\,dt+\sigma\,dW_t
$$

The simulated interest-rate scenarios are then connected to borrower credit risk. Higher interest rates can increase debt-service burdens and potentially increase the probability of default. Monte Carlo simulation is subsequently used to generate thousands of possible portfolio outcomes by simultaneously considering default events, stochastic LGD, loan exposure, and different interest-rate environments.

The resulting simulations produce a **distribution of potential portfolio credit losses**, rather than a single expected-loss estimate. From this distribution, the project calculates metrics such as **Expected Loss, Value at Risk (VaR), and Expected Shortfall**.

Finally, the framework connects credit risk to loan-product pricing. Different loan interest rates are evaluated by considering the trade-off between interest income, funding costs, and expected credit losses. This demonstrates how quantitative risk modeling can support questions such as:

**How might changes in interest rates affect borrower default risk, portfolio losses, and the economics of a loan product?**

## Project Objectives

The main objectives are to:

* Build a borrower-level Probability of Default model.
* Simulate future interest-rate paths using the Vasicek model.
* Incorporate interest-rate scenarios into dynamic credit risk.
* Simulate stochastic PD, LGD, and EAD.
* Generate a Monte Carlo distribution of portfolio credit losses.
* Calculate Expected Loss, VaR, and Expected Shortfall.
* Examine the relationship between interest rates and credit losses.
* Evaluate the potential profitability of different loan interest-rate assumptions.
* Demonstrate how machine learning and mathematical finance can be combined in credit-risk analytics.

## Conceptual Framework

The overall framework can be summarized as:

$$
\boxed{
\text{Borrower Characteristics}
\rightarrow
\text{PD Model}
\rightarrow
\text{Interest-Rate Scenarios}
\rightarrow
\text{Monte Carlo Simulation}
\rightarrow
\text{Credit Loss Distribution}
\rightarrow
\text{Loan Pricing Analysis}
}
$$

This project is intended as an **educational MVP rather than a production banking model**. The portfolio data and several relationships are simulated for demonstration purposes. In a production environment, the framework would require historical loan-performance data, validated macroeconomic relationships, calibrated interest-rate models, default-correlation modeling, rigorous model validation, and appropriate regulatory and governance controls.

## Possible Extensions

1. **Use Real Loan Data**

   Replace synthetic data with historical loan-performance data and perform out-of-time validation.

2. **Dynamic PD & Macroeconomic Modeling**

   Model PD as a function of borrower characteristics, interest rates, GDP, inflation, unemployment, and other economic variables:


3. **Advanced Interest-Rate & Monte Carlo Models**

   Compare Vasicek with CIR or Hull--White and simulate correlated interest-rate and default scenarios.

4. **Stochastic LGD & EAD**

   Allow LGD and EAD to change according to collateral values, borrower behavior, economic conditions, and utilization.
