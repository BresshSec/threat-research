# Full Paper — Case Study 003

The full publication paper is the canonical long-form analysis for this case study.

**Research freeze:** 14 September 2026  
**Closure review:** 15 September 2026  
**Public release update:** 16 September 2026  
**Status:** FINAL / CLOSED

## Public Release

The 43-page Case Study 3 paper has now reached its public-release stage.

The canonical technical release remains:

- `CASE_STUDY_3_BresshSec_PUBLICATION_v1_5_RELEASE.pdf`

For public/social distribution, a separately sanitized edition was prepared on 16 September 2026. The sanitized edition preserves the length and analytical substance of the 43-page paper while reducing unnecessary operational identifiers and victim-sensitive details.

The research itself remains frozen: this publication update does **not** introduce new technical findings or expand claims beyond the established evidence boundary.

## Principal Finding

The principal original observation is state-dependent module delivery within the analyzed BW Panel / ErrTraffic-compatible session: requests associated with the same module key transitioned from substantial active JavaScript responses (~91 KB / ~103 KB) to an explicit 17-byte executable no-op.

This means retrospective replay of a delivery endpoint may not reproduce the content originally observed during the active session.

## Final Evidence Boundary

The public paper and repository preserve the following distinctions:

- the state-dependent active-to-no-op transition is the principal original protocol finding;
- exact server-side gating remains unknown;
- configuration and infrastructure correlations strengthen the broader lineage assessment;
- victim-specific initial access remains unproven;
- valid-account compromise remains an assessed hypothesis, not a confirmed victim fact;
- no specific CVE is claimed as the entry vector for the directly analyzed Italian victims;
- no named threat actor or APT is attributed;
- legitimate websites are treated as victims/compromised infrastructure unless evidence demonstrates otherwise.

## Closure Criterion

The investigation is technically complete at the independent/passive-research stage. Resolving the remaining initial-access question would require primary server-side forensic evidence such as authentication logs, web access logs, WordPress audit records, historical plugin/core inventories, database snapshots or filesystem artifacts.

Absent materially new primary evidence, future information should be published as an **addendum/update** rather than silently modifying the frozen research conclusions.

## Release Artifacts

- `CASE_STUDY_3_BresshSec_PUBLICATION_v1_5_RELEASE.pdf` — canonical frozen technical paper (43 pages)
- Sanitized public/social edition — prepared 16 September 2026 for external distribution

**Publication state:** PAPER RELEASED / CASE CLOSED  
**Research alias:** BresshSec
