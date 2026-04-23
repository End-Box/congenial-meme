# Green Gage HubSpot Theme (CLI)

A calm, editorial HubSpot CMS theme built with HubL templates and custom modules.

## Local workflow

1. Authenticate HubSpot CLI.
2. Upload/watch this folder:

```bash
hs upload . <portal_name>/green-gage-theme
hs watch . <portal_name>/green-gage-theme
```

## Structure

- `templates/`: page templates and shared base layout.
- `partials/`: shared fragments (`header`, `footer`, and `nav-list`) plus macros.
- `modules/`: reusable custom modules with fields/meta/html/css.
- `css/`: base/components/utilities style architecture.
- `fields.json`: theme settings.
- `theme.json`: theme manifest.
- `hsproject.json`: CLI project metadata.

## Refactor notes

- Shared link resolution logic is centralized in `partials/macros/link-utils.html`.
- Shared section attribute logic is centralized in `partials/macros/section-utils.html`.
- Repeated nav rendering is centralized in `partials/nav-list.html`.
- Flow spacing utilities (`flow-sm`, `flow-md`, `flow-lg`) replace repeated inline spacing values.
