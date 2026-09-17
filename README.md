# Personal Health Record Sync

A personal, read-only application that copies one patient's own records from
the Epic patient-access FHIR R4 API (the same data shown in MyChart) into a
local database on that patient's own computer. It is used by its author only.

- Audience: patients. Read-only. No data is sent anywhere; nothing is shared.
- Authorization: SMART App Launch standalone launch with PKCE. The patient logs
  in through MyChart and can revoke access at any time from MyChart settings.
- Client authentication: asymmetric (JWT client assertion, RS384). The public
  JSON Web Key Set is served from this repository at
  `https://jschuller.github.io/fhir-jwks/jwks.json`. It contains public keys
  only; the private key never leaves the machine that generated it.
- Data requested: USCDI v3 resources only (Patient, Observation, DiagnosticReport,
  DocumentReference and Binary, Encounter, Condition, MedicationRequest,
  Procedure, Immunization, AllergyIntolerance).

Contact: the repository owner via GitHub.

Sandbox key set (Epic non-production, separate key): `https://jschuller.github.io/fhir-jwks/sandbox/jwks.json`
