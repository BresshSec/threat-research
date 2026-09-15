# Full Paper — Case Study 003

The full publication paper is the canonical long-form analysis for this case study.

**Frozen public release:** v1.5  
**Research freeze:** 14 September 2026  
**Final closure review:** 15 September 2026  
**Status:** FINAL / CLOSED

The v1.5 PDF remains the frozen long-form publication artifact. The repository-level closure review performed on 15 September adds stronger external correlation and an updated initial-access assessment without changing the evidence boundary of the paper.

## Final Evidence Boundary

The public paper and repository should preserve the following distinctions:

- the state-dependent active-to-no-op transition is the principal original protocol finding;
- exact server-side gating remains unknown;
- exact configuration and infrastructure correlations strengthen the broader lineage assessment;
- victim-specific initial access remains unproven;
- valid-account compromise is the leading assessed initial-access hypothesis, not a confirmed victim fact;
- no specific CVE is claimed as the entry vector for the directly analyzed Italian victims;
- no named threat actor or APT is attributed;
- legitimate websites are treated as victims/compromised infrastructure unless evidence demonstrates otherwise.

## Closure Criterion

The investigation is considered technically complete at the independent/passive-research stage. Resolving the remaining initial-access question would require primary server-side forensic evidence such as authentication logs, web access logs, WordPress audit records, historical plugin/core inventories, database snapshots or filesystem artifacts.

Absent such new primary evidence, further passive pivoting is unlikely to materially change the publication-grade conclusions and risks adding correlation without increasing evidentiary strength.

## Release Artifact

- `CASE_STUDY_3_BresshSec_PUBLICATION_v1_5_RELEASE.pdf` — frozen public paper

Future changes should be treated as a new revision only if materially new primary evidence becomes available.
