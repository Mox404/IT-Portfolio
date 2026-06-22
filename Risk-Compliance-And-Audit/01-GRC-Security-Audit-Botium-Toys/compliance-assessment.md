# Compliance Assessment

## PCI DSS

| Best Practice | Status | Finding | Risk | Suggested Improvement |
| --- | --- | --- | --- | --- |
| Only authorized users have access to customer credit card information. | Not aligned | All employees can access internal data, which may include cardholder data. | Unauthorized access to cardholder data could lead to data exposure and compliance issues. | Apply least privilege and limit cardholder data access to approved roles only. |
| Credit card information is accepted, processed, transmitted, and stored internally in a secure environment. | Not aligned | Cardholder data is not encrypted and access is too broad. | Payment data may not be protected enough during storage or use. | Secure cardholder data handling, restrict access, and encrypt sensitive data. |
| Implement data encryption procedures for cardholder data. | Not aligned | Encryption is not currently used. | Exposed cardholder data could create high compliance and customer trust risk. | Encrypt cardholder data at rest and in transit. |
| Adopt secure password management policies. | Not aligned | Password requirements are weak and there is no password management system. | Weak credentials could allow account compromise. | Strengthen password requirements and implement centralized password management. |

## GDPR

| Best Practice | Status | Finding | Risk | Suggested Improvement |
| --- | --- | --- | --- | --- |
| EU customer data is kept private and secured. | Not aligned | Sensitive data is not sufficiently protected due to lack of encryption and broad access. | Personal data could be exposed or accessed without proper authorization. | Restrict access, encrypt sensitive data, and review privacy controls. |
| Breach notification plan supports notification within 72 hours. | Aligned | A plan exists to notify EU customers within 72 hours of a breach. | The plan may still be less effective if it is not tested. | Test and review the notification process regularly. |
| Data is properly classified and inventoried. | Not aligned | Assets have been listed, but data and assets are not properly classified. | The company may not know which information needs the strongest protection. | Classify data and assets based on sensitivity and business value. |
| Privacy policies, procedures, and processes are enforced. | Aligned | Privacy policies, procedures, and processes have been developed and enforced. | Policies may become outdated without periodic review. | Continue enforcement and review privacy documentation regularly. |

## SOC Type 1 / SOC Type 2

| Best Practice | Status | Finding | Risk | Suggested Improvement |
| --- | --- | --- | --- | --- |
| User access policies are established. | Not aligned | Least privilege and separation of duties are not implemented. | Users may have more access than they need. | Create role based access policies and review access regularly. |
| Sensitive data, PII, and SPII remain confidential and private. | Not aligned | Encryption is not used and access is too broad. | Sensitive data may be exposed or misused. | Encrypt sensitive data and restrict access to authorized users. |
| Data integrity is ensured. | Aligned | Controls are in place to support data integrity. | Integrity risk is reduced but still requires monitoring. | Continue monitoring and testing integrity controls. |
| Data is available to authorized individuals. | Partially aligned | Data is available, but access should be limited to properly authorized individuals only. | Availability is present, but authorization controls are weak. | Keep data available while limiting access to approved roles. |
