# Privacy Policy, Data Residency & Security Statement — Jira Quota & Limit Radar

**Effective Date**: October 14, 2026  
**Publisher**: EvidencePair LLC  
**App Key**: `com.evidencepair.jira.limit.radar`  
**App ID**: `ari:cloud:ecosystem::app/29570e2c-492a-461e-b5fc-ce8b493a1e8f`

---

## 1. Zero Data Egress & Architecture Statement ("Runs on Atlassian")

**Jira Quota & Limit Radar** executes 100% inside Atlassian's managed Forge Cloud runtime (`nodejs24.x`) and declares **zero external remote endpoints (`remotes:`)** and **zero external egress permissions**.

- **0 Bytes External Storage**: EvidencePair LLC does not operate any external servers, databases, or telemetry endpoints that receive customer data from Jira Quota & Limit Radar.
- **100% Native Jira Entity Property Storage (<32 KB Enforced)**:
  - Guardrail scan summaries are stored exclusively inside your Jira instance's **Project Properties** (`/rest/api/3/project/{projectId}/properties/limitRadarSummary`).
  - Pre-change custom field option rollback snapshots and SHA-256 signatures are stored exclusively inside your Jira instance's **Project Properties** (`/rest/api/3/project/{projectId}/properties/limitRadarBackup_{fieldId}`).
  - Zero Forge SQL and Zero Forge KVS storage are used.

---

## 2. Data Residency & Compliance Inheritance

Because Jira Quota & Limit Radar stores 100% of its telemetry and rollback vault snapshots within native Jira Project Properties:
- **Automatic Data Residency**: All app data automatically resides in the exact geographic region (US, EU, AU, DE, SG, CA, UK, JP, etc.) configured for your host Jira Cloud product under Atlassian Data Residency.
- **Lifecycle & Deletion**: All app properties are automatically included in standard Jira Cloud backups and are permanently deleted when the host project or property is deleted by your administrator.

---

## 3. Privacy Policy (GDPR / CCPA / SOC 2 Alignment)

### Personal Data Processed
To provide cryptographic attribution in the SHA-256 Rollback Vault, Jira Quota & Limit Radar records:
- **Atlassian Account ID (`accountId`)** of the administrator initiating a bulk option disable action.
- **ISO-8601 UTC Timestamp (`timestamp`)** and custom field option metadata (`id`, `value`, `disabled`).

### How Personal Data Is Used
- Processed solely within the Atlassian Forge runtime to compute a deterministic SHA-256 integrity signature (`accountId|fieldId|contextId|timestamp|optionsJson`).
- Never transmitted outside your Atlassian Cloud tenant, never sold, and never shared with third parties.

### Data Subject Rights (Access, Rectification, Erasure)
Organization administrators have full read/write/delete control over all Jira Quota & Limit Radar properties via standard Jira REST v3 APIs:
- `GET` / `DELETE /rest/api/3/project/{projectIdOrKey}/properties/limitRadarSummary`
- `GET` / `DELETE /rest/api/3/project/{projectIdOrKey}/properties/limitRadarBackup_{fieldId}`

---

## 4. Security Contact
Security inquiries or vulnerability reports may be submitted to **EvidencePair LLC** at `support@titlecovenant.com`.
