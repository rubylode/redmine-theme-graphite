# Contrast

Graphite aims at WCAG 2.2 AA in light and dark: 4.5:1 for text (3:1 for large text), and 3:1 for the parts of a control that
identify it (field borders, outlines), for focus indicators and for the flags and circles in the issue list, which are graphics
beside a word that carries the same meaning.

## How it is measured

- The page check (`npm run check`) loads 29 pages in light and dark, at 1280px and 390px wide, and measures every visible
  piece of text against the colour stacked behind it. On 2026-11-02 against Redmine 7.0.2 with the Rubylode plugins mounted it
  measured 3,832 text pairs across the 58 desktop runs and 5,218 across the 58 phone runs, and found none below AA: 116 of 116
  gated runs clean. At the 16px base size every measured pair also reaches 4.5:1, so none relies on the 3:1 allowance for large text.
- The tokens, one pair at a time, below (`tokens.css` and `dark.css`). The check skips text over a gradient or an image, and it
  does not see field borders, outlines or the flags, so those are measured here. Chip colours are the mixes the stylesheet makes
  (`color-mix`), worked out on the colour of the panel or stripe they sit on. In the issue list the status and priority are
  not chips but ink text beside a circle or a flag, so the chip rows are the ones on the issue page.
- The paper grain is a noise image blended into the page, so a pixel of the page is darker than the token `--theme-page`. Text
  that sits straight on the paper (page headings, the footer, the sidebar notes of a plugin page) was measured against the
  darkest pixel of the grain in a screenshot of the sign-in page, taken at the strength the theme ships
  (`--theme-paper-grain-opacity: 0.5`). The panels, the sidebar and the table rows are opaque, so the grain does not touch the
  pairs in the tables.
- The sidebar's selected item and the buttons on hover are shaded with hatching, a gradient of thin lines at 20 to 22 percent.
  The check skips text over it, so its text is measured here on the sidebar colour. In light the lines only darken the
  background, and the ink is above 15:1 on the plain colour. In dark they lighten it, and on a pixel of a line the white ink is still
  above 7:1.

## Straight on the grained paper

| Text | Light | Dark |
|---|---|---|
| Body text | 10.19 | 8.91 |
| Secondary text | 7.71 | 7.83 |
| Muted text | 4.82 | 4.95 |
| Link | 5.37 | 4.81 |
| Red pencil text | 4.95 | 4.92 |

## Light

