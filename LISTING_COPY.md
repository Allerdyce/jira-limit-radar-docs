# Atlassian Marketplace Partner Listing Copy — Jira Quota & Limit Radar

## App Identity
- **App Name**: Jira Quota & Limit Radar — Guardrail Scanner, Orphan Option Auditor & SHA-256 Rollback Vault
- **App Key**: `com.evidencepair.jira.limit.radar`
- **App ID**: `ari:cloud:ecosystem::app/29570e2c-492a-461e-b5fc-ce8b493a1e8f`
- **Vendor**: EvidencePair LLC
- **Category**: Admin Tools / Custom Fields / Governance & Compliance
- **Runs on Atlassian Badge Eligibility**: **100% Eligible** (Native Forge `nodejs24.x`, Zero Remotes, Zero Data Egress)

---

## 80-Character Tagline / Summary
> Scan Jira guardrails, detect 0-usage field options & bulk-disable with rollback.
*(80 characters)*

---

## Full Marketplace Description

### Prevent Jira Custom Field Option Limit Outages Before They Break Your Workflows

Enterprise Jira Cloud tenants silently accumulate thousands of custom fields, contexts, and select list options—until a critical custom field context hits Atlassian's **10,000-option guardrail** and blocks admins and automation rules.

**Jira Quota & Limit Radar** gives Jira and JSM administrators proactive visibility into Atlassian Cloud limits, automatic JQL zero-usage option detection, and a 1-click SHA-256 rollback vault—built 100% on Atlassian Forge (`nodejs24.x`) with **zero external servers** and **zero data egress**:

1. **Atlassian Cloud Quota & Guardrail Scanner (`jira:adminPage` & `jira:projectPage`)**:
   - Monitor custom field options per context (`10,000` limit), contexts per field (`100` limit), total custom fields (`1,200` limit), workflow statuses (`400` limit), and issue security levels (`100` limit) in real time.
2. **Orphan & Zero-Usage Option Detector (`/rest/api/3/search/jql`)**:
   - Audits custom select field options via live JQL count queries (`cf[id] = "Option Value"`) to identify orphan options with **0 associated work items** while protecting active options in use.
3. **1-Click Safe Bulk Disable & SHA-256 Rollback Vault**:
   - Computes a deterministic **SHA-256 cryptographic signature** (`accountId|fieldId|contextId|timestamp|optionsJson`) and stores the pre-change option snapshot in native Jira Project Properties (`limitRadarBackup_{fieldId}`) before bulk-disabling unused options.
   - Restore previous option states in **1 click** with full cryptographic tamper verification (`SHA-256 VERIFIED`).

---

## Key Features Checklist
- [x] Real-time Atlassian Cloud guardrail utilization dashboard (`HEALTHY`, `WARNING`, `CRITICAL`)
- [x] Live `/rest/api/3/search/jql` zero-usage custom field option detector
- [x] Safe 1-click bulk disable (`disabled: true`) that preserves historical issue integrity
- [x] Deterministic SHA-256 Rollback Vault with 1-click restore
- [x] 100% Host Entity Property persistence (`<32 KB` enforced per key, zero Forge SQL/KVS, automatic Data Residency inheritance)
