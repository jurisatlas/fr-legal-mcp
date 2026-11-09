---
name: fr-legal-mcp-skill
description: Official France (FR) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# France Legal Research & Multi-Tier Case Law Skill (`fr-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **France (FR)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:FR:CCASS:2024:C100123 or Code civil art. 1240`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** Tribunaux judiciaires (TJ), Tribunaux de commerce, Conseils de prud'hommes & Tribunaux administratifs (TA)
   - **Second Instance (Cantonal / Regional / Appellate):** 36 Cours d'appel (CA — Open Data Judilibre CA) & 9 Cours administratives d'appel (CAA)
   - **Supreme & Constitutional Instance:** Cour de cassation, Conseil d'État & Conseil constitutionnel
   - **Primary Tiered Database:** Judilibre API (Cour de cassation, 36 Cours d'appel & Tribunaux judiciaires) + ArianeWeb (TA/CAA/CE) (`https://www.courdecassation.fr/recherche-judilibre`)
