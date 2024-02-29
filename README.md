# CosmoExplorer: DESC SprintDayWinter2024 Event

CosmoExplorer is an **in-development** data sharing platform hosted at the Argonne National Laboratory. The application leverages Globus Compute and Transfer to run queries and predefined analysis scripts on our simulation data products, **using compute resources at the Argonne Leadership Computing Facility**


## Links
- HACC Compute Portal: [https://cosmoexplorer.alcf.anl.gov](https://cosmoexplorer.alcf.anl.gov)

## Available Datasets

### Gravity-Only Simulations
We provide data from 8 snapshots (ranging from z=0 to z=2) of the following simulations:
- **LastJourney:**
- **LastJourneySV:**

### Hydro Simulations:
We provide data from 8 snapshots (ranging from z=0 to z=2) of the following simulations:
- **SCIDAC_T001:**
- **SCIDAC_T002:**
- **SCIDAC_T003:**

## Caveats and known issues
- **This platform is in an early development stage**, so expect things to fail and be patient :). If you run into issues, please report them (see below), this will help us to improve the application.
- **halo-particle queries:** The query will fail if the halo cannot be found (invalid `fof_halo_tag`) or if the halo is below the particle-output mass threshold listed above. Currently, there is no "nice" error message; instead, you'll have to open the flow in Globus and look at the event details.

## Reporting Issues
If you find an issue or error not listed above, please let us know on Slack, or by sending an email to Patricia Larsen or Michael Buehlmann.
- if the run failed, please **check the error logs on Globus** by clicking `Open in Globus` -> `Event Log`. Expand the failed action and copy the content in your error report.
- **include the run UUID** and the query type in your report. That helps us to find the log files on the Argonne machines.


## Acknowledgements
