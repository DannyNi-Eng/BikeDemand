# Project plan

**Status: Planned.** No modeling or evaluation has been completed.

## Research objective

Forecast hourly bike-sharing demand from the UCI Seoul Bike Sharing Demand dataset. Compare how model architecture, forecast horizon, and historical lookback affect predictive accuracy.

## Planned configurations

Two architectures (MLP and GRU) × two horizons (next hour and next 24 individual hours) × two lookbacks (48 and 168 hours) = eight primary neural network configurations. The 24-hour target is a vector of 24 hourly predictions, not one daily aggregate.

## Planned evaluation

- Use chronological training, validation, and test periods to avoid future information entering earlier predictions.
- Develop and document feature engineering using only information available at forecast time.
- Account for non-functioning service periods with masked losses and corresponding evaluation masks, with the masking rule documented before training.
- Compare configurations on held-out time periods using suitable per-hour error metrics and, for 24-hour forecasts, report error by forecast lead as well as overall error.
- Keep reusable training and evaluation code, record experimental settings, and save small figures under `results/figures/`.

Metric definitions, split boundaries, baselines, and tuning rules will be specified before experiments. No results are claimed here.

## Milestones

1. Set up environment and public repository scaffold. **Current stage.**
2. Obtain and inspect the dataset; document its source and license or terms.
3. Define chronological splits, features, targets, and masking rules.
4. Implement data loading and the eight planned model configurations.
5. Implement reusable training, validation, and evaluation workflows.
6. Run controlled experiments and summarize results with limitations.
7. Prepare portfolio documentation and publish the repository.
