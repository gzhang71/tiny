# Causal inference vs. A/B testing

Both answer the same question — *what is the causal effect of X on Y?* — but under different constraints.

## Rule of thumb

**If you can randomize, randomize.** An A/B test (randomized controlled trial) removes confounding by design: randomization makes treatment independent of everything else, observed or not. Observational causal inference methods exist for when you *can't* randomize, and they all rely on assumptions you cannot fully verify.

## When A/B testing doesn't work

- **Infeasible or unethical to randomize** — you can't randomly assign users to churn, or patients to smoking.
- **The decision already happened** — you have historical data and need an answer now.
- **Interference / network effects** — treated units affect control units (marketplaces, social networks), breaking the standard RCT assumptions.
- **Long horizons** — the outcome takes months or years; an experiment is too slow.

## The observational toolbox (see tiny_causal_inference)

| Method | Key assumption |
|---|---|
| Propensity score matching / weighting | No unmeasured confounders (all confounders observed) |
| Difference-in-differences | Parallel trends between groups absent treatment |
| Instrumental variables | Instrument affects outcome only through treatment |
| Regression discontinuity | Units just above/below a cutoff are comparable |
| Synthetic control | Donor pool can reconstruct the counterfactual |

The price of skipping randomization is that each method trades the RCT's design guarantee for an untestable assumption. Sensitivity analysis — asking "how strong would an unmeasured confounder have to be to overturn this result?" — is how you stress-test that trade.

## They compose

In practice the two are complementary: use observational methods to size an opportunity and generate hypotheses, then confirm the ones that matter with an experiment. And experiments themselves borrow observational machinery — e.g., instrumental variables to handle non-compliance, regression adjustment (CUPED) for variance reduction.
