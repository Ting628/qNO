# qNO Research Materials

Selected materials accompanying **qNO: Objective-Informed Ranking and Routing for Qubit Mapping**.

## Data and code availability

The manuscript is currently under peer review. This public repository provides selected benchmark circuits, nominal hardware profiles, experimental result tables, and related documentation.

The complete implementation and evaluation code are not included in this public repository. For confidential access for editorial or peer-review assessment, please contact the journal editorial office to arrange access with the authors.

Other inquiries concerning access to the code may be directed to **jiating.yao@outlook.com**.

## Contents

- `benchmark_inputs/`: three selected QASM input circuits (bv_n14, multiplier_n15, and dnn_n51); this is a sample, not the full benchmark input collection.
- `hardware_profiles/`: nominal representative profiles for the four hardware sizes used in the study, with interpretation notes.
- `data/results/`: per-circuit result tables and recorded failures.
- `data/summary/`: derived summary and analysis tables.
- `data/benchmark_manifest.csv`: reference inventory of the broader benchmark collection. Most inventory entries are not distributed in this selected-circuit repository.

Some data-directory notes were written for the broader research package. The scope of the materials distributed here is defined by this README and the files present.

## Hardware profiles

The hardware profiles are fixed nominal representative inputs, not live-device calibration snapshots. Scalar parameters were manually recorded over several days, averaged, and rounded. Exact observation dates, counts, and source snapshots were not retained. These profiles support comparisons under fixed representative inputs and should not be interpreted as reconstructible dated calibrations or current-device performance claims. See `hardware_profiles/README.md` for details.

## Licensing and sources

See `LICENSE` and `THIRD_PARTY_NOTICES.md`. Third-party benchmark circuits retain their upstream licensing conditions; they are not relicensed by the repository's MIT License.