| Pair | Foreground | Background | Ratio |
|---|---|---|---|
| Body text on a panel | `#1f1e1b` | `#f7f4ea` | 15.15 |
| Body text on a sunken panel or stripe | `#1f1e1b` | `#ebe6d8` | 13.37 |
| Body text on a hovered row | `#1f1e1b` | `#e3e9f2` | 13.66 |
| Secondary text on a panel | `#35332e` | `#f7f4ea` | 11.47 |
| Secondary text on a sunken panel | `#35332e` | `#ebe6d8` | 10.12 |
| Muted text on a panel | `#55514a` | `#f7f4ea` | 7.17 |
| Muted text on a sunken panel or stripe | `#55514a` | `#ebe6d8` | 6.33 |
| Muted text on a hovered row | `#55514a` | `#e3e9f2` | 6.46 |
| Link on a panel | `#2e4a7d` | `#f7f4ea` | 7.98 |
| Link on a sunken panel or stripe | `#2e4a7d` | `#ebe6d8` | 7.04 |
| Link on a hovered row | `#2e4a7d` | `#e3e9f2` | 7.19 |
| White on the primary (the red pencil) | `#ffffff` | `#b2432f` | 5.62 |
| White on the primary, hovered | `#ffffff` | `#983525` | 7.31 |
| Button text | `#1f1e1b` | `#f7f4ea` | 15.15 |
| Delete button text | `#8f2f1f` | `#f8e7e2` | 6.75 |
| Overdue date and required mark (red pencil text) on a panel | `#8f2f1f` | `#f7f4ea` | 7.36 |
| Overdue date (red pencil text) on a stripe | `#8f2f1f` | `#ebe6d8` | 6.49 |
| Sidebar link | `#35332e` | `#eee9dd` | 10.42 |
| Sidebar selected item, on the paler end of its hatching | `#111111` | `#eee9dd` | 15.59 |
| Top bar links | `#35332e` | `#f1ede2` | 10.79 |
| Count badge | `#f1ede2` | `#1f1e1b` | 14.25 |
| White on the avatar grey | `#ffffff` | `#55514a` | 7.89 |
| Code block (kept light) | `#1f1e1b` | `#efebe0` | 13.99 |
| Closed or up message | `#1d5a33` | `#e5efe4` | 6.95 |
| Warning message | `#5f3f00` | `#f5ecd2` | 8.10 |
| Status block, up | `#1d5a33` | `#e3efe4` | 6.92 |
| Status block, unavailable | `#6b4400` | `#f5ecd2` | 7.26 |
| Phone menu text | `#e8e3d4` | `#2b2a27` | 11.19 |
| Chip New (issue page), on a panel | `#3b4352` | `#e2e1dc` | 7.60 |
| Chip New (issue page), on a sunken panel | `#3b4352` | `#d7d5cc` | 6.77 |
| Chip In Progress (issue page), on a panel | `#26395b` | `#dddfde` | 8.62 |
| Chip In Progress (issue page), on a sunken panel | `#26395b` | `#d3d3ce` | 7.69 |
| Chip Resolved (issue page), on a panel | `#1d4c2e` | `#dbe3d4` | 7.50 |
| Chip Resolved (issue page), on a sunken panel | `#1d4c2e` | `#d1d7c4` | 6.69 |
| Chip Feedback (issue page), on a panel | `#683f06` | `#ece0cb` | 6.99 |
| Chip Feedback (issue page), on a sunken panel | `#683f06` | `#e2d4bb` | 6.24 |
| Chip Closed (issue page), on a panel | `#3b3832` | `#e2dfd5` | 8.76 |
| Chip Closed (issue page), on a sunken panel | `#3b3832` | `#d7d3c5` | 7.80 |
| Chip Rejected (issue page), on a panel | `#6e2a1d` | `#eddbd0` | 7.78 |
| Chip Rejected (issue page), on a sunken panel | `#6e2a1d` | `#e3cfc0` | 6.93 |
| Chip High (issue page), on a panel | `#7d560b` | `#f1e5cc` | 5.24 |
| Chip High (issue page), on a sunken panel | `#7d560b` | `#e6d9bc` | 4.68 |
| Chip Urgent (issue page), on a panel | `#7c3224` | `#f0ddd1` | 6.83 |
| Chip Urgent (issue page), on a sunken panel | `#7c3224` | `#e6d1c2` | 6.10 |
| White on priority Immediate (issue page chip) | `#ffffff` | `#a63a27` | 6.45 |
| Field border on a panel (control) | `#1f1e1b` | `#f7f4ea` | 15.15 |
| Focus outline on a panel | `#1f1e1b` | `#f7f4ea` | 15.15 |
| Button outline on a panel (control) | `#1f1e1b` | `#f7f4ea` | 15.15 |
| Flag for Urgent and Immediate, on a stripe | `#8f2f1f` | `#ebe6d8` | 6.49 |
| Flag for the lower priorities, on a stripe | `#55514a` | `#ebe6d8` | 6.33 |
| Status circle outline, on a stripe | `#1f1e1b` | `#ebe6d8` | 13.37 |
| Tracker square for bugs, on a stripe | `#b2432f` | `#ebe6d8` | 4.51 |
| Sidebar pencil line, on the sidebar | `#4a4843` | `#eee9dd` | 7.54 |

## Dark

