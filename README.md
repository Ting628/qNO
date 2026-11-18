# qNO Research Materials

Selected materials accompanying **qNO: Objective-Informed Ranking and Routing for Qubit Mapping**.

## Data and code availability

This public repository provides the archived benchmark circuit collection, nominal hardware profiles, experimental result tables, representative mapped-circuit examples, and related documentation.

The complete implementation and evaluation code are not included in this public repository. For confidential access for editorial or peer-review assessment, please contact the journal editorial office to arrange access with the authors.

Other inquiries concerning access to the code may be directed to **jiating.yao@outlook.com**.

## Contents

- `benchmark_inputs/`: the complete archived benchmark-input directory from the previous research package, including 356 QASM circuit files and accompanying documentation/data files.
- `hardware_profiles/`: nominal representative profiles for the four hardware sizes used in the study, with interpretation notes.
- `examples/minimal/`: archived mapped-circuit and evaluation-output examples for `bv_n14`, `multiplier_n15`, and `dnn_n51`.
- `data/results/`: per-circuit result tables and recorded failures.
- `data/summary/`: derived summary and analysis tables.
- `data/benchmark_manifest.csv`: inventory of the archived benchmark inputs, including file hashes and available upstream information. Inclusion in this input collection does not by itself establish inclusion in every reported experiment; use the experiment result tables to identify the evaluated cases.

Some data-directory notes were written for the broader research package. The scope of the materials distributed here is defined by this README and the files present.

## Example outputs

The `examples/minimal/` directory contains three archived qNO output examples:

| Example | Hardware profile | Input circuit |
|---|---|---|
| `bv_n14` | `hardware_profiles/Garnet.layout` (20 qubits) | `benchmark_inputs/qasm/circuit20/bv_n14_transpiled.qasm` |
| `multiplier_n15` | `hardware_profiles/Garnet.layout` (20 qubits) | `benchmark_inputs/qasm/circuit20/multiplier_n15_transpiled.qasm` |
| `dnn_n51` | `hardware_profiles/iqm_emerald.layout` (54 qubits) | `benchmark_inputs/qasm/circuit54/dnn_n51_transpiled.qasm` |

Each example folder contains:

- `mapped_circuit.qasm`: the mapped output circuit.
- `hardware_native.qasm`: the circuit expressed in the hardware-native basis used for evaluation.
- `layout.txt`: initial and final logical-to-physical layouts and the routing permutation. This mapping record is distinct from the hardware topology and parameter profiles in `hardware_profiles/`.
- `*_qNO_ot_results.json`: archived evaluation output, including the basis policy, timing units, and ASAP/ALAP gate counts, depths, OT values, and success-proxy quantities.

The examples are supplied as input/output records for inspection. The implementation and evaluator needed to regenerate them are subject to the code-access arrangement described above. Absolute Windows paths in the JSON `source` fields record the original evaluation environment; they are provenance metadata, not paths expected to exist on a reader's computer.

## Hardware profiles

The hardware profiles are fixed nominal representative inputs, not live-device calibration snapshots. Scalar parameters were manually recorded over several days, averaged, and rounded. Exact observation dates, counts, and source snapshots were not retained. These profiles support comparisons under fixed representative inputs and should not be interpreted as reconstructible dated calibrations or current-device performance claims. See `hardware_profiles/README.md` for details.

## Licensing and sources

See `LICENSE` and `THIRD_PARTY_NOTICES.md`. Third-party benchmark circuits retain their upstream licensing conditions; they are not relicensed by the repository's MIT License.
