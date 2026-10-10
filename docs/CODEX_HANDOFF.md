# Codex Handoff: Open Journal Systems (OJS) Project

## Project Overview
This repository contains the source code for an Open Journal Systems (OJS) deployment. The repository is prepared specifically for audit, refactoring, and further development by OpenAI Codex.

**OJS Version:** 3.5.0.4

## Folder Structure
The repository retains the standard OJS structure. Important directories include:
- `classes/`: Core application logic, DAOs, and service classes.
- `controllers/`: User Interface controllers handling grid and modal interactions.
- `pages/`: Page routing and handlers.
- `plugins/`: System plugins including themes, blocks, and gateways.
  - `plugins/themes/`: Contains the visual themes. Look here for UI customizations.
- `templates/`: Smarty template files (.tpl) used to render the frontend and backend UI.
- `lib/pkp/`: (If present as submodule/directory) The Public Knowledge Project core library shared across their applications.

## Customization Locations
- **Themes & Plugins:** Any visual modifications, custom blocks, or specific feature additions requested by the user will likely reside within the `plugins/` directory, especially under `plugins/themes/`.
- **Core Modifications:** Check `classes/` and `controllers/` for any hardcoded logic changes.

## Development Environment & Dependencies
- **Language:** PHP 8.0+ (typical for OJS 3.3/3.4/3.5).
- **Database:** MySQL/MariaDB or PostgreSQL (credentials are omitted from this repo for security).
- **Frontend Dependencies:** Node.js/NPM (see `package.json` if available) and Vue.js (used extensively in the OJS backend).
- **Backend Dependencies:** Composer (see `composer.json` for PHP libraries).

## Areas for Codex Audit
The following areas have NOT been deeply examined during the initial upload and require your detailed audit:
1. **Security & Vulnerabilities:** Check custom plugins and theme files for XSS, SQLi, and secure data handling.
2. **Code Quality:** Refactor any hastily written customizations or hardcoded patches.
3. **Best Practices:** Ensure any modifications adhere to the OJS plugin architecture rather than hacking core files directly.
4. **Performance:** Audit custom queries and frontend asset loading.

## Security Notes & Limitations
- **Sensitive Data Excluded:** The production `config.inc.php` file, production database (`*.sql`), uploaded user manuscripts (`files/` and `ojs_files/`), and cache/logs have been explicitly excluded via `.gitignore`.
- **Secrets check:** While `.gitignore` is in place, always be mindful if any API keys or credentials were accidentally hardcoded into template files (`*.tpl`) or custom plugins. 
- **Modifications:** Since no functional changes were made during this upload process, all existing bugs or architectural flaws are untouched and should be reported to the user.

---
*Generated for Codex Handoff.*
