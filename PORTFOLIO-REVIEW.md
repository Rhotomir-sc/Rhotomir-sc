# Portfolio review guide

A concise index of cybersecurity work that can be inspected or reproduced. **Completed labs, synthetic demonstrations and planned follow-up tasks are not interchangeable.** I am an Information Security Technology student, not claiming production security engineering experience.

## Recommended review order

| Project | What to review | Current evidence |
|---|---|---|
| [Cloud identity investigation (TryHackMe Lab 10)](https://github.com/Rhotomir-sc/tryhackme-portfolio-pack/tree/main/portfolio-labs/10-cloud-identity-basics) | Entra ID/Splunk queries, error-code interpretation and tested [offline timeline validator](https://github.com/Rhotomir-sc/tryhackme-portfolio-pack/blob/main/portfolio-labs/10-cloud-identity-basics/timeline-review.md) | Lab screenshots and code tests exist; **the original event-level timeline has not been rerun** |
| [Google Cybersecurity integrated case](https://github.com/Rhotomir-sc/google-cybersecurity-portfolio-pack/tree/main/integrated-security-case) | Synthetic cloud sign-ins, web logs, SQL, and [AUTH-001 detection rule](https://github.com/Rhotomir-sc/google-cybersecurity-portfolio-pack/blob/main/integrated-security-case/DETECTION-RULE.md) | Runnable Python/SQL analysis and unit tests; scenario is **fictional** |
| [Windows network baseline tooling](https://github.com/Rhotomir-sc/google-cybersecurity-portfolio-pack/blob/main/03_Module-3_Connect-and-Protect_Networks/network-baseline-and-security-notes.md) | Read-only collector, minimized JSON, before/after comparison and tests | Synthetic fixtures and GitHub-hosted Windows smoke test; **personal host capture pending** |
| [Security capstone](https://github.com/Rhotomir-sc/security-capstone) | SSH authentication-log sequence analysis, risk assessment and [reproduction guide](https://github.com/Rhotomir-sc/security-capstone/blob/main/REPRODUCE.md) | Synthetic SSH fixture with runnable Python tests; **live remediation pending** |
| [12 TryHackMe investigations](https://github.com/Rhotomir-sc/tryhackme-portfolio-pack/blob/main/LAB-INDEX.md) | SOC triage, Windows/Sysmon, incident response, networks, cloud identity and phishing | Each lab has documentation and an evidence index; some follow-up validation remains open |
| [Academic evidence](https://github.com/Rhotomir-sc/semester-evidence-packs) | Coursework artifacts, Linux and networking notes, risk register and C log analyzer | Reproducible C fixture and academic documentation; not presented as industry experience |

## Practical verification

For the integrated case, from the **Google repository root**, using Python 3.10+:

```sh
python integrated-security-case/scripts/analyze_signin_case.py --format json
python -m unittest discover -s integrated-security-case/tests -v
python tools/run_sql_case.py
```

For the SSH capstone, from the **Security Capstone repository root**:

```sh
python scripts/log_summary.py
python -m unittest discover -s tests -v
```

For TryHackMe Lab 10's **synthetic validation fixture only**, from the **TryHackMe repository root**:

```sh
python -m unittest discover -s portfolio-labs/10-cloud-identity-basics/tests -v
```

These checks validate included code and sample datasets, not an actual cloud intrusion or production monitoring service. Each repository maintains its own scope, current run instructions and documented limitations.

## Current learning direction

**Cloud Security + Identity Security + Security Automation + AI Security.** I am building toward security engineering and architecture through Microsoft identity/cloud fundamentals, small detection automation projects, reproducible labs, and a supporting attacker-informed defensive perspective.

The AI Security/LLM component is a **future learning and lab direction**, not a claim that this portfolio currently demonstrates a deployed AI security product.

## Evidence standard

I label each result as one of the following:

- **Observed in an authorized training lab:** backed by recorded queries, screenshots or outputs, with limits stated.
- **Reproducible synthetic work:** runnable code and artificial fixtures, clearly separate from real-world evidence.
- **Planned or pending:** a proposed experiment or control not yet demonstrated with actual results.

A passing GitHub Actions workflow indicates that its configured checks passed; it does not substitute for analyst confirmation or deployment evidence.

[Back to profile](README.md)
