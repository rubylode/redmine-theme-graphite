# Contrast

Graphite aims at WCAG 2.2 AA in light and dark: 4.5:1 for text (3:1 for large text), and 3:1 for the parts of a control that
identify it (field borders, outlines), for focus indicators and for the flags and circles in the issue list, which are graphics
beside a word that carries the same meaning.

## How it is measured

- The page check (`npm run check`) loads 29 pages in light and dark, at 1280px and 390px wide, and measures every visible
  piece of text against the colour stacked behind it. On 2026-11-02 against Redmine 7.0.2 with the Rubylode plugins mounted it
  measured 5,272 text pairs across the 58 desktop runs and 6,382 across the 58 phone runs, and found none below AA: 116 of 116
  gated runs clean. At the 16px base size every measured pair also reaches 4.5:1, so none relies on the 3:1 allowance for large text.
- The tokens, one pair at a time, below (`tokens.css` and `dark.css`). The check skips text over a gradient or an image, and it
  does not see field borders, outlines or the flags, so those are measured here. Chip colours are the mixes the stylesheet makes
  (`color-mix`), worked out on the colour of the panel or stripe they sit on. In the issue list the status and priority are
  not chips but ink text beside a drawn circle or flag, so the chip rows are the ones on the issue page.
- The page is a flat colour: there is no grain or texture under the text, so the token pairs are the real ones.
- The sidebar's selected item and the buttons on hover are shaded with hatching, a gradient of thin lines at 20 to 45 percent.
  The check skips text over it, so its text is measured here on the sidebar colour. In light the lines only darken the
  background, and the ink is above 15:1 on the plain colour. In dark they lighten it, and the white ink stays above 5:1 on a
  pixel of a line.
- Links are the same graphite as the text and set apart by an underline in pencil grey. The underline is not text, so it is
  outside the ratios, and a link reads as one by its underline, not by its colour.

## Light

