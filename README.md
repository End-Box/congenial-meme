# Green Gage HubSpot Theme (CLI)

A calm, editorial HubSpot CMS theme built with HubL templates and custom modules.

## Project identity

- Project name: `greengages-theme`
- Project reference: `@project/greengages-theme`
- HubSpot platform version: `2026.03`

## Local workflow

1. Authenticate HubSpot CLI.
2. Upload from the project root with projects framework commands:

```bash
hs project upload
```

## Structure

- `src/theme/greengages-theme-hsmeta.json`: theme component config for projects framework.
- `src/theme/greengages-theme/`: actual HubSpot theme folder containing:
  - `templates/`: page templates and shared base layout.
  - `partials/`: shared fragments and macros.
  - `modules/`: reusable custom modules with fields/meta/html/css.
  - `css/`: base/components/utilities style architecture.
  - `js/` and `assets/`: static/supporting files.
  - `fields.json`: theme settings.
  - `theme.json`: theme manifest.
- `hsproject.json`: CLI project metadata.

## Refactor notes

- Shared link resolution logic is centralized in `partials/macros/link-utils.html`.
- Shared section attribute logic is centralized in `partials/macros/section-utils.html`.
- Repeated nav rendering is centralized in `partials/nav-list.html`.
- Flow spacing utilities (`flow-sm`, `flow-md`, `flow-lg`) replace repeated inline spacing values.

## Header menu language setup (HubSpot)
1. In HubSpot, go to **Website > Navigation**.
2. Create two menus: **Green Gage’s Header FR** and **Green Gage’s Header EN**.
3. In each language variation of the Site Header global partial, configure the single `Header navigation` module with the corresponding menu.
4. Keep the website and blog pages attached to their published multilingual variants; the native language switcher derives its labels and destinations from those relationships.
5. Website and blog templates inherit this global partial from the base layout, so do not add a separate menu module to either blog template.
