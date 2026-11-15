# Learning Pythia with the LHC $gg \rightarrow t \bar{t} $ simulations

A learning notebook following Sections 3 to 5 of the [PYTHIA 8.3 Worksheet](https://www.pythia.org/pdfdoc/worksheet8312.pdf), written with the PYTHIA Python interface.

## What it covers

1. **Hello world:** generate a single $gg \to t\bar t$ event at 13 TeV and read the event record.
2. **Event loop:** generate 1000 events (mix of $gg \to t\bar t$ and $q\bar q \to t\bar t$), find the last top-quark copy, and histogram its transverse momentum $p_T$ and pseudorapidity $\eta$.
3. **Charged multiplicity:** compare the number of charged final-state particles with final-state radiation (FSR), initial-state radiation (ISR) or multiparton interactions (MPI) switched off one at a time.

The notebook also answers the worksheet's questions on the shape of the $p_T$ and $\eta$ distributions.

## Results (1000 events per setup, fixed seed)

| Setup  | Mean charged multiplicity | Std  | Error on mean |
|--------|--------------------------:|-----:|--------------:|
| all on | 252.5 | 80.6 | 2.55 |
| no FSR | 196.4 | 66.7 | 2.11 |
| no ISR | 159.1 | 54.0 | 1.71 |
| no MPI | 127.3 | 29.2 | 0.92 |

- Mean top $p_T$ in the loop sample: 127.4 GeV.
- Switching off MPI has the largest effect on both the mean and the width of the distribution.
- All differences are much larger than the error on the mean.

## Requirements

- Python 3.9+
- PYTHIA 8.3 Python bindings, either:
  - `conda install -c conda-forge pythia8`, or
  - `pip install pythia8mc`
- `numpy`, `matplotlib`, `jupyter`

The notebook was run with PYTHIA 8.312.


Event generation is done in a Python loop, so the 1000-event runs take a few minutes in total. Lower `N_EVENTS` and `N` in the notebook for a quick test.

## References

- Worksheet: <https://www.pythia.org/pdfdoc/worksheet8312.pdf>
- C. Bierlich et al., *A comprehensive guide to the physics and usage of PYTHIA 8.3*, SciPost Phys. Codebases 8 (2022), [arXiv:2203.11601](https://arxiv.org/abs/2203.11601)
