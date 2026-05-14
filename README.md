# Green Gage HubSpot Theme (CLI)

A calm, editorial HubSpot CMS theme built with HubL templates and custom modules.

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
3. In global content for the Site Header partial, configure `Header Menu FR` and `Header Menu EN` modules.
4. The header auto-selects EN on `/en` pages and FR otherwise.
5. If blog URL includes `/fr/thegreengage`, that path is controlled by HubSpot Blog multilingual settings (not hardcoded in theme templates).
