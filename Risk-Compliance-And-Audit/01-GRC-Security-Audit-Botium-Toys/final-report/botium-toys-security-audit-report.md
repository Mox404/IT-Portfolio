# Botium Toys Security Audit Report

Botium Toys is a fictional company used in the Google Cybersecurity course. I kept this report because it was a useful exercise in looking at security controls from a risk and compliance angle.

## Summary

The scenario showed several weak or missing controls around access, encryption, backups, disaster recovery, intrusion detection, password management, and asset classification.

There were also controls already in place, including a firewall, antivirus software, locks, CCTV, fire detection, breach notification procedures, privacy processes, and data integrity controls.

The main issue was that the existing controls did not cover some of the highest risk areas.

## Scope

I reviewed:

* access management
* protection of sensitive data
* backup and recovery readiness
* monitoring and detection
* physical security
* general PCI DSS and GDPR awareness
* SOC Type 1 and SOC Type 2 concepts from the course material

## Main findings

| Area | What stood out |
| --- | --- |
| Access | least privilege and separation of duties were not properly in place |
| Data protection | sensitive customer and cardholder data was not encrypted |
| Recovery | no proper disaster recovery plan or critical data backups |
| Monitoring | antivirus was present, but there was no IDS |
| Network | a firewall was already in place |
| Physical security | locks, CCTV, and fire controls were already being used |

## Compliance view

### PCI DSS

The biggest problems were broad access to cardholder data, no encryption, and weak password controls.

### GDPR

The scenario had privacy and breach notification processes, but sensitive data still needed stronger protection and classification.

### SOC concepts

Data integrity and availability controls existed, but access and confidentiality needed more work.

## Risk

I rated the overall scenario as high risk because the missing controls affected sensitive data, business continuity, and privileged access.

| Area | My rating | Why |
| --- | --- | --- |
| Data security | High | sensitive data was not encrypted and access was too broad |
| Compliance | High | several controls needed for the scenario were weak or missing |
| Business continuity | High | no proper recovery plan or critical backups |
| Access control | High | least privilege and separation of duties were missing |
| Technical monitoring | Medium to high | firewall and antivirus existed, but IDS and some other controls did not |
| Physical security | Low to medium | the main physical controls were already in place |

## What I would prioritize

1. tighten access and apply least privilege
2. encrypt sensitive customer and cardholder data
3. create and test backups and disaster recovery procedures
4. improve detection with an IDS or similar monitoring
5. strengthen password and privileged account controls
6. classify important data and assets
7. keep the existing firewall, antivirus, CCTV, locks, and fire controls maintained

## What I got from the exercise

This was useful for seeing how a technical weakness turns into a business risk.

For example, missing encryption is not just a technical gap. It affects exposure if data is stolen and can create compliance problems too. The same applies to backups, access control, and monitoring.

> Fictional course scenario. This is not a real company audit.
