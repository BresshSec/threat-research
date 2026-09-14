# Evidence & Provenance — Case Study 003

## Primary Evidence

The primary technical evidence is an isolated ANY.RUN execution performed on **14 September 2026** against the deep-dive sample.

The sandbox classified the activity as malicious and associated it with tags including phishing, ClickFix, terminal-fix, EtherHiding and obfuscated JavaScript.

## Evidence Index

| ID | Artifact | Evidence class | Role |
|---|---|---|---|
| E-01 | ANY.RUN primary report | Primary sandbox evidence | Classification, URLs, domains, IPs, ATT&CK |
| E-02 | Captured `/api.php?s=...` traffic | Primary network evidence | Module retrieval keys and response behavior |
| E-03 | Captured `k=<K>&d=...` request | Primary network evidence | Cross-stage key reuse and encoded client context |
| E-04 | Decoded Base64 `d` object | Derived from primary capture | `action`, `k`, `os`, `vid`, `ref`, `ray` |
| E-05 | Obfuscated JavaScript samples | Primary static evidence | XOR/Base64/dynamic execution and client logic |
| E-06 | 17-byte JavaScript response | Primary network evidence | Explicit no-op `(function(){})();` |
| E-07 | Polygon JSON-RPC / `eth_call` capture | Primary network evidence | Contract/selector resolution path |

## Evidence Discipline

Public artifacts should be relevant to a published claim, sanitized, free of unrelated personal/sandbox metadata and mapped to the claim they support.

## Explicit Limits

This evidence set does **not** establish:

- the original compromise vector of the legitimate website;
- a named threat actor;
- the exact server-side gating algorithm;
- operator identity;
- cross-victim reuse unless separately documented with reproducible evidence.

These limits are part of the analytical result.
