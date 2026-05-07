\# Claude Project Instructions – Page Builder Sprint (TDS)

You are building an internal \*\*page builder\*\* experience for Instacart tooling surfaces (e.g., flyers, marketing pages, builder tools). The UI must look and behave like it was built with the \*\*Tooling Design System (TDS)\*\*.

\#\# 1\. Overall Principles

\- Target: \*\*desktop web, enterprise tooling\*\* (high information density, not marketing/landing pages).  
\- Use \*\*TDS components and tokens only\*\* (no custom buttons, colors, or ad-hoc nav).  
\- Favor \*\*clear hierarchy and alignment\*\*: 12-column-ish grid, consistent spacing, left-aligned content.

\#\# 2\. Standard Page Builder Layout

Assume this basic layout unless asked otherwise:

1\. \*\*Global page header\*\*  
   \- Use a TDS page header pattern (title, key actions, optional breadcrumbs).  
   \- Example actions: “Publish”, “Save draft”, “Preview”.

2\. \*\*Left rail – structure / navigation\*\*  
   \- Tree or list of \*\*sections / blocks\*\* on the page (e.g., “Hero”, “Promo grid”, “Footer”).  
   \- Use TDS navigation / list / checkbox patterns for:  
     \- Selecting a section  
     \- Reordering (up/down handles or drag affordance)  
     \- Visibility toggles (show/hide)

3\. \*\*Center – canvas\*\*  
   \- Main \*\*page preview / layout\*\* area.  
   \- Use TDS cards, grids, tables, and text/image placeholders.  
   \- Keep layout \*\*grid-aligned and data-dense\*\* (builder, not WYSIWYG marketing).

4\. \*\*Right panel – properties\*\*  
   \- Contextual properties for the selected section/block.  
   \- Use TDS form controls:  
     \- Inputs (text, number, currency)  
     \- Selects, checkboxes, radios  
     \- Segmented Switch for key toggles (e.g., “Simple / Advanced”)  
   \- Group fields with clear section titles and helper text.

\#\# 3\. Core TDS Components to Prefer

When you need a pattern, map to these first:

\- \*\*Page shell / structure\*\*  
  \- Page header → \`TDS.Page Header\` (or closest equivalent)  
  \- Tabs for modes (e.g., “Content / Layout / Settings”) → \`TDS.Tab Group\`  
  \- Overview or status summaries → KPI/status cards from TDS

\- \*\*Lists, trees, and content organization\*\*  
  \- Section list / block list → TDS list / nav / card patterns  
  \- Grouped options → cards \+ title row \+ buttons rather than ad-hoc rows

\- \*\*Forms & controls (right panel)\*\*  
  \- Text/number inputs → \`TDS.Input\` variants  
  \- Monetary fields → currency input pattern  
  \- Boolean toggles → TDS switch / Segmented Switch  
  \- Enum choices → \`TDS.Select\`, radios, or segmented switch depending on importance

\- \*\*Data & feedback\*\*  
  \- Tables (for variants, versions, or analytics) → TDS table \+ TDS pagination  
  \- Inline status → TDS marker / status chip  
  \- Errors & warnings → \`TDS.Alert\` and form error patterns

\#\# 4\. Page Builder Flow

Design flows around this mental model:

1\. \*\*Setup\*\* – choose surface / template / initial layout  
2\. \*\*Build\*\* – add/remove/reorder sections, edit content in the canvas \+ right panel  
3\. \*\*Modify\*\* – adjust layout options, targeting, variants  
4\. \*\*Preview\*\* – preview different devices / states  
5\. \*\*Publish\*\* – confirm summary and publish

Ensure each step is clearly represented with TDS components (tabs, steps, or clear headers \+ actions) rather than bespoke UI.

\#\# 5\. When in Doubt

\- If unsure which component to use, \*\*pick the closest existing TDS component\*\* and use it consistently.  
\- Do \*\*not\*\* introduce new visual styles (colors, radii, typography) when a TDS token or component exists.  
\- Prefer \*\*reuse and cohesion\*\* across the builder (same header pattern, same card pattern, same form layout) over one-off designs.  

## 6. Icons (IDS)

- All icons must come from the **official IDS/TDS icon set**, not random libraries.
- **Do not** add new icon packages (Heroicons, Material, etc.) for this project.

### 6.1 IDS Assess icon

- When an “Assess” / evaluation icon is needed, **use the existing IDS Assess icon**.
- Reuse the exact import + usage pattern already in this repo.

Implementation contract (fill these in for this project):

- Import path: `import { AssessIcon } from '@instacart/ids-core'`
- JSX usage: `<AssessIcon aria-label="Assess" />`

Claude: whenever you need an “Assess” icon, use this component and pattern instead of inventing a new icon.