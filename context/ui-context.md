# UI Context

Read when touching UI. One token mapping — do not also list raw hex in another file.

## Theme

Dark only / light only / both. Colors go through CSS variables, then utilities. No raw palette classes and no hardcoded hex in components.

| Role | CSS variable | Utility | Notes |
| --- | --- | --- | --- |
| Page background |  |  |  |
| Surface |  |  |  |
| Primary text |  |  |  |
| Brand |  |  |  |

New colors: add the variable first, then use the utility.

## Typography

| Role | Font | CSS variable |
| --- | --- | --- |
| UI |  |  |
| Display |  |  |
| Mono |  |  |

## Radius and spacing

| Context | Class / token |
| --- | --- |
| Controls |  |
| Cards |  |
| Overlays |  |

## Layout patterns

- App shell:
- Navbar:
- Empty states: short muted text, optional icon, CTA if there is a next action.

## Component library

Where primitives live. Do not restyle generated foundation files.

## Do nots

- A reference image wins over this file for layout and color.
- Do not invent a second visual direction.
- Icon-only buttons need an accessible name. Visible focus on every control.