| Pair | Foreground | Background | Ratio |
|---|---|---|---|
| Body text on a panel | `#1c1c1c` | `#fbfbfb` | 16.47 |
| Body text on a sunken panel or stripe | `#1c1c1c` | `#ececec` | 14.43 |
| Body text on a hovered row | `#1c1c1c` | `#e2e2e2` | 13.16 |
| Secondary text on a panel | `#333333` | `#fbfbfb` | 12.21 |
| Secondary text on a sunken panel | `#333333` | `#ececec` | 10.69 |
| Muted text on a panel | `#555555` | `#fbfbfb` | 7.20 |
| Muted text on a sunken panel or stripe | `#555555` | `#ececec` | 6.31 |
| Muted text on a hovered row | `#555555` | `#e2e2e2` | 5.75 |
| Link on a panel | `#1c1c1c` | `#fbfbfb` | 16.47 |
| Link on a sunken panel or stripe | `#1c1c1c` | `#ececec` | 14.43 |
| Link on a hovered row | `#1c1c1c` | `#e2e2e2` | 13.16 |
| Light text on the primary (dark graphite) | `#fafafa` | `#2b2b2b` | 13.57 |
| Light text on the primary, hovered | `#fafafa` | `#000000` | 20.12 |
| Button text | `#1c1c1c` | `#fbfbfb` | 16.47 |
| Delete button text | `#8a3b32` | `#ececec` | 6.46 |
| Overdue date and error text (red pencil) on a panel | `#8a3b32` | `#fbfbfb` | 7.37 |
| Overdue date (red pencil) on a stripe | `#8a3b32` | `#ececec` | 6.46 |
| Sidebar link | `#333333` | `#efefef` | 10.99 |
| Sidebar selected item, on the paler end of its hatching | `#000000` | `#efefef` | 18.26 |
| Link on a panel (graphite, underlined) | `#1c1c1c` | `#fbfbfb` | 16.47 |
| Top bar links | `#333333` | `#f4f4f4` | 11.49 |
| Count badge | `#f4f4f4` | `#1c1c1c` | 15.49 |
| White on the avatar grey | `#ffffff` | `#4a4a4a` | 8.86 |
| Code block (kept light) | `#1c1c1c` | `#f0f0f0` | 14.95 |
| Closed or up message | `#2e2e2e` | `#ececec` | 11.49 |
| Warning message | `#2e2e2e` | `#e4e4e4` | 10.68 |
| Status block, up | `#2e2e2e` | `#e8e8e8` | 11.08 |
| Status block, unavailable | `#2e2e2e` | `#e4e4e4` | 10.68 |
| Phone menu text | `#e6e6e6` | `#2a2a2a` | 11.50 |
| Chip New (issue page), on a panel | `#444444` | `#e7e7e7` | 7.88 |
| Chip New (issue page), on a sunken panel | `#444444` | `#dadada` | 6.97 |
| Chip In Progress (issue page), on a panel | `#1d1d1d` | `#dedede` | 12.53 |
| Chip In Progress (issue page), on a sunken panel | `#1d1d1d` | `#d1d1d1` | 11.04 |
| Chip Resolved (issue page), on a panel | `#2e2e2e` | `#e2e2e2` | 10.48 |
| Chip Resolved (issue page), on a sunken panel | `#2e2e2e` | `#d5d5d5` | 9.25 |
| Chip Feedback (issue page), on a panel | `#383838` | `#e4e4e4` | 9.22 |
| Chip Feedback (issue page), on a sunken panel | `#383838` | `#d8d8d8` | 8.23 |
| Chip Closed (issue page), on a panel | `#4c4c4c` | `#e9e9e9` | 7.07 |
| Chip Closed (issue page), on a sunken panel | `#4c4c4c` | `#dcdcdc` | 6.26 |
| Chip Rejected (issue page), on a panel | `#111111` | `#dcdcdc` | 13.77 |
| Chip Rejected (issue page), on a sunken panel | `#111111` | `#cfcfcf` | 12.12 |
| Chip High (issue page), on a panel | `#444444` | `#e7e7e7` | 7.88 |
| Chip High (issue page), on a sunken panel | `#444444` | `#dadada` | 6.97 |
| Chip Urgent (issue page), on a panel | `#242424` | `#e0e0e0` | 11.76 |
| Chip Urgent (issue page), on a sunken panel | `#242424` | `#d3d3d3` | 10.37 |
| White on priority Immediate (issue page chip) | `#ffffff` | `#1c1c1c` | 17.04 |
| Field border on a panel (control) | `#1c1c1c` | `#fbfbfb` | 16.47 |
| Focus outline on a panel | `#1c1c1c` | `#fbfbfb` | 16.47 |
| Button outline on a panel (control) | `#1c1c1c` | `#fbfbfb` | 16.47 |
| Flag for Urgent and Immediate, on a stripe | `#1c1c1c` | `#ececec` | 14.43 |
| Flag for the lower priorities, on a stripe | `#555555` | `#ececec` | 6.31 |
| Status circle outline, on a stripe | `#1c1c1c` | `#ececec` | 14.43 |
| Tracker square, on a stripe | `#1c1c1c` | `#ececec` | 14.43 |
| Sidebar pencil line, on the sidebar | `#444444` | `#efefef` | 8.47 |

## Dark

