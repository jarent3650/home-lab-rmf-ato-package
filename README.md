# home-lab-rmf-ato-package
A self-built, self-authorized "system" — two lab VMs (Windows and Linux) — taken through the same Risk Management Framework (RMF) lifecycle used to authorize real systems for operation in government and enterprise environments.

This isn't a tutorial-following exercise. It's a full authorization package: categorization, hardening to DISA STIG standards, vulnerability scanning, continuous monitoring, a findings tracker modeled on eMASS, and the final authorization documentation (SSP, SAR, ATO memo).

Why I built this: to demonstrate hands-on RMF, STIG hardening, and vulnerability management skills using the same tools and processes used in real ISSO/cybersecurity compliance roles — without needing a clearance or a government eMASS account to prove it.

Enviroment
Hypervisor: VirtualBox (free) — or substitute Proxmox/ESXi
Systems under test:
Windows 10/11 VM
Ubuntu (or RHEL/CentOS) VM
All tools used are free:
DISA STIGs & SCAP content — DoD Cyber Exchange
SCAP Compliance Checker (SCC) — DoD Cyber Exchange
STIG Viewer — DoD Cyber Exchange
Tenable Nessus Essentials — free, up to 16 IPs
Splunk Free — 500MB/day ingest

Structure
rmf-authorization-lab/
├── 01-categorization/     FIPS 199 categorization of the lab system
├── 02-hardening/          STIG checklists and remediation notes (Windows + Linux)
├── 03-scanning/           SCAP and Nessus scan results
├── 04-monitoring/         Splunk dashboards and detection searches
├── 05-poam/               Plan of Action & Milestones (eMASS-style findings tracker)
├── 06-package/            SSP, SAR, and ATO memo tying it all together
└── screenshots/           Supporting evidence for each phase

How to Reproduce
Stand up a Windows and a Linux VM in VirtualBox (or your hypervisor of choice).
Download the relevant STIGs for your OS versions from DoD Cyber Exchange.
Manually apply each applicable STIG control, tracking pass/fail in STIG Viewer.
Validate your hardening with SCC (SCAP) and scan for additional weaknesses with Nessus.
Stand up Splunk Free, forward logs from both VMs, and build detections for the STIG controls and general suspicious activity.
Log every open finding in the POA&M tracker (05-poam/), with severity and remediation dates.
Write up the SSP, SAR, and ATO memo in 06-package/ summarizing the whole effort.

Disclaimer
This is a personal lab project for skills development. It uses publicly available DoD STIG and SCAP content but is not affiliated with, endorsed by, or representative of any government agency or contractor. No real production systems, networks, or data are involved.
