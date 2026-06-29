# Data Management (MSCF infrastructure)

The storage and compute half of a Data Management Plan, the part about where data lives and how it is handled on MSCF/TACC. The researcher still provides the data-specific parts (types, formats, metadata standards, and the repository used for sharing).

## What this covers

- **Storage during the project:** TACC Vista. `$HOME` (backed up, for scripts), `$WORK` (durable working space), `$SCRATCH` (large-scale, purged after inactivity, for active jobs and big datasets). `[REFINE: exact quotas and purge policy]`
- **Transfer:** moving data in and out through Tapis, and Globus for large transfers.
- **Access and security:** TACC account with multi-factor authentication; access under allocation TRA25001. `[REFINE: allocation framing]`
- **Backup and retention:** what is backed up versus purged; long-term preservation and public sharing happen in a domain repository chosen by the researcher, not on scratch.

## Draft paragraph

> During the award, data and computation will be hosted on TACC's Vista system, accessed through the Morehouse Tapis tenant under allocation TRA25001. Active datasets reside in `$WORK` (durable) and `$SCRATCH` (large-scale, for running jobs); code and configuration are kept in the backed-up `$HOME`. Transfers use Tapis and Globus, and access requires a TACC account with multi-factor authentication. `[REFINE]`

## The researcher still provides

- Data types and expected volume.
- Formats and metadata standards for the field.
- The public repository and timeline for sharing.
- Any privacy, consent, or IRB constraints.

> DRAFT.
