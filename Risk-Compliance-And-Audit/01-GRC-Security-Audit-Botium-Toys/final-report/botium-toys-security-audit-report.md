# Botium Toys Security Audit Report

## Title Page

**Project:** Internal Security Audit Case Study  
**Company:** Botium Toys  
**Scenario Type:** Fictional scenario  
**Prepared For:** Cybersecurity portfolio  
**Focus Area:** Governance, risk, compliance, and security auditing  
**Date:** June 2026

## Executive Summary

Botium Toys has a high risk security posture due to missing or weak controls in access management, encryption, disaster recovery, backups, intrusion detection, password management, and asset classification.

The strongest concerns are broad employee access to internally stored data, no encryption for sensitive customer and cardholder data, no disaster recovery plan, and no critical data backups. These gaps increase the risk of unauthorized access, data exposure, business disruption, and compliance issues.

The company does have several useful controls in place. These include a firewall, antivirus software, locks, CCTV surveillance, fire detection and prevention systems, breach notification procedures, privacy processes, and data integrity controls. These controls are a good foundation, but they do not fully reduce the current level of risk.

## Scope

The audit reviewed current security controls, IT managed assets, access management practices, sensitive data protection, business continuity readiness, physical security controls, and compliance alignment with PCI DSS, GDPR, and SOC Type 1 and SOC Type 2 expectations.

## Methodology

The audit process included reviewing scope and goals, reviewing IT managed assets, reviewing current controls and risk comments, classifying controls as administrative, technical, or physical, assessing compliance alignment, identifying control gaps, and prioritizing recommendations based on business risk and data sensitivity.

## Control Assessment Summary

| Area | Summary |
| --- | --- |
| Access management | Least privilege and separation of duties are not implemented. Password policy exists but needs improvement. |
| Data protection | Encryption is not currently used for sensitive customer or cardholder data. |
| Business continuity | Disaster recovery plans and critical data backups are not in place. |
| Monitoring | Antivirus software is monitored, but there is no intrusion detection system. |
| Network security | A firewall is in place and blocks traffic using defined rules. |
| Legacy systems | Legacy systems are monitored and maintained, but the process needs a regular schedule and clearer procedures. |
| Physical security | Locks, CCTV, and fire detection and prevention controls are in place and functioning. |

## Compliance Assessment Summary

### PCI DSS

Botium Toys is not fully aligned with PCI DSS expectations. Cardholder data access is too broad, encryption is not used, and password management controls are weak.

### GDPR

Botium Toys has breach notification procedures and privacy processes in place, but sensitive data is not sufficiently protected. Data and assets also need proper classification.

### SOC Type 1 / SOC Type 2

Botium Toys has data integrity controls and data availability, but access control and confidentiality controls need improvement. Least privilege, separation of duties, and encryption should be prioritized.

## Risk Summary

**Overall Risk Rating:** High

The highest risk areas are data security, compliance, business continuity, access control, and technical monitoring. Physical security is stronger than the other areas because locks, CCTV, and fire detection and prevention systems are working.

| Risk Area | Rating | Main Concern |
| --- | --- | --- |
| Data security | High | Sensitive data is not encrypted and access is too broad. |
| Compliance | High | Current controls do not fully support PCI DSS, GDPR, or SOC expectations. |
| Business continuity | High | No disaster recovery plan or critical data backups are in place. |
| Access control | High | Least privilege and separation of duties are missing. |
| Technical controls | Medium to high | Firewall and antivirus are present, but IDS, encryption, and password management are missing. |
| Physical security | Low to medium | Physical controls are in place and functioning. |

## Prioritized Recommendations

1. Implement least privilege and separation of duties to reduce unnecessary access.
2. Encrypt sensitive customer and cardholder data at rest and in transit.
3. Create and test disaster recovery and backup procedures.
4. Deploy an IDS or IDS IPS solution for better detection.
5. Strengthen password requirements and implement centralized password management.
6. Classify and inventory data and assets based on sensitivity and business value.
7. Formalize legacy system maintenance and monitoring with a clear schedule.
8. Continue maintaining existing firewall, antivirus, locks, CCTV, and fire controls.

## Conclusion

Botium Toys has some important security controls in place, but the overall security posture remains high risk because several core controls are missing or weak. The most important improvements are access control, encryption, backup and disaster recovery planning, intrusion detection, password management, and data classification.

Completing these improvements would reduce business risk, support compliance alignment, and help protect customer and cardholder data.

## Disclaimer

This report is based on a fictional company scenario. It was prepared as a portfolio case study and does not represent a real company audit. The public repository contains only rewritten portfolio-ready documentation.
