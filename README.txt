eMANDEVAL Future v3.0.0

A fully upgraded decision aid for vaccine mandate design across Australia, France and Italy.

---
WHAT IS NEW IN v3.0.0
---

Workflow and navigation
- Five-step workflow stepper shows progress through Settings, Configuration, Costing, Results and Export
- Step tabs are numbered and labelled to match the stepper
- "Next: enter costs" and "Next: view results" navigation buttons guide first-time users
- Empty-state panels in Configuration and Results tabs replace passive "Pending" labels

Change detection and apply-all
- Tool detects when form inputs have changed but have not yet been applied
- Yellow unapplied-changes banner appears at the top with a one-click "Apply all and update results" button
- Dismiss button allows the banner to be closed without applying changes

Permalink and share link
- "Share link" button in the header encodes the current configuration and settings as a URL hash
- Pasting the link into a new browser tab restores the configuration automatically
- URL hash updates whenever configuration is applied

In-situ AI briefing generation
- Optional "Generate with AI" panel in the Briefings tab
- Enter your own Anthropic API key (stored in the browser session only, not saved to disk)
- Generates single-scenario briefings and comparative policy memos using Claude
- API key field is session-only for security; the key is never sent anywhere other than the Anthropic API
- Prompt templates are still available for copy-paste into Copilot or ChatGPT as before

Sensitivity tornado chart
- Horizontal bar chart in the Results tab shows which inputs most influence the benefit-cost ratio
- Each bar shows the BCR range when that input is varied by 20 percent (or low/central/high for lives saved)
- Bars are sorted by range width so the most influential inputs appear at the top

Print and PDF export
- "Print / Export PDF" button in the Results tab opens the browser print dialogue
- Print stylesheet hides navigation, banners, form tabs and buttons
- Results tab content is formatted cleanly for print and PDF export

Accessible traffic lights
- Status chips now include text icons (check mark, exclamation mark, cross) alongside colour coding
- Aria-labels on traffic-stripe segments describe support and BCR levels for screen readers
- Colour is no longer the sole means of conveying status

Configurable thresholds
- New section in the Settings tab lets users adjust support and BCR thresholds
- Defaults are 50 percent and 70 percent for support and 0.8 and 1.0 for BCR
- Thresholds are saved in localStorage and persist across sessions

Costing input guidance
- Cost input fields show placeholder text indicating typical magnitudes
- A hint banner prompts users to load evidence-based defaults before entering manual figures
- Tooltip text updated to include typical per-million-population ranges

MRS plain-language explainer
- A shaded explainer block above the MRS table explains how to read positive and negative values
- MRS table values are colour-coded: red for positive (less preferred), green for negative (more preferred)

Improved presentation mode
- Entering presentation mode now navigates automatically to the Results tab
- Presentation mode hides the unapplied-changes banner

Equity notes in exports
- Equity groups, sectors and concerns are saved with each scenario
- Equity notes are included in Word export briefings

Version and code quality
- Version bumped to v3.0.0
- Stylesheet consolidated into a single clean file (removed layered v2.2.0 and v2.3.0 override blocks)
- All CSS variables and design tokens unified

---
FILES
---

- index.html             Main tool interface
- styles.css             Consolidated stylesheet (v3.0.0)
- script.js              Application logic (v3.0.0)
- technical-appendix.html  Statistical and methodological appendix (unchanged)
- README.txt             This file

---
VALIDATION
---

- HTML parsed successfully (no syntax errors)
- JavaScript syntax checked successfully (Node.js --check)
- No em dash or en dash characters in user-facing text
- No external dependencies beyond Chart.js (loaded from CDN)

---
DEPLOYMENT
---

Upload all files together to your GitHub Pages repository root, or replace the existing deployed files with these versions. No build step or server is required. The tool runs entirely in the browser.

Note on the AI generate feature:
The in-situ AI briefing generation requires an Anthropic API key entered by each user. The key is stored only in the browser session (sessionStorage) and is never logged or transmitted except to the Anthropic API at api.anthropic.com. If you prefer not to use this feature, simply ignore the API key field in the Briefings and AI tab. The prompt template copy-paste workflow continues to function without any API key.
