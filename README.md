# Chiral-GW

Numerical and symbolic notebooks for studying bubble collisions, chiral effects, and gravitational-wave spectra in a first-order phase transition setting.

## Layout

- `notebooks/` - Python notebooks for velocity relations, GW spectra, and chirality detectability. Wolfram Mathematica notebooks for analytic estimates and bubble-collision setup.
- `data/cache/gwplot/` - cached spectrum results written by `bubble_coll.ipynb`.
- `data/sensitivity/power-law-integrated_sensitivities/` - detector sensitivity data used by `chirality.ipynb`.
- `external/AlbertoRoper-GW_turbulence/` - bundled reference project and detector sensitivity inputs.
- `figures/` - generated plots and exported PDFs.
- `docs/` - reference documents such as `chiral-gw-proposal.pdf`.

## Main Files

- `notebooks/chirality.ipynb` - GW detectability, magnetic helicity, and chirality plots.
- `notebooks/bubble_coll.ipynb` - two-bubble gravitational-wave spectrum with cache reuse.
- `notebooks/bubble_coll.nb` - Mathematica collision functions and cutoff profiles.

## Requirements

- Python 3.10+ recommended for the Python notebooks
- `numpy`
- `scipy`
- `matplotlib`
- `numba`
- `tqdm`
- Wolfram Mathematica 14.0 or a compatible version for the `.nb` notebooks

## Running

Open the notebooks from their new locations and run them top to bottom.

`bubble_coll.ipynb` will load or regenerate cache files under `data/cache/gwplot/` and export the final spectrum plot to `figures/gw_bubble.pdf`.

`chirality.ipynb` reads detector sensitivity curves from `data/sensitivity/power-law-integrated_sensitivities/` and `external/AlbertoRoper-GW_turbulence/detector_sensitivity/`, then writes its plots into `figures/`.

## Notes

- Generated PDFs and cache files are intentionally kept out of the top level.
- If you add new notebooks, keep them under `notebooks/` and point any output paths to `figures/` or `data/cache/`