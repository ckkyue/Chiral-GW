# Chiral-GW

Numerical and symbolic notebooks for studying bubble collisions, chiral effects, and gravitational-wave spectra in a first-order phase transition setting.

The repository mixes Python notebooks and Wolfram Mathematica notebooks:

- `fluid_velocity.ipynb` explores velocity relations across a phase boundary and includes a simple 3D velocity-field visualization.
- `gwplot.ipynb` computes a two-bubble gravitational-wave spectrum, caches expensive runs to `.pkl` files, and saves the main figure to `Figure/gwplot_twobubble.png`.
- `chiral_estimate.nb` performs a Mathematica-based estimate of chiral/gravitational-wave related quantities from phase-transition parameters.
- `gw_bubble_coll.nb` contains Mathematica calculations for bubble-collision setup functions such as cutoff profiles and excluded-angle behavior.

## Repository Layout

- `Figure/` - generated plots and figures.
- `gwscaled_*.pkl` - cached spectrum results produced by `gwplot.ipynb`.
- `chiral-gw-proposal.pdf` - supporting proposal or reference document.
- `Chiral-GW.code-workspace` - VS Code workspace configuration.

## Requirements

Python notebook:

- Python 3.10+ recommended
- `numpy`
- `scipy`
- `matplotlib`
- `numba`
- `tqdm`

Mathematica notebooks:

- Wolfram Mathematica 14.0 or a compatible version with support for legacy packages used in the notebooks.

## How To Run

For the Python notebook, open `fluid_velocity.ipynb` or `gwplot.ipynb` in Jupyter or VS Code and run the cells top to bottom.

The `gwplot.ipynb` notebook will:

1. Build a frequency grid and compute the spectrum for different CP-violating phases.
2. Reuse cached results from `gwscaled_*.pkl` when the parameters match.
3. Write the final plot to `Figure/gwplot_twobubble.png`.

For the Mathematica notebooks, open the `.nb` files in Wolfram Mathematica and evaluate the cells in order.

## Notes

- The cache files are generated artifacts. If you delete them, `gwplot.ipynb` will recompute the spectra and recreate the cache.
- The notebooks are parameterized around a bubble wall velocity near `vW = 0.9`, a separation scale `d`, and electroweak-scale inputs around `T = 100 GeV`.
- If you want a cleaner release snapshot, you can remove generated caches and regenerate the figure from `gwplot.ipynb`.