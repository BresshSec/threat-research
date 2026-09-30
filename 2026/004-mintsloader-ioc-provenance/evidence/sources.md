# Public source register

## Primary campaign sources

- Certego, Operation GhostWallet report, 22 July 2026: https://www.certego.net/it/blog/pec-malevola-e-crypto-wallet-trojan-di-accesso-remoto/
- CERT-AGID campaign report, 24 September 2026: https://cert-agid.gov.it/news/mintsloader-via-pec-falsi-solleciti-di-pagamento-per-diffondere-malware/
- CERT-AGID event 26383 IOC JSON: https://cert-agid.gov.it/wp-content/uploads/2026/09/mintsloader-pec-24-09-2026.json

## MintsLoader technical references

- Red Canary Threat Detection Report: https://redcanary.com/threat-detection-report/threats/mintsloader/
- eSentire Threat Response Unit, 16 January 2025: https://www.esentire.com/blog/mintsloader-stealc-and-boinc-delivery

## Pester provenance

- PowerShell Gallery, Pester 3.3.5 manifest: https://www.powershellgallery.com/packages/Pester/3.3.5/Content/Pester.psd1
- Chocolatey, Pester 3.3.12, updated 8 December 2015: https://community.chocolatey.org/packages/pester/3.3.12
- Joe Sandbox analysis 758249, start time 1 December 2022: https://www.joesandbox.com/analysis/758249/0/pdf
- ANY.RUN analysis showing a later malicious reputation verdict: https://any.run/report/52f47b2ffb1dbb5da4239354d04044edf7b0d912b1fb26225479b418fcebe419/c6807ec4-4d45-4823-81ca-9e27529e1ad6

## Source interpretation notes

- Certego documents the June chain and its artifact gaps; it does not identify the loader as MintsLoader.
- Red Canary and eSentire establish the comparison fingerprint, not the attribution of the exact June sample.
- Package records establish historical legitimate provenance for the Pester URL. They do not guarantee the domain's present security state.
- The Joe Sandbox report provides an independent historical execution-context observation.
