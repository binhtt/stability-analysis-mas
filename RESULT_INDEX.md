# Result and source index

All filenames below are relative to their study directory. CSV headers and JSON objects are the authoritative schemas; archived environment metadata records the actual software versions and elapsed times.

| Study | Generator / validator | Raw data / configurations | Summaries |
| --- | --- | --- | --- |
| Main | `baseline/study.py` | `cases.csv`, `configs.json`, `timings.csv`, `baselines.csv` | `resolution_summary.csv`, `timing_summary.csv` |
| Duration | `baseline/extensions.py` | `duration_sensitivity.csv` | `duration_summary.csv` |
| Cache | `baseline/cache_screen.py` | `cache_cases.csv`, `cache_timings.csv` | `cache_summary.csv` |
| Independent seed | `baseline/heldout.py` | `heldout_cases.csv`, `heldout_configs.json` | `heldout_summary.csv`, `heldout_size_summary.csv` |
| Successive versions | `evolution/run_extensions.py` | `sequential.csv`, `sequential_configs.json` | `sequential_summary.csv`, `sequential_ci.csv` |
| Topology and timing | `evolution/run_extensions.py` | `topology_scaling.csv`, `topology_configs.json` | `topology_summary.csv`, `scaling_timing_summary.csv` |
| Cost profiling | `evolution/run_extensions.py` | `cost_profile.csv` | `profile_summary.csv` |
| Boundary guards | `evolution/numerical_audit.py` | `guard_sweep.csv`, `numerical_models.json`, `near_boundary_intervals.json` | `guard_summary.csv` |
| Independent interval exponentials | `evolution/independent_interval_expm.py` | `independent_interval_expm.json` | Individual check records |
| Cache intervals | `evolution/validate_cache.py` | `cache_interval_configs.json`, `cache_interval_checks.json` | Individual check records |
| Initial preprocessing | `evolution/profile_initialization.py` | `initialization_profile.csv` | Separate reconstruction timing |

Run the top-level reproduction driver from the repository root. It changes to the correct directory for each script. Running a study script directly requires its own study directory as the working directory.

`numerical_design.json` and `design.json` document fixed numerical targets and generation seeds. `extensions_metadata.json`, `numerical_metadata.json`, and baseline metadata describe recorded environments. Historical source hashes in metadata describe the original scientific runs; `MANIFEST.sha256` describes this packaged distribution, whose reporting scripts have been edited to remove manuscript generation.