| Pair | Foreground | Background | Ratio |
|---|---|---|---|
| Body text on a panel | `#f4f1e8` | `#2f3033` | 11.68 |
| Body text on a sunken panel or stripe | `#f4f1e8` | `#2b2c2f` | 12.36 |
| Body text on a hovered row | `#f4f1e8` | `#2a3750` | 10.56 |
| Secondary text on a panel | `#e6e3d9` | `#2f3033` | 10.28 |
| Secondary text on a sunken panel | `#e6e3d9` | `#2b2c2f` | 10.87 |
| Muted text on a panel | `#b9b6ab` | `#2f3033` | 6.50 |
| Muted text on a sunken panel or stripe | `#b9b6ab` | `#2b2c2f` | 6.88 |
| Muted text on a hovered row | `#b9b6ab` | `#2a3750` | 5.87 |
| Link on a panel | `#9db4e0` | `#2f3033` | 6.31 |
| Link on a sunken panel or stripe | `#9db4e0` | `#2b2c2f` | 6.67 |
| Link on a hovered row | `#9db4e0` | `#2a3750` | 5.70 |
| White on the primary (the red pencil) | `#ffffff` | `#b2432f` | 5.62 |
| White on the primary, hovered | `#ffffff` | `#983525` | 7.31 |
| Button text | `#f4f1e8` | `#2f3033` | 11.68 |
| Delete button text | `#ffb3a3` | `#42221f` | 8.26 |
| Overdue date and required mark (red pencil text) on a panel | `#f4a090` | `#2f3033` | 6.46 |
| Overdue date (red pencil text) on a stripe | `#f4a090` | `#2b2c2f` | 6.83 |
| Sidebar link | `#d6d3c8` | `#222326` | 10.48 |
| Sidebar selected item, on the paler end of its hatching | `#ffffff` | `#222326` | 15.71 |
| Top bar links | `#d6d3c8` | `#26272a` | 9.96 |
| Count badge | `#26272a` | `#f4f1e8` | 13.22 |
| White on the avatar grey | `#ffffff` | `#6a6760` | 5.64 |
| Code block (kept light) | `#1f1e1b` | `#efebe0` | 13.99 |
| Closed or up message | `#c2f0d2` | `#173d27` | 9.63 |
| Warning message | `#ffe9b8` | `#4a3a14` | 9.23 |
| Status block, up | `#8fe0ad` | `#173d27` | 7.75 |
| Status block, unavailable | `#f0c070` | `#4a3a14` | 6.55 |
| Phone menu text | `#e8e3d4` | `#1d1e20` | 13.00 |
| Chip New (issue page), on a panel | `#d0d6e1` | `#4d5057` | 5.53 |
| Chip New (issue page), on a sunken panel | `#d0d6e1` | `#494d54` | 5.82 |
| Chip In Progress (issue page), on a panel | `#c9d6ee` | `#49505d` | 5.54 |
| Chip In Progress (issue page), on a sunken panel | `#c9d6ee` | `#464d59` | 5.81 |
| Chip Resolved (issue page), on a panel | `#b0e5c3` | `#3e564a` | 5.63 |
| Chip Resolved (issue page), on a sunken panel | `#b0e5c3` | `#3b5347` | 5.90 |
| Chip Feedback (issue page), on a panel | `#f7d8ac` | `#5d5140` | 5.66 |
| Chip Feedback (issue page), on a sunken panel | `#f7d8ac` | `#5a4e3d` | 5.93 |
| Chip Closed (issue page), on a panel | `#d6d4ce` | `#4f4f4f` | 5.53 |
| Chip Closed (issue page), on a sunken panel | `#d6d4ce` | `#4c4c4c` | 5.79 |
| Chip Rejected (issue page), on a panel | `#f6bfb3` | `#5d4643` | 5.38 |
| Chip Rejected (issue page), on a sunken panel | `#f6bfb3` | `#5a4340` | 5.63 |
| Chip High (issue page), on a panel | `#f7d8ac` | `#5d5140` | 5.66 |
| Chip High (issue page), on a sunken panel | `#f7d8ac` | `#5a4e3d` | 5.93 |
| Chip Urgent (issue page), on a panel | `#f6bfb3` | `#5d4643` | 5.38 |
| Chip Urgent (issue page), on a sunken panel | `#f6bfb3` | `#5a4340` | 5.63 |
| White on priority Immediate (issue page chip) | `#ffffff` | `#a63a27` | 6.45 |
| Field border on a panel (control) | `#cfcdc4` | `#2f3033` | 8.28 |
| Focus outline on a panel | `#f4f1e8` | `#2f3033` | 11.68 |
| Button outline on a panel (control) | `#cfcdc4` | `#2f3033` | 8.28 |
| Flag for Urgent and Immediate, on a stripe | `#f4a090` | `#2b2c2f` | 6.83 |
| Flag for the lower priorities, on a stripe | `#b9b6ab` | `#2b2c2f` | 6.88 |
| Status circle outline, on a stripe | `#f4f1e8` | `#2b2c2f` | 12.36 |
| Tracker square for bugs, on a stripe | `#ef8a74` | `#2b2c2f` | 5.69 |
| Sidebar pencil line, on the sidebar | `#cfcdc4` | `#222326` | 9.86 |

## Not covered

- Redmine's own avatar colours are replaced by one pencil grey with white initials (7.9:1 in light, 5.6:1 in dark).
- Syntax highlighting inside code blocks is Redmine's, made for a light background, which is why code blocks stay light in dark mode.
- Colour is never the only signal: the status circle sits beside the status name, the flag beside the priority name and the
  tracker square beside the tracker name.
- The handwriting font of titles, menus and buttons depends on the system. The page check measures it where it runs; a system
  with none of the listed fonts falls back to the generic cursive, whose letters can be thinner.