| Pair | Foreground | Background | Ratio |
|---|---|---|---|
| Body text on a panel | `#ececec` | `#333333` | 10.69 |
| Body text on a sunken panel or stripe | `#ececec` | `#2e2e2e` | 11.49 |
| Body text on a hovered row | `#ececec` | `#404040` | 8.78 |
| Secondary text on a panel | `#dcdcdc` | `#333333` | 9.21 |
| Secondary text on a sunken panel | `#dcdcdc` | `#2e2e2e` | 9.90 |
| Muted text on a panel | `#b8b8b8` | `#333333` | 6.37 |
| Muted text on a sunken panel or stripe | `#b8b8b8` | `#2e2e2e` | 6.85 |
| Muted text on a hovered row | `#b8b8b8` | `#404040` | 5.23 |
| Link on a panel | `#ececec` | `#333333` | 10.69 |
| Link on a sunken panel or stripe | `#ececec` | `#2e2e2e` | 11.49 |
| Link on a hovered row | `#ececec` | `#404040` | 8.78 |
| Light text on the primary (dark graphite) | `#1c1c1c` | `#e8e8e8` | 13.91 |
| Light text on the primary, hovered | `#1c1c1c` | `#ffffff` | 17.04 |
| Button text | `#ececec` | `#333333` | 10.69 |
| Delete button text | `#e6a79d` | `#3a3a3a` | 5.62 |
| Overdue date and error text (red pencil) on a panel | `#e6a79d` | `#333333` | 6.24 |
| Overdue date (red pencil) on a stripe | `#e6a79d` | `#2e2e2e` | 6.71 |
| Sidebar link | `#d8d8d8` | `#252525` | 10.75 |
| Sidebar selected item, on the paler end of its hatching | `#ffffff` | `#252525` | 15.33 |
| Link on a panel (graphite, underlined) | `#ececec` | `#333333` | 10.69 |
| Top bar links | `#d8d8d8` | `#2a2a2a` | 10.07 |
| Count badge | `#2a2a2a` | `#e2e2e2` | 11.08 |
| White on the avatar grey | `#ffffff` | `#6a6a6a` | 5.41 |
| Code block (kept light) | `#1c1c1c` | `#f0f0f0` | 14.95 |
| Closed or up message | `#ececec` | `#3a3a3a` | 9.63 |
| Warning message | `#ececec` | `#404040` | 8.78 |
| Status block, up | `#dcdcdc` | `#3a3a3a` | 8.29 |
| Status block, unavailable | `#dcdcdc` | `#404040` | 7.56 |
| Phone menu text | `#e6e6e6` | `#1c1c1c` | 13.65 |
| Chip New (issue page), on a panel | `#d4d4d4` | `#515151` | 5.36 |
| Chip New (issue page), on a sunken panel | `#d4d4d4` | `#4d4d4d` | 5.70 |
| Chip In Progress (issue page), on a panel | `#eeeeee` | `#5d5d5d` | 5.68 |
| Chip In Progress (issue page), on a sunken panel | `#eeeeee` | `#595959` | 6.04 |
| Chip Resolved (issue page), on a panel | `#e1e1e1` | `#575757` | 5.53 |
| Chip Resolved (issue page), on a sunken panel | `#e1e1e1` | `#535353` | 5.88 |
| Chip Feedback (issue page), on a panel | `#dadada` | `#545454` | 5.42 |
| Chip Feedback (issue page), on a sunken panel | `#dadada` | `#505050` | 5.77 |
| Chip Closed (issue page), on a panel | `#c7c7c7` | `#4c4c4c` | 5.08 |
| Chip Closed (issue page), on a sunken panel | `#c7c7c7` | `#484848` | 5.41 |
| Chip Rejected (issue page), on a panel | `#f8f8f8` | `#616161` | 5.83 |
| Chip Rejected (issue page), on a sunken panel | `#f8f8f8` | `#5d5d5d` | 6.20 |
| Chip High (issue page), on a panel | `#d4d4d4` | `#515151` | 5.36 |
| Chip High (issue page), on a sunken panel | `#d4d4d4` | `#4d4d4d` | 5.70 |
| Chip Urgent (issue page), on a panel | `#e5e5e5` | `#595959` | 5.56 |
| Chip Urgent (issue page), on a sunken panel | `#e5e5e5` | `#555555` | 5.92 |
| White on priority Immediate (issue page chip) | `#ffffff` | `#5a5a5a` | 6.90 |
| Field border on a panel (control) | `#d8d8d8` | `#333333` | 8.86 |
| Focus outline on a panel | `#e2e2e2` | `#333333` | 9.75 |
| Button outline on a panel (control) | `#d8d8d8` | `#333333` | 8.86 |
| Flag for Urgent and Immediate, on a stripe | `#e2e2e2` | `#2e2e2e` | 10.48 |
| Flag for the lower priorities, on a stripe | `#b8b8b8` | `#2e2e2e` | 6.85 |
| Status circle outline, on a stripe | `#e2e2e2` | `#2e2e2e` | 10.48 |
| Tracker square, on a stripe | `#e2e2e2` | `#2e2e2e` | 10.48 |
| Sidebar pencil line, on the sidebar | `#bdbdbd` | `#252525` | 8.16 |

The lowest text pair in either mode is the Closed chip on the issue page in dark, at 5.08:1. In light it is 5.75:1, muted text on a
hovered row.

## Not covered

- Redmine's own avatar colours are replaced by one pencil grey with white initials (8.9:1 in light, 5.4:1 in dark).
- Syntax highlighting inside code blocks is Redmine's, made for a light background, which is why code blocks stay light in dark mode.
- Colour is never the only signal: the status circle sits beside the status name, the flag beside the priority name and the
  tracker square beside the tracker name.
- The handwriting font of titles, menus and buttons depends on the system. The page check measures it where it runs; a system
  with none of the listed fonts falls back to the generic cursive, whose letters can be thinner.
