# ATLAS Legal — Plugin Google Antigravity & MCP

Connectez **ATLAS Legal** (`https://www.atlas-legal.lu`), la plateforme européenne de gestion de cabinet d'avocats (dossiers contentieux et conseil, clients, calendrier procédural, diligences, facturation, expertises judiciaires Opalexe et sous-comptes CARPA), directement à votre agent IA.

## Installation & Authentification OAuth 2.1

1. **OAuth 2.1 + PKCE (`S256`) + CIMD** : À la première requête, votre client IA ouvre l'écran sécurisé `https://www.atlas-legal.lu/api/oauth/authorize`.
2. **Clé API MCP** : Vous pouvez vous authentifier avec vos identifiants cabinet ou votre clé API `atlas_sk_live_...`.

## Les 12 Outils MCP (`readOnlyHint: true`)

- `get_cabinet_summary`, `list_dossiers`, `get_dossier_details`, `list_clients`, `list_deadlines`, `list_diligences`, `list_bills`, `list_judicial_expertises`, `list_carpa_accounts`, `list_documents`, `search`, `fetch`.
