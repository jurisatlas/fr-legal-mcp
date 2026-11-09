# France Legal Research MCP Server (`fr-legal-mcp`)

**[Français](#lang-fr) | [English Documentation](#english-documentation)**

---

<a id="lang-fr"></a>
## Serveur MCP de Législation et Jurisprudence (`fr-legal-mcp`) — Français

### À propos de ce dépôt

Ce dépôt fournit un serveur Model Context Protocol (MCP) reliant directement votre application d'intelligence artificielle (Claude Desktop, Cursor, Windsurf, VS Code / Copilot, Cline, Continue.dev ou Antigravity) aux portails législatifs officiels et aux bases de jurisprudence multi-niveaux pour **France** (juridictions de première instance, tribunaux cantonaux / cours d'appel et juridictions suprêmes ou constitutionnelles).

### Installation rapide (Sélection de votre client IA)

1. **Téléchargement :** Cliquez sur **`<> Code` -> `Download ZIP`** en haut à droite et extrayez le dossier sur votre ordinateur.
2. **Lancement de l'assistant :** Double-cliquez sur **`Click_Here_To_Install_Windows.bat`** (Windows) ou **`Click_Here_To_Install_Mac.command`** (macOS).
3. **Choix de l'application IA :** Cochez les applications IA que vous utilisez (Claude, Cursor, Windsurf, VS Code, Antigravity), lancez l'installation automatique et redémarrez votre application IA.

**Note de sécurité :** L'utilitaire fonctionne exclusivement en lecture seule (read-only) et n'accède à aucun fichier personnel sur votre ordinateur.

### Hiérarchie juridictionnelle et sources officielles

| Degré de juridiction | Juridictions couvertes |
|:---|:---|
| **1er degré (Première instance)** | Tribunaux judiciaires (TJ), Tribunaux de commerce, Conseils de prud'hommes & Tribunaux administratifs (TA) |
| **2nd degré (Juridictions cantonales, régionales et cours d'appel)** | 36 Cours d'appel (CA — Open Data Judilibre CA) & 9 Cours administratives d'appel (CAA) |
| **Juridictions suprêmes et constitutionnelles** | Cour de cassation, Conseil d'État & Conseil constitutionnel |

- **Légifrance (legifrance.gouv.fr) & Data.gouv.fr LEGI:** [https://www.legifrance.gouv.fr](https://www.legifrance.gouv.fr) (`legifrance.gouv.fr`, `assemblee-nationale.fr`, `senat.fr`)
- **Judilibre API (Cour de cassation, 36 Cours d'appel & Tribunaux judiciaires) + ArianeWeb (TA/CAA/CE):** [https://www.courdecassation.fr/recherche-judilibre](https://www.courdecassation.fr/recherche-judilibre) (`courdecassation.fr`, `conseil-etat.fr`, `conseil-constitutionnel.fr`, `legifrance.gouv.fr`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **France (FR)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **France**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | Tribunaux judiciaires (TJ), Tribunaux de commerce, Conseils de prud'hommes & Tribunaux administratifs (TA) |
| **Tier 2 — Regional / Cantonal / Appellate** | 36 Cours d'appel (CA — Open Data Judilibre CA) & 9 Cours administratives d'appel (CAA) |
| **Tier 3 — Supreme & Constitutional** | Cour de cassation, Conseil d'État & Conseil constitutionnel |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** Légifrance (legifrance.gouv.fr) & Data.gouv.fr LEGI — [https://www.legifrance.gouv.fr](https://www.legifrance.gouv.fr)
  - *Indexed Legislation Domains:* `legifrance.gouv.fr`, `assemblee-nationale.fr`, `senat.fr`
- **Court Decisions & Jurisprudence Archives:** Judilibre API (Cour de cassation, 36 Cours d'appel & Tribunaux judiciaires) + ArianeWeb (TA/CAA/CE) — [https://www.courdecassation.fr/recherche-judilibre](https://www.courdecassation.fr/recherche-judilibre)
  - *Indexed Judicial & Open Case Law Domains:* `courdecassation.fr`, `conseil-etat.fr`, `conseil-constitutionnel.fr`, `legifrance.gouv.fr`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in France. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for France. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for France. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "fr-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/fr-legal-mcp/archive/refs/heads/main.zip",
        "fr-legal-mcp"
      ]
    }
  }
}
```
</details>
