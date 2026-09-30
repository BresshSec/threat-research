# Case Study 004 - MintsLoader Infrastructure and IOC Provenance

**Research date:** 30 September 2026  
**Researcher:** BresshSec  
**Status:** CERT REVIEW / PUBLICATION READY  
**Focus:** MintsLoader - Operation GhostWallet - infrastructure correlation - IOC provenance

## Executive Summary

This case study examines whether the June 2026 Operation GhostWallet delivery chain can be associated with MintsLoader and reviews the provenance of indicators published for the 24 September 2026 CERT-AGID MintsLoader campaign.

The June chain is technically consistent with MintsLoader tradecraft. The public record does not preserve the remote stage required for a definitive family attribution, so the relationship is assessed with moderate confidence.

The strongest finding concerns `pesterbdd[.]com/images/Pester.png`. Historical PowerShell Gallery and Chocolatey package records identify the URL as the Pester module icon, while an independent 2022 sandbox report recovered it beside other Pester metadata. Without campaign-specific contact telemetry, the URL should be treated as likely package metadata or environmental noise rather than attacker-controlled infrastructure.

## Key Research Findings

1. **June GhostWallet correlation.** The `Fattura` JavaScript lure, hidden PowerShell, `1.php?s=` retrieval path, 15-character `.top` stage and secondary-payload role are consistent with independently documented MintsLoader behavior. Definitive attribution remains open because the remote stage body is unavailable.
2. **Confirmed infrastructure overlap.** `165.22.13[.]227` appears in both the June Certego report and the September CERT-AGID IOC export. This supports correlation but does not establish common control.
3. **Pester provenance.** `pesterbdd[.]com/images/Pester.png` has documented legitimate historical use as package metadata. It is classified as likely noise unless campaign telemetry demonstrates an actual malicious request or response.
4. **Unverified candidate.** `x3qqyj78o2rdso9[.]top` was not present in the examined CERT-AGID JSON and could not be independently reproduced in public indexed sources. It remains outside the confirmed dataset.

## Evidence Scope

Confidence language used throughout the research:

- **CONFIRMED** - directly supported by a cited public source.
- **CORRELATED** - supported by multiple specific observations, with an identified evidence gap.
- **UNVERIFIED** - technically plausible but not reproducible from the preserved public record.
- **EXCLUDED OR NOISY** - supported by provenance evidence as likely unrelated to attacker infrastructure.

The publication does not claim that GhostWallet was definitively MintsLoader, that the June and September activity shared an operator, or that infrastructure overlap proves continuity of control.

## Defensive Takeaways

Defenders should prioritize behavioral combinations over isolated domains. Relevant combinations include invoice-themed JavaScript executed by `wscript.exe`, creation and hidden execution of PowerShell, `Invoke-RestMethod` or `curl` combined with `Invoke-Expression`, requests to `1.php?s=`, and later contact with algorithmically named `.top` domains.

IOC producers should preserve whether a value came from contacted infrastructure, DNS resolution, file or memory strings, package metadata, sandbox artifacts, or analyst enrichment.

## Repository Contents

- [paper/](./paper/) - publication paper and release notes
- [iocs/](./iocs/) - sanitized defensive indicators and classification notes
- [evidence/](./evidence/) - source provenance, methodology and claim boundaries

## Research Status

| Field | Status |
|---|---|
| Technical investigation | Complete at the public-source research stage |
| June MintsLoader relationship | Correlated with moderate confidence |
| Shared infrastructure | Confirmed overlap with analytical limitation |
| Pester URL | Excluded or noisy with high confidence |
| `x3qqyj78o2rdso9[.]top` | Unverified candidate |
| Named threat actor or operator | Not supported |
| CERT coordination | Package prepared for review |
| Publication readiness | Ready, pending CERT feedback |

## Responsible Research

The presence of a domain, IP address, organization or public-sector source in this research does not imply malicious ownership, operational responsibility or error.

No unauthorized exploitation, vulnerability scanning or access was performed. The analysis relies on public reporting, official package records and public sandbox evidence.

---

**BresshSec**  
Independent Cybersecurity & Threat Research  
Focus: Italian Threat Landscape
