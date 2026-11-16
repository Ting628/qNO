# Hardware Topology and Evaluation Profiles

The supplied machine-readable profiles are:

- `Garnet.layout`: 20Q IQM Garnet-like square lattice;
- `iqm_emerald.layout`: 54Q IQM Emerald-like square lattice;
- `ibm_strasbourg.layout`: 127Q IBM Strasbourg-like heavy-hex topology;
- `topo_433.layout`: 433Q IBM Osprey-like heavy-hex topology.

Before public release, verify and document for each profile:

- qubit count and coupling edges;
- directed/undirected interpretation;
- native gate set;
- one- and two-qubit gate durations;
- two-qubit error or fidelity parameter;
- effective coherence parameter;
- measurement/reset assumptions if used;
- source, access date, calibration snapshot, or explanation that the profile is synthetic/representative;
- units and parser format.

The paper's topology drawings are explanatory figures and do not substitute for these files.

<!-- BEGIN NOMINAL HARDWARE PROFILE PROVENANCE -->
## Status and provenance of the hardware profiles

The four `.layout` files in this directory are **nominal representative profiles** used to make the routing experiments reproducible. Their scalar timing, fidelity, and coherence values were manually recorded over several days from the official Amazon Braket device information for IQM Garnet and IQM Emerald and the IBM Quantum Platform for IBM Strasbourg and IBM Osprey, then averaged and rounded to the precision shown below. They are not exports of a live backend, device certificates, or reproducible dated calibration snapshots.

| Layout file | Nominal class | Qubits | 1Q duration | 2Q duration | Nominal 2Q fidelity | Nominal coherence time |
|---|---:|---:|---:|---:|---:|---:|
| `Garnet.layout` | square-lattice | 20 | 40 ns | 60 ns | 99.3% | 10 us |
| `iqm_emerald.layout` | square-lattice | 54 | 40 ns | 60 ns | 99.5% | 20 us |
| `ibm_strasbourg.layout` | heavy-hex | 127 | 60 ns | 600 ns | 99.0% | 110 us |
| `topo_433.layout` | heavy-hex | 433 | 60 ns | 600 ns | 99.0% | 150 us |

### Construction rules

- **Topology and size.** Each connectivity graph is a fixed representative graph for the stated hardware class and qubit count. It is used as an experimental input rather than as a claim about currently available hardware.
- **Gate durations.** The 1Q and 2Q durations are rounded multi-day representative values and are applied uniformly within each profile unless a layout entry explicitly overrides them.
- **Fidelity/error.** The reported two-qubit fidelity is the rounded representative value. When an error probability is required, the conversion is `p_2q = 1 - F_2q`.
- **Effective coherence.** The recorded multi-day representative coherence value is used directly as the profile-level `T2_eff` input. The dimensionless routing proxy is computed as `T2_eff / t_2q` after conversion to consistent time units.
- **Aggregation.** The author-recorded values from several observation days were combined by averaging and then rounded. The exact observation count and the within-day qubit/edge aggregation shown by the platforms were not retained, so the profiles must not be treated as independently reconstructible calibration aggregates.
- **Access dates and raw records.** The exact observation dates, original screenshots, and machine-readable property snapshots were not retained. This limitation is stated explicitly rather than replacing the missing provenance with inferred dates.

Consequently, results obtained with these files should be interpreted as comparisons under controlled nominal hardware classes. They must not be presented as predictions for the current performance of the named commercial systems. Future calibration-based experiments should archive the provider response, backend identifier, retrieval timestamp, raw property file, and aggregation rule.
<!-- END NOMINAL HARDWARE PROFILE PROVENANCE -->


