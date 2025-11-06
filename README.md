# Natural Gas Forward Curve — Spline Interpolation & On-Date Price Lookup

## Overview
This notebook fits a smooth forward curve for Natural Gas prices using `UnivariateSpline` and exposes a callable to retrieve price for any given date. It demonstrates curve fitting, date handling, and quick visualization.

## Data
- **Input:** `Nat_Gas.csv` with columns like `Dates` (MM/DD/YY) and `Price`.
- Sorts by date, converts to datetime, and builds a numeric index for spline.

## Methods
- Spline-based curve fitting (`scipy.interpolate.UnivariateSpline`)
- On-date price lookup function, e.g. `get_price('2025-03-31')`
- Basic plots to visualize the fitted curve vs. historical points

## Results
- Smooth curve across given dates
- Quick lookup for interpolated price on specific dates

## Notes & Limitations
- Interpolation is reliable between known dates; extrapolation beyond data range is risky.
- Consider walk-forward backtesting to quantify error before using for decisions.

## What can make this better..
- Add time-split backtesting (MAE/MAPE/RMSE)
- Parameter tuning for spline smoothing and knots
- Export a small `get_price.py` utility for reuse
