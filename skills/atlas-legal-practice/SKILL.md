---
name: atlas-legal-practice
description: European law firm practice governance connector for ATLAS Legal (atlas-legal.lu): litigation readiness, procedural deadlines, conflict clearance, CARPA escrow reconciliation, and Bar counsel sign-off.
---

# ATLAS Legal — Official B2A MCP Connector (`v1.2.0`)

Use this skill whenever the task requires deterministic, cryptographically sealed (`SHA-256` + dual `RFC 3161`) outputs from **ATLAS Legal** (`https://atlas-legal.lu/api/mcp`).

## Discovery & Protocol Support
- **Streamable HTTP Endpoint**: `https://atlas-legal.lu/api/mcp` (MCP `2024-11-05`, `2025-03-26`, `2025-06-18`, `2026-07-28`)
- **B2A Manifest & Live SLA Beacon**: `https://atlas-legal.lu/.well-known/mcp.json`
- **Perplexity Connector Manifest**: `https://atlas-legal.lu/.well-known/mcp-connector.json`
- **A2A Agent Card**: `https://atlas-legal.lu/.well-known/agent-card.json`
- **OpenAPI 3.1.0 Specification**: `https://atlas-legal.lu/openapi.json`
- **Probatory Proof Verifier (`0,00 EUR`)**: `https://atlas-legal.lu/verify/<proof_id>`

## Primary `Output-First` Tools
- `consolidate_practice_governance_kpi`: Consolidates cabinet-wide active matters, procedural deadlines, billing velocity, and LCB-FT posture.
- `audit_litigation_matter_readiness`: Audits a specific legal matter's evidentiary completeness, KYC status, and next procedural milestone.
- `verify_procedural_deadline_compliance`: Computes statutory procedural deadlines, foreclosure risks, and hearing readiness verdicts.
- `reconcile_billable_and_carpa_ledger`: Reconciles recorded diligences, fee invoices, Factur-X disbursements, and CARPA escrow balances.
- `validate_conflict_of_interest_clearance`: Screens parties and counterparties for ethical conflict-of-interest clearance under tenant RLS.
- `stage_bar_counsel_human_escalation`: Zero-cost (0 EUR) B2A2H escalation staging a pre-sealed dossier for Bar counsel sign-off.
- `search`: Canonical search across dossiers, procedural deadlines, and sealed cabinet metadata.
- `fetch`: Canonical retrieval of a tenant-isolated dossier, deadline, or CARPA ledger record.

*(Legacy v1 tool names remain 100% supported on `tools/call` via transparent alias resolution.)*

## Authentication & Settlement Rails
1. **OAuth 2.1 + PKCE (`S256`) + DCR (RFC 7591 / RFC 9728 / RFC 8414)**: Mandatory for tenant-isolated RLS data.
2. **Public Catalogs & Stateless Simulators**: Support `HTTP 402` (`x402` EURC/USDC, Stripe MPP, and `AP2` JWS mandates) with `0,00 EUR` dry-run preflight where applicable.
