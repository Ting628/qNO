# qNO Research Materials

Selected materials accompanying **qNO: Objective-Informed Ranking and Routing for Qubit Mapping**.

## Data and code availability

The manuscript is currently under peer review. This public repository provides the archived benchmark circuit collection, nominal hardware profiles, experimental result tables, and related documentation.

The complete implementation and evaluation code are not included in this public repository. For confidential access for editorial or peer-review assessment, please contact the journal editorial office to arrange access with the authors.

Other inquiries concerning access to the code may be directed to **jiating.yao@outlook.com**.

## Contents

- `benchmark_inputs/`: the complete archived benchmark-input directory from the previous research package, including 356 QASM circuit files and accompanying documentation/data files.
- `hardware_profiles/`: nominal representative profiles for the four hardware sizes used in the study, with interpretation notes.
- `data/results/`: per-circuit result tables and recorded failures.
- `data/summary/`: derived summary and analysis tables.
- `data/benchmark_manifest.csv`: inventory of the archived benchmark inputs, including file hashes and available upstream information. Inclusion in this input collection does not by itself establish inclusion in every reported experiment; use the experiment result tables to identify the evaluated cases.

Some data-directory notes were written for the broader research package. The scope of the materials distributed here is defined by this README and the files present.

## Hardware profiles

The hardware profiles are fixed nominal representative inputs, not live-device calibration snapshots. Scalar parameters were manually recorded over several days, averaged, and rounded. Exact observation dates, counts, and source snapshots were not retained. These profiles support comparisons under fixed representative inputs and should not be interpreted as reconstructible dated calibrations or current-device performance claims. See `hardware_profiles/README.md` for details.

## Licensing and sources

See `LICENSE` and `THIRD_PARTY_NOTICES.md`. Third-party benchmark circuits retain their upstream licensing conditions; they are not relicensed by the repository's MIT License.
