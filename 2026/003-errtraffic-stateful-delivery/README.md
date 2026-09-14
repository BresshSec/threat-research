# Case Study 003 — Stateful Module Delivery in a ClickFix / EtherHiding Chain

**Research date:** 14 September 2026  
**Researcher:** BresshSec  
**Status:** Release candidate  
**Focus:** ClickFix · EtherHiding · BW Panel / ErrTraffic · state-dependent delivery

## Executive Summary

This case study documents a web-based malware delivery chain observed through compromised Italian web infrastructure and exhibiting characteristics associated with the ClickFix, EtherHiding and BW Panel / ErrTraffic ecosystem.

The protocol-level evidence presented here is intentionally centered on one deep-dive sandbox sample. The research reconstructs observable client-side state, module retrieval and callback behavior while separating confirmed observations from analytical assessment and unresolved server-side behavior.

## Key Research Finding

During the same sandbox execution, requests associated with the same module key transitioned from substantial active JavaScript delivery to an explicit executable no-op:

```javascript
(function(){})();
```

The observed transition supports **state-dependent module delivery in the analyzed session**. The exact server-side gating condition remains unknown.

## Evidence Scope

The primary evidence set is the documented deep-dive sandbox execution. Additional victim sites are not presented as evidence-bearing samples unless their corresponding artifacts and citations are included.

Confidence language used throughout the research:

- **CONFIRMED** — directly supported by captured evidence.
- **ASSESSED** — analytical interpretation supported by available observations.
- **UNKNOWN** — not established by available evidence.

Cross-victim reuse, the initial compromise vector and named-actor attribution are not promoted to confirmed findings in this release.

## Observed Chain

1. Compromised web infrastructure
2. ClickFix-style deceptive interaction
3. Obfuscated JavaScript
4. Remote delivery component
5. Polygon JSON-RPC / EtherHiding-style resolution
6. State carried across module retrieval and callback stages
7. Active JavaScript delivery
8. Later suppression through an executable no-op response

## Why This Matters

A tiny, syntactically valid JavaScript response can look benign to simplistic automated collection. In the observed session, however, the no-op appeared after substantial active JavaScript had already been delivered under related protocol state.

A single late-stage fetch therefore may not faithfully represent what the same delivery path returned earlier in the session. Historical request/response context matters.

## Defensive Takeaways

Defenders investigating similar chains should preserve request chronology and correlate module keys, client/session identifiers, referrer context and response sizes rather than evaluating responses in isolation.

A no-op response should not automatically be interpreted as evidence that an endpoint or delivery path was inactive throughout the session.

## Repository Contents

- [paper/](./paper/) — publication notes for the full paper
- [iocs/](./iocs/) — sanitized defensive indicators
- [evidence/](./evidence/) — evidence provenance and claim boundaries
- [figures/](./figures/) — publication-safe figure specifications

## Responsible Research

A legitimate domain appearing in this research may itself be a victim of compromise. Inclusion does **not** imply malicious ownership or participation.

No named threat actor is attributed in this case study. Ecosystem/framework similarity must not be interpreted as proof of operator identity.

---

**BresshSec**  
Independent Cybersecurity & Threat Research  
Focus: Italian Threat Landscape
