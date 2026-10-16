# ReID

Individual re-identification of coelacanths from their spot patterns.

Part of the [Chalumna](https://github.com/Chalumna) organisation.

## Goal

Each coelacanth carries a pattern of white spots on its body that stays stable over many years. This repository explores whether a learned model can match photographs of the same individual, without tagging or touching the animal, and without the manual spot selection that earlier software required.

## Background

Thornycroft & Booth (2012) tested semi-automatic photo-identification on coelacanths filmed off South Africa. Without operator intervention, the software ranked the correct individual first in 56 to 92% of cases, and fish photographed at a yaw angle above 60° were much harder to identify.

These numbers are the baseline this project aims to compare against, using the same kind of evaluation.

## Status

Early stage. There is no model yet, and the repository contains no coelacanth data.

- [ ] Repository skeleton and tooling
- [ ] Evaluation protocol (see below)
- [ ] Data loaders for public datasets of other spotted species
- [ ] Baseline
- [ ] Metric learning models
- [ ] Tests on coelacanth images, only if the data owners agree

## Planned evaluation protocol

- Train and test sets are split by individual: no individual appears in both.
- Left and right flanks are treated as separate identities, as in the 2012 study, so results stay comparable.
- Identification is evaluated in an open-set setting: the model must also say when an individual is not in the reference database.
- Metrics: rank-1 and top-k accuracy, open-set detection, and results reported by yaw-angle range.

## Data

This repository does not contain any coelacanth images or videos. Datasets, images and videos belong to the people and institutions that collected them, and they are used here only with their explicit agreement. See [DATA_POLICY.md](DATA_POLICY.md).

While the work is at the prototype stage, public re-identification datasets of other species are used (to be selected and listed here).

## Repository layout

Target layout, filled in progressively:

```
configs/        experiment configuration
src/            package code (data, models, evaluation)
notebooks/      exploration
scripts/        training and evaluation entry points
tests/          tests folder
docs/           documents folder
data/           ignored by Git
```

## Getting started

Installation and usage instructions will be added with the first working version.

## Contributing

Questions, ideas and suggestions are welcome through issues and discussions on this repository.

## License

The code in this repository is released under the MIT License (see [LICENSE](LICENSE)). The license covers the code only. Data and third-party material are not included and are not covered by it.

## Notes

- This is an independent personal project. It is not affiliated with, or endorsed by, any research programme or institution mentioned on this page.
- Exact sites where coelacanths are observed are never published, to protect the animals.

## References

- Thornycroft R.E. & Booth A.J. (2012). *Computer-aided identification of coelacanths, Latimeria chalumnae, using scale patterns*. Marine Biology Research, 8: 300-306. https://doi.org/10.1080/17451000.2011.628679
