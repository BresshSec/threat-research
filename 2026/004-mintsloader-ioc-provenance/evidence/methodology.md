# Methodology

## Evidence hierarchy

1. Primary incident reporting and official IOC exports.
2. Technical vendor research containing reproducible behaviors or code characteristics.
3. Official package manifests and historical distribution records.
4. Public sandbox reports with a preserved analysis identifier and timestamp.
5. Search-index results used only for discovery, never as sole proof.

## Confidence model

- High: directly observable in a primary source or supported by independent records that establish the same fact.
- Moderate: several specific traits or overlaps support the relationship, but one material artifact or ownership fact is missing.
- Low: plausible lead with one observation or an unreproducible record.

## IOC handling

Every indicator is assigned to one of three files. `confirmed.csv` contains values directly supported by a cited campaign source. `correlations.csv` contains relationships that require analytical judgment. `excluded-or-noisy.csv` contains values with a documented alternative explanation or inadequate campaign context.

## Negative searches

Failure to retrieve an exact string from public search, a repository, or a feed is recorded as “not found in the examined public sources.” It is not converted into a claim that the value is globally absent or newly discovered.

## Reproducibility

Each material conclusion cites a stable public page, JSON export, package record, or sandbox analysis ID. Claims that depend on unavailable private telemetry are stated as limitations.
