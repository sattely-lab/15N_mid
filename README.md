## Introduction
`15N_mid` is a repository for some crude scripts and Jupyter notebooks that we use to quantify 15N incorporation into nitrogenous metabolites from measurements made by high-resolution mass spectrometry.

## Contents

This repo contains:

1. `get_MID_15N.py` 
  This is a Python script that relies on the [`pyteomics`](https://pypi.org/project/pyteomics/) package to parse `*.mzML` files.  It takes in an ion structure (or _m_/_z_), a retention time window, an `*.mzML` file, and a bound on the number of distinct mass isotopomers to include in the output.  It extracts the mass isotopomer distribution (or perhaps more correctly, the mass isotopologue distribution) for the provided ion from the provided file.  It assumes that: (a) isotopic "fine structure" is not resolved, e.g. 13C14N cyanide and 12C15N cyanide both contribute to the intensity of an "M1" isotopologue; and (b) that carbon and nitrogen are the only elements for which there is appreciable abundance of non-standard isotopes.  This script is a very lightly modified version of a similar script available at `https://github.com/Stanford-ChEMH-MCAC/d2o_metabolomics/blob/master/get_MID.py` and reported in [Nett et al. 2018](https://aiche.onlinelibrary.wiley.com/doi/abs/10.1002/aic.16413).
  
2. `fit_isotopic_abundance_to_MID_FULL.ipynb`
  This is a Jupyter notebook that calls on `get_MID_15N.py` to analyze some phytoene labeling patterns in an experiment done by Tim S.
  
3. `mid_files`
  This directory contains the `*.csv`-formatted outputs of `get_MID_15N.py` run on samples from the afforementioned labeling experiment.
  
4. `mzml_files`
  This directory contains the raw `*.mzML` files obtained by converting Agilent `*.d` files recorded by the mass spectrometer to `*.mzML` files using msconvert.
  
## CAUTION

We are publishing this repository in the interest of transparency, *not* because we think this code is a well-maintained, easy to use, install, or easy to install.  

## Authorship and License

This code is by Curt R. Fischer.  This repository is licensed with the MIT license.

