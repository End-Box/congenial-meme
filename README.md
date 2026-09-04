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
3. In the Site Header global content, configure the `Contextual Header Navigation` fields: `Main English menu`, `Main French menu`, `Blog English menu`, and `Blog French menu`.
4. The header explicitly resolves `main_en`, `main_fr`, `blog_en`, or `blog_fr`; an unconfigured field renders no public fallback menu rather than HubSpot placeholder links.
5. The language switcher uses fixed `English` and `Français` labels and canonical main-site or blog-listing destinations.
