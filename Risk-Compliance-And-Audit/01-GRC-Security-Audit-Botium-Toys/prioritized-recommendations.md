# Prioritized Recommendations

## Priority 1: Implement least privilege and separation of duties

**Issue:** All employees currently have broad access to internally stored data, and separation of duties is not in place.

**Why it matters:** Excessive access increases the risk of unauthorized viewing, misuse, fraud, and mistakes.

**Recommended action:** Create role based access rules, limit access based on job duties, and separate conflicting responsibilities.

**Expected benefit:** Reduced access risk and stronger support for compliance expectations.

## Priority 2: Encrypt sensitive customer and cardholder data

**Issue:** Sensitive customer and cardholder data is not currently encrypted.

**Why it matters:** Unencrypted data can be exposed more easily if systems or accounts are compromised.

**Recommended action:** Encrypt sensitive data at rest and in transit.

**Expected benefit:** Better protection for customer data and stronger alignment with PCI DSS, GDPR, and SOC expectations.

## Priority 3: Create and test disaster recovery and backup procedures

**Issue:** Disaster recovery plans and critical data backups are not currently in place.

**Why it matters:** A system outage, cyber incident, or data loss event could interrupt business operations.

**Recommended action:** Create backup schedules, define recovery procedures, assign owners, and test restoration regularly.

**Expected benefit:** Improved business continuity and faster recovery after incidents.

## Priority 4: Deploy an IDS or IDS IPS

**Issue:** No intrusion detection system is currently installed.

**Why it matters:** Without intrusion detection, suspicious activity may not be noticed quickly.

**Recommended action:** Deploy an IDS or IDS IPS solution and create a process to review alerts.

**Expected benefit:** Better security monitoring and faster response to possible attacks.

## Priority 5: Strengthen password policy and implement centralized password management

**Issue:** A password policy exists, but requirements are weak, and there is no centralized password management system.

**Why it matters:** Weak credentials can lead to account compromise and unauthorized access.

**Recommended action:** Strengthen password requirements and implement an approved password manager.

**Expected benefit:** Lower credential risk and more consistent password handling.

## Priority 6: Classify and inventory data and assets

**Issue:** Assets have been listed, but data and assets are not properly classified.

**Why it matters:** Without classification, it is harder to know which data needs the strongest protection.

**Recommended action:** Classify data and assets by sensitivity, business value, and compliance impact.

**Expected benefit:** Better security prioritization and stronger compliance documentation.

## Priority 7: Formalize legacy system maintenance and monitoring

**Issue:** Legacy systems are monitored and maintained, but there is no regular schedule and procedures are unclear.

**Why it matters:** Unsupported or poorly maintained systems may introduce vulnerabilities and operational issues.

**Recommended action:** Create a maintenance calendar, document procedures, and assign responsible owners.

**Expected benefit:** More reliable maintenance and reduced legacy system risk.

## Priority 8: Continue maintaining existing firewall, antivirus, locks, CCTV, and fire controls

**Issue:** Several controls are working, but they still need ongoing maintenance.

**Why it matters:** Security controls can lose effectiveness if they are not reviewed, updated, or tested.

**Recommended action:** Continue scheduled reviews, updates, inspections, and monitoring.

**Expected benefit:** Continued protection from existing technical and physical controls.
