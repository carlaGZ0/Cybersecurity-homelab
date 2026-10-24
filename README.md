# Cybersecurity Home Lab: Segmented Network, Active Directory and SOC Detection

A virtualized lab where I design a segmented network, deploy an Active Directory domain, simulate attacks and write detections with Wazuh. Built to learn and demonstrate defensive security (SOC) skills.

**Status:** In progress · **Last updated:** October 2026 · **Host:** VirtualBox on Linux Mint

---

## Goals

- Learn how to design and segment a network with VLANs and firewall rules.
- Practise administering an Active Directory domain.
- Simulate common attack techniques and detect them with a SIEM.
- Document everything as a real analyst would: evidence, analysis and lessons learned.

## Architecture

![Network diagram](img/network-diagram.png)

*Figure 1. Network diagram with VLANs, hosts and log flow to Wazuh.*

| Component | Role | OS / Software | Network / VLAN |
|---|---|---|---|
| Hypervisor | Hosts all VMs | VirtualBox on Linux Mint | n/a |
| Firewall / router | Segmentation and access rules | OPNsense / pfSense | All VLANs |
| Domain controller | Active Directory, DNS | Windows Server 2022 | VLAN 10, 192.168.10.0/24 |
| Windows client | Domain-joined workstation, Sysmon | Windows 10/11 | VLAN 20 |
| Linux server | Web service / SIEM agent | Ubuntu Server | VLAN 30 |
| SIEM | Log collection and alerting | Wazuh | VLAN 40 |
| Attacker | Attack simulation | Kali Linux | VLAN 50 |

## Lab status

| Lab | Topic | Status |
|---|---|---|
| [LAB 1: Network and services](labs/01-network/) | Segmentation, DHCP/DNS, firewall rules, web server, backups | In progress |
| [LAB 2: Active Directory](labs/02-active-directory/) | Domain, OUs, GPOs, users, event auditing | In progress |
| LAB 3: Red team | Reconnaissance and attack simulation | Planned |
| LAB 4: Blue team / SOC | Wazuh SIEM, log collection, detection rules | Planned |
| LAB 5: Attack / Defense | Hardening and re-testing controls | Planned |
| LAB 6: Incident response | Investigation, containment, final report | Planned |

## Key results

- n attack techniques simulated and mapped to MITRE ATT&CK
- n of them detected by default Wazuh rules; n required custom rules
- n custom detection rules written (see `detection-rules/`)
- n incident report(s) written (see `incident-reports/`)

## Methodology

Every lab follows the same structure:

1. Requirements and architecture justification
2. Network design and segmentation
3. Step-by-step implementation
4. Security testing and mitigation
5. Lessons learned and future improvements

## Skills demonstrated

- **Networking:** VLAN segmentation, inter-VLAN routing, firewall rules, DHCP, DNS
- **Systems:** Windows Server, Active Directory, GPOs, Linux administration
- **Security:** Wazuh, Sysmon, MITRE ATT&CK, log analysis, detection engineering
- **Documentation:** Git, Markdown, diagrams, incident reports

## Repository structure

```
cybersecurity-homelab/
├── README.md
├── docs/             network diagram, addressing table, setup notes
├── labs/             one folder per lab, each with its own README
├── detection-rules/  custom Wazuh / Sigma rules
├── incident-reports/
├── configs/          sanitized configuration files
└── img/              diagrams and screenshots (no sensitive data)
```

## Roadmap

- [ ] Document the VLAN segmentation with real evidence
- [ ] Deploy Wazuh and connect Windows and Linux agents
- [ ] First attack report: SSH brute force, from attack to detection
- [ ] First complete incident report

## Disclaimer

This is an isolated educational lab. All attacks are run only against machines I own, inside a network that is not connected to my home network. No real credentials, domains or personal data are included.

## About me

Your Name, student of Higher Vocational Training in Network Systems Administration (ASIR), interested in defensive security and SOC roles.

[LinkedIn](https://www.linkedin.com/in/your-profile) · your.email@example.com

---

<details>
<summary>Resumen en español</summary>

Laboratorio virtualizado donde diseño una red segmentada, despliego un dominio de Active Directory, simulo ataques y escribo detecciones con Wazuh. Cada laboratorio sigue la misma metodología y documenta evidencias, análisis y lecciones aprendidas.

</details>
