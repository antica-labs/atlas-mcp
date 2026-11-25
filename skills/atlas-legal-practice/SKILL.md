---
name: atlas-legal-practice
description: Gestion de cabinet d'avocats, dossiers contentieux et conseil, calendrier procédural, diligences, facturation, expertises judiciaires (Opalexe) et sous-comptes CARPA via le serveur MCP officiel d'ATLAS Legal (www.atlas-legal.lu).
---

# ATLAS Legal — Gestion de Cabinet d'Avocats & Pratique Juridique (MCP)

Utilisez cette compétence pour analyser et consulter les dossiers, clients, échéances procédurales, diligences, factures, expertises judiciaires et sous-comptes CARPA d'un cabinet d'avocats sur **ATLAS Legal** (`https://www.atlas-legal.lu`).

## Authentification & Sécurité

Le serveur MCP ATLAS Legal (`https://www.atlas-legal.lu/api/mcp`) supporte :
1. **OAuth 2.1 + PKCE (`S256`) + CIMD** via `https://www.atlas-legal.lu/.well-known/oauth-authorization-server`.
2. **Bearer Token (`atlas_sk_live_...`)** généré depuis l'espace cabinet ATLAS Legal.
Toutes les données sont cloisonnées par cabinet (`tenant_id`) sous Row-Level Security (RLS) et l'ensemble des 12 outils sont en **lecture seule stricte** (`readOnlyHint: true`, `destructiveHint: false`, `openWorldHint: false`).

## Les 12 Outils MCP ATLAS Legal (`readOnlyHint: true`)

- `get_cabinet_summary` : Synthèse de l'activité du cabinet (informations du cabinet, compteurs de dossiers actifs, clients particuliers et personnes morales, échéances procédurales, factures émises).
- `list_dossiers` : Liste paginée des dossiers juridiques et contentieux du cabinet (référence, intitulé, catégorie, nature de mission, statut, profil LCB-FT, avancement).
- `get_dossier_details` : Fiche détaillée d'un dossier par `dossierId` ou référence interne, incluant ses échéances procédurales et ses factures rattachées.
- `list_clients` : Liste paginée des clients particuliers et personnes morales (dénomination, forme juridique, juridiction, numéro d'immatriculation).
- `list_deadlines` : Calendrier des échéances procédurales, audiences de plaidoirie, mises en état et délais de rigueur.
- `list_diligences` : Liste paginée des diligences juridiques et temps passés par dossier (libellé, catégorie d'acte, durée en minutes, montant HT/TTC).
- `list_bills` : Liste paginée des factures d'honoraires et notes de frais émises par le cabinet.
- `list_judicial_expertises` : Suivi des missions d'expertise judiciaire (référence interne, numéro RG, référence Opalexe/Net-Expert, juridiction, expert désigné, statut).
- `list_carpa_accounts` : Situation des sous-comptes affaires CARPA et séquestres du cabinet (caisse CARPA, numéro d'affaire, nature des fonds, solde disponible).
- `list_documents` : Métadonnées des pièces, actes, conclusions et documents juridiques scellés SHA-256 du cabinet.
- `search` : Recherche transversale par mots-clés dans les dossiers, clients et échéances procédurales.
- `fetch` : Extraction détaillée d'un élément ATLAS par identifiant (`dossier:<id>`, `client:<id>`, `deadline:<id>`).
