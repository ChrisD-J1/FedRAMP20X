# FedRAMP KSI Validations and JSON Reporting Overview

The FedRAMP Key Security Indicators (KSIs) define essential security controls that a cloud service offering must meet to ensure protection of federal data and compliance with FedRAMP standards. These KSIs cover multiple domains such as network security, service configuration, identity and access management, monitoring, change management, and more.

---

## Purpose

The KSIs provide a clear, structured set of controls that cloud providers validate to demonstrate their security posture. This framework helps federal agencies and auditors gain confidence that the cloud service enforces rigorous security measures consistently and continuously.

---

## Validation Approach

- **Automated Evidence Collection**  
  Cloud providers leverage automated security graph platforms (e.g., JupiterOne) to execute precise queries (J1QL) against their environment. These queries collect real-time evidence confirming whether each security control is implemented correctly.

- **Human-Readable Query Summaries**  
  Each query is accompanied by a natural language description (`query_nlp`) explaining what the query is verifying. This enhances clarity and auditability by translating technical queries into understandable sentences.

- **Third-Party Auditor Verification**  
  Independent FedRAMP 3PAO organizations review the automated validations, verifying data accuracy, completeness, and evidence traceability.

- **Continuous Compliance Reporting**  
  Results are generated regularly and stored in secure JSON report files, enabling ongoing monitoring and rapid identification of security gaps.

---

## JSON File Structure and Role

The KSI validation results are captured in a standardized JSON format including these key elements:

- **Provider Information**  
  Details about the cloud service provider and the specific service offering.

- **Approach Summary**  
  Description of the automated and manual methods used to collect and validate evidence, including coverage percentage of automation.

- **Third-Party Assessment Summary**  
  Notes and verification statements from the 3PAO auditor, including dates and reviewer identity.

- **Assessment Data**  
  - `report_timestamp`: When the report was generated.  
  - `ksi_validations`: An array of objects, each representing a specific KSI control with:  
    - `ksi_id` and `description`: Define the control.  
    - `status`: (`True` or `False`) indicating if the control passed validation.  
    - `method`: Explains if validation is automated or manual.  
    - `validation_criteria`: Lists underlying requirements.  
    - `evidence`: Contains the query (`query_language` and `query`) and a human-readable explanation (`query_nlp`) of what the query checks.  
    - `3pao_verification`: Confirms independent verification of the evidence.

- **Continuous Reporting Proposal**  
  Description of how continuous compliance will be maintained through secure pipelines and integration hooks.

---

## Summary

Together, the FedRAMP KSI controls and their associated JSON validation reports form a rigorous, automated, and transparent framework. They enable cloud providers to continuously demonstrate that their environments are secure and compliant, while auditors and stakeholders can easily review, verify, and understand the security posture through structured, human-readable data.

---

*For questions or support, please contact the compliance team or visit the [JupiterOne FedRAMP repository](https://github.com/JupiterOne/).*

Notes:
File structure is

ksi-{control}-{type}

Control Family KSI found at https://github.com/FedRAMP/rfcs/discussions/18 and https://www.fedramp.gov/20x/phase-one/

Prior draft contained either md/markdown, yaml, or json.

Relevant FedRAMP GitHub links.

https://github.com/OSCAL-Foundation/OSCAL-Foundation/blob/main/content/catalog/json/FedRAMP%20RFC-0006%2020x%20Phase%20One%20Key%20Security%20Indicators.json

https://github.com/FedRAMP/community/discussions/
