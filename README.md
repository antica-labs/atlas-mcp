# ATLAS Legal — Official B2A & Enterprise MCP Connector (`v1.2.0`)

European law firm practice governance connector for ATLAS Legal (atlas-legal.lu): litigation readiness, procedural deadlines, conflict clearance, CARPA escrow reconciliation, and Bar counsel sign-off.

## Sovereign Endpoints & Discovery
| Surface | URL |
| :--- | :--- |
| **MCP Streamable HTTP** | `https://atlas-legal.lu/api/mcp` |
| **MCP Discovery & SLA Beacon** | `https://atlas-legal.lu/.well-known/mcp.json` |
| **Perplexity Connector Manifest** | `https://atlas-legal.lu/.well-known/mcp-connector.json` |
| **A2A Agent Card** | `https://atlas-legal.lu/.well-known/agent-card.json` |
| **OAuth 2.1 Protected Resource (RFC 9728)** | `https://atlas-legal.lu/.well-known/oauth-protected-resource` |
| **OAuth 2.1 Authorization Server (RFC 8414)** | `https://atlas-legal.lu/.well-known/oauth-authorization-server` |
| **OpenAPI 3.1.0 Spec** | `https://atlas-legal.lu/openapi.json` |
| **Agent Index (`llms.txt`)** | `https://atlas-legal.lu/llms.txt` |

## Primary `Output-First` Tools
- `consolidate_practice_governance_kpi`: Consolidates cabinet-wide active matters, procedural deadlines, billing velocity, and LCB-FT posture.
- `audit_litigation_matter_readiness`: Audits a specific legal matter's evidentiary completeness, KYC status, and next procedural milestone.
- `verify_procedural_deadline_compliance`: Computes statutory procedural deadlines, foreclosure risks, and hearing readiness verdicts.
- `reconcile_billable_and_carpa_ledger`: Reconciles recorded diligences, fee invoices, Factur-X disbursements, and CARPA escrow balances.
- `validate_conflict_of_interest_clearance`: Screens parties and counterparties for ethical conflict-of-interest clearance under tenant RLS.
- `stage_bar_counsel_human_escalation`: Zero-cost (0 EUR) B2A2H escalation staging a pre-sealed dossier for Bar counsel sign-off.
- `search`: Canonical search across dossiers, procedural deadlines, and sealed cabinet metadata.
- `fetch`: Canonical retrieval of a tenant-isolated dossier, deadline, or CARPA ledger record.

## Guarantees
- **Zero Data Retention (`ZDR`)**: `X-Data-Retention: zero`, `X-Training-On-Payloads: false`, EU sovereign processing (`EU-FR-LU`).
- **AST Prompt-Injection Defense**: 6-layer deterministic sanitizer (`X-Prompt-Injection-Sanitized: ast-v2`).
- **Cryptographic Opposability**: `SHA-256` payload digest + dual qualified `RFC 3161` timestamps + `0,00 EUR` counterparty verification at `https://atlas-legal.lu/verify/<proof_id>`.
