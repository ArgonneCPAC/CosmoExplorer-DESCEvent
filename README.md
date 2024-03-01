# CosmoExplorer: DESC SprintDayWinter2024 Event

CosmoExplorer is an **in-development** data sharing platform hosted at the Argonne National Laboratory. The application leverages Globus Compute and Transfer to run queries and predefined analysis scripts on our simulation data products, **using compute resources at the Argonne Leadership Computing Facility**


## Getting Access
- You need to have a Globus account. Send us your account email and we'll add it to the correct Globus group.
- You will get an email that you have been invited to the Globus group. **You need to accept the invitation prior to accessing our page, otherwise the login will be denied!**
- HACC Compute Portal: [https://cosmoexplorer.alcf.anl.gov](https://cosmoexplorer.alcf.anl.gov)

## Available Datasets

All simulations use a Planck cosmology with parameters $h= 0.6766$, $\Omega_\text{CDM}=0.261$, $\Omega_b=0.049$, $\sigma_8=0.8102$, and $n_s=0.9665$.
### 1. Gravity-Only Simulations
We provide data from 8 snapshots (ranging from z=0 to z=2) of the following simulations:
- **LastJourney:** $10752^3$ particles in a $(3400 h^{-1}\mathrm{Mpc})^3$ box, $m_p = 2.7174 \times 10^9$ $h^{-1}M_\odot$.
- **LastJourneySV:** small-volume version of the Last Journey simulation: $1024^3$ particles in a $(250 h^{-1}\mathrm{Mpc})^3$ box, $m_p = 1.2506 \times 10^9$ $h^{-1}M_\odot$.

> [!NOTE]
Queries outside the following mass ranges  will most likely not return any results:
> - LastJourney: $M \in [10^{11}, 10^{16}]h^{-1}M_\odot$
> - LastJourneySV: $M \in [10^{11}, 10^{15}]h^{-1}M_\odot$

### 2. Hydro Simulations:
We provide data from 8 snapshots (ranging from z=0 to z=2) of three simulations run from the same intial conditions, but with different subgrid model parameters: **SCIDAC_T001**, **SCIDAC_T002**, and **SCIDAC_T003**.

The three simulations cover a (128 $h^{-1} \mathrm{Mpc})^3$ volume with $2 \times 512^3$ particles. The particle masses are $1.13 \times 10^9$ $h^{-1}M_\odot$ for DM and $\sim2 \times 10^8$ $h^{-1}M_\odot$ for primordial gas.

> [!NOTE]
Queries outside the following mass ranges  will most likely not return any results:
> - $M_{200c} \in [10^{11}, 6 \times 10^{14}]h^{-1}M_\odot$
> - $M_{500c} \in [10^{11}, 4 \times 10^{14}]h^{-1}M_\odot$
> - $R_{200c} \in [0.05, 1.4]h^{-1}\mathrm{Mpc}$


#### Subgrid Parameters:
- **FSN:** Fractional supernova energy that is converted to wind
- **VEL:** Supernova wind velocity [km/s]
- **TEXP:** AGN Feedback Energy ($\Delta_T 10^\mathrm{TEXP}$ K)
- **BETA:** Bondi equation boost factor $\dot{M}_\mathrm{Bondi} \propto (n_H/\bar{n}_H)^\beta$

| Simulation | FSN   | VEL     | TEXP | BETA   |
|------------|-------|---------|------|--------|
| T001       | 0.4710| 165.577 | 9.710| 0.2613 |
| T002       | 0.5613| 250.611 | 10.00| 0.6968 |
| T003       | 0.6968| 341.979 | 8.694| 0.0581 |

> [!IMPORTANT]
> These simulations are provided for demonstration purposes. Don't use them outside of this demo.

## How to read / use the data
**Florian Keruzore provided this excellent [Python Notebook](https://nbviewer.org/github/ArgonneCPAC/CosmoExplorer-DESCEvent/blob/main/data_manipulation_examples.ipynb)** that describes the data contained in the HDF5 files. It also includes some amazing post-processing examples!

## Caveats and known issues
- **This platform is in an early development stage**, so expect things to fail and be patient :). If you run into issues, please report them (see below), this will help us to improve the application.
- **error messages:** errors that occur during the run **are not cleanly forwarded to the webpage** at the moment. Open the flow on Globus to see more info, and ask us; we can look up the exact error and let you know.
- **halo-particle queries:** The query will fail if the halo cannot be found (invalid `fof_halo_tag`) or if the halo is below the particle-output mass threshold listed above. Currently, there is no "nice" error message; instead, you'll have to open the flow in Globus and look at the event details.

## Reporting Issues
If you find an issue or error not listed above, please let us know on Slack, or by sending an email to Patricia Larsen or Michael Buehlmann.
- if the run failed, please **check the error logs on Globus** by clicking `Open in Globus` -> `Event Log`. Expand the failed action and copy the content in your error report.
- **include the run UUID** and the query type in your report. That helps us to find the log files on the Argonne machines.


## Acknowledgements
This project is using resources of the Argonne Leadership Computing Facility, which is a DOE Office of Science User Facility supported under Contract DE-AC02-06CH11357. The work at Argonne National Laboratory is supported under the U.S. DOE contract DE-AC02-06CH11357.