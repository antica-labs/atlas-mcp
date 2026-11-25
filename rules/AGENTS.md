---
description: Règles de confidentialité, d'isolation par cabinet (RLS) et de lecture seule lors de l'utilisation du serveur MCP ATLAS Legal.
---

# Règles d'utilisation du connecteur MCP ATLAS Legal

1. **Lecture Seule & Confidentialité du Cabinet** : Les 12 outils du serveur MCP ATLAS Legal (`https://www.atlas-legal.lu/api/mcp`) opèrent en lecture seule stricte (`readOnlyHint: true`) dans le périmètre du cabinet authentifié (`tenant_id`).
2. **Exactitude des Références** : Citez toujours la référence exacte du dossier (`reference`), la juridiction et la date d'échéance procédurale retournées par `list_dossiers`, `get_dossier_details` ou `list_deadlines`.
3. **Sous-comptes CARPA & Facturation** : Lors de l'analyse des sous-comptes CARPA (`list_carpa_accounts`) ou des factures (`list_bills`), indiquez systématiquement le numéro d'affaire et le statut officiel sans jamais proposer de décaissement automatisé.
