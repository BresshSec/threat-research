
# Threat Research

Personal repository where I document cybersecurity research, malware analysis, phishing campaigns and detection techniques.

The primary focus of this project is the analysis of **threats involving Italian domains, websites and infrastructure**, with particular attention to malicious campaigns affecting Italian users and organizations.

Research includes threats observed in the wild such as phishing, ClickFix, malicious redirects, compromised websites, malware delivery infrastructure and other emerging attack techniques.

The goal is to analyze real-world threats, reconstruct their behavior and attack chain, extract useful Indicators of Compromise (IOCs), and develop detection opportunities for defensive security.

## Research

| Date | Campaign | Target / Context | Technique | Analysis |
|------|----------|------------------|-----------|----------|
| 2026-09-03 | ClickFix Campaign | Italian domain | Fake CAPTCHA / MSHTA | [Read Analysis](./2026/001-clickfix-informatore-agrario) |
| 2026-09-04 | PagoPA / TARI Refund Phishing | Italian users / PagoPA impersonation | Phishing / Passive DNS / Infrastructure correlation | [Read Analysis](./2026/002-pagopa-tari-phishing/) |

## Research Focus

Primary areas of research:

- Threats involving Italian domains and infrastructure
- Phishing campaigns targeting Italian users
- Compromised or abused websites
- ClickFix and Fake CAPTCHA campaigns
- Malware delivery chains
- Malicious redirects
- Living Off The Land techniques
- Malware Analysis
- Threat Intelligence
- Detection Engineering
- MITRE ATT&CK mapping
- IOC collection and analysis

## Analysis Workflow

My typical research workflow includes:

1. Identification of suspicious activity
2. Collection of URLs, domains and initial indicators
3. Analysis in an isolated environment
4. Process and network behavior analysis
5. Attack chain reconstruction
6. MITRE ATT&CK mapping
7. IOC extraction
8. Detection development
9. Responsible disclosure when applicable

Tools used may include ANY.RUN, VirusTotal, Wireshark, Sysinternals and other threat intelligence and malware analysis resources.

## Repository Structure

Each investigation is stored separately and may contain:

    analysis/
    screenshots/
    iocs/
    detections/

Depending on the investigation, detection content may include Sigma rules, YARA rules, Suricata signatures or SIEM queries.

## Responsible Disclosure

When research involves infrastructure belonging to a legitimate organization, I make reasonable efforts to notify the affected organization before publishing technical details.

Sensitive information may be removed or defanged when appropriate.

## Disclaimer

All research published in this repository is performed for educational, research and defensive cybersecurity purposes.

The presence of a domain, IP address, organization or other third party in an analysis does not necessarily imply malicious intent or responsibility for the observed activity.

Indicators of Compromise are provided exclusively to support threat intelligence, detection and defensive security activities.

---

**Andrea Salvadori**

System Administrator | Cybersecurity & Threat Research  
Focus: **Italian Threat Landscape**
