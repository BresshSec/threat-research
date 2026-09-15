# Case Study 003 — Stateful Module Delivery in a ClickFix / EtherHiding Chain

**Research window:** 14–15 September 2026  
**Researcher:** BresshSec  
**Status:** FINAL / RESEARCH CLOSED  
**Focus:** ClickFix · EtherHiding · BW Panel / ErrTraffic · state-dependent delivery

## Executive Summary

This case study documents a web-based malware delivery chain observed through compromised Italian web infrastructure and exhibiting characteristics associated with the ClickFix, EtherHiding and BW Panel / ErrTraffic ecosystem.

The investigation moved beyond IOC collection into protocol reconstruction. Captured traffic, obfuscated client-side code, Polygon JSON-RPC resolution and downstream module retrieval showed that the delivery backend could alter its response according to state that was not fully visible to the analyst.

The research is now closed at the passive/independent-investigation stage. Additional certainty around victim-specific initial access would require server-side evidence from the affected organization rather than further external probing.

## Key Research Finding

During the same sandbox execution, requests associated with the same module key transitioned from substantial active JavaScript delivery to an explicit executable no-op:

```javascript
(function(){})();
```

The observed transition supports **state-dependent module delivery in the analyzed session**. The exact server-side gating condition remains unknown.

This matters because a later replay can look benign even when the same delivery path served active content earlier in the session.

## Closure Update — 15 September 2026

The final research pass added four important conclusions:

1. **Exact configuration correlation.** A routing/configuration key recovered from one Italian institutional web asset was independently reproduced with the same Polygon contract, function selector and delivery grammar. This upgrades the case from generic technique similarity to a high-confidence configuration-lineage correlation.
2. **Longitudinal infrastructure.** The same on-chain control design and associated delivery infrastructure were observed across multiple compromised websites over time, while domains and final payloads rotated.
3. **Initial-access assessment.** Victim-specific initial access remains unproven. Valid WordPress account compromise is the leading hypothesis based on independently reconstructed intrusions in the same operational lineage, while no specific CVE is supported as the entry vector for the directly analyzed Italian victims.
4. **Research boundary reached.** Further resolution of initial access requires victim-side authentication logs, web-server logs, historical WordPress/plugin versions, filesystem/database artifacts or equivalent forensic evidence. Passive OSINT alone cannot responsibly promote that hypothesis to a confirmed finding.

## Evidence Scope

Confidence language used throughout the research:

- **CONFIRMED** — directly supported by captured evidence.
- **ASSESSED** — analytical interpretation supported by multiple observations.
- **UNKNOWN** — not established by available evidence.

The final publication deliberately keeps the following boundaries:

- state-dependent delivery is confirmed in the analyzed session;
- exact server-side gating remains unknown;
- framework/infrastructure linkage is stronger than human-actor attribution;
- no named APT is attributed;
- no single exploited CVE is claimed for the analyzed victims;
- legitimate websites are treated as compromised infrastructure/victims unless evidence demonstrates otherwise.

## Observed Chain

1. Compromised WordPress web infrastructure
2. Injected / obfuscated JavaScript
3. Polygon JSON-RPC / EtherHiding-style configuration resolution
4. Smart-contract `eth_call`
5. ABI-decoded rotating delivery host
6. Configuration-keyed `/api.php` module retrieval
7. Client/site/session context carried into later communication
8. Active JavaScript delivery
9. Later suppression through an executable no-op response

## Why This Matters

A tiny, syntactically valid JavaScript response can look benign to simplistic automated collection. In the observed session, however, the no-op appeared after substantial active JavaScript had already been delivered under related protocol state.

A single late-stage fetch therefore may not faithfully represent what the same delivery path returned earlier in the session. Historical request/response context matters, particularly for sandbox reproduction, IOC validation and retrospective threat hunting.

## Defensive Takeaways

Defenders investigating similar chains should preserve:

- request chronology;
- complete response bodies and sizes;
- module/configuration keys;
- referrer and hostname context;
- client/session identifiers;
- cookies and browser storage;
- Polygon RPC calls and raw ABI responses;
- DNS answers and timestamps.

For compromised WordPress infrastructure, responders should additionally preserve authentication logs, web-server access logs, plugin/theme inventories, MU-plugins, filesystem timestamps and database changes before remediation.

## Repository Contents

- [paper/](./paper/) — frozen publication paper and release notes
- [iocs/](./iocs/) — sanitized defensive indicators
- [evidence/](./evidence/) — evidence provenance and claim boundaries
- [figures/](./figures/) — publication-safe figure specifications

## Final Research Status

| Field | Status |
|---|---|
| Technical investigation | Complete |
| Primary protocol finding | Supported |
| Cross-sample corroboration | Present |
| Infrastructure/configuration lineage | High confidence |
| Victim-specific initial access | Unresolved; valid-account compromise assessed as leading hypothesis |
| Specific exploited CVE | Not established |
| Named threat actor / APT | Not supported |
| Publication readiness | Final |
| Research status | Closed |

The case can be reopened only if materially new primary evidence becomes available, such as victim-side forensic artifacts or a directly linked malware/server sample.

## Responsible Research

A legitimate domain appearing in this research may itself be a victim of compromise. Inclusion does **not** imply malicious ownership or participation.

No unauthorized exploitation, vulnerability scanning or access was performed against third-party infrastructure as part of this research.

No named threat actor is attributed in this case study. Ecosystem/framework similarity must not be interpreted as proof of operator identity.

---

**BresshSec**  
Independent Cybersecurity & Threat Research  
Focus: Italian Threat Landscape
