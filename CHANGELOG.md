# Changelog

Notable changes to this theme. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [2.0.0] - 2026-11-02

### Changed

- The theme is built on the shared Rubylode theme base. The stylesheets, `javascripts/theme.js`, `test/`, `bin/demo` and `docker-compose.yml` are generated from it, and a drift check compares them with the base.
- `application.css` is now a small file that loads Redmine's own stylesheet, then `tokens.css`. `responsive.css` loads `structure.css`, `plugins.css`, `sidebar-layout.css`, `dark.css` and `flourishes.css`.
- The dark set moved from the end of `application.css` to `dark.css`. To keep the theme light-only, remove its import from `responsive.css`.
- Colours, corners, fonts and sizes are `--theme-*` tokens, with the same names in every Rubylode theme. Custom overrides that used the old names need the new ones (see the table below).
- The sidebar, the paper grain, the pencil outlines, the to-do list look of the issue list, the tape, the tabs above the list and the hatched initials are kept, now in `flourishes.css` and `javascripts/theme.js`.
- The base text size is 16px, set by `--theme-font-size`. List text and the sidebar are 14px; fields and buttons are 15px.
- Text is Noto Sans and code is Noto Sans Mono, both shipped in `graphite/fonts/`. The Inter-first stack of 1.0.0 is gone. Titles, menus, table headings and buttons keep the handwriting stack.
- The red pencil is now the primary colour, so the New issue button of the plugin, the current page and the context-menu selection are red too. In 1.0.0 only the submit buttons and the sidebar's "+" were.
- The status circle and the priority flag in the issue list are drawn with the base's status and priority classes. The status circle is empty for New, hatched for In Progress and Feedback, filled for Resolved and Closed, red for Rejected. The old status and priority colours per row are gone.
- Avatars are one pencil grey with white initials, in light and dark. Redmine's eight avatar colours no longer show.
- The paper grain is lighter (opacity 0.5, was 0.9), so that muted text on the page keeps 4.5:1 against the darkest grain pixel.
- The top bar has no fill of its own, so the grain shows through it.
- The sidebar is 240px wide, up from 236px.
- Dark mode keeps the chalk-on-charcoal look. The red pencil is a darker red in dark so that white text on it reaches 4.5:1.

### Added

- Pages the 1.0.0 theme did not style: the home page, My page, the projects list and overview, activity, the roadmap, the Gantt chart, the calendar, time entries, project settings, administration, the wiki editor and the phone slide-out menu.
- The Rubylode plugins' blocks: Projects, Home, To-do, Uptime Kuma, GlitchTip, Windmill, Beszel, Stats and the New issue button, in light and dark.
- A pencil mark at the start of the top bar and above the sign-in form.
- Global links in the sidebar on pages with no project menu, such as My page and the welcome page.
- README sections for the plugins, customising and fonts, `docs/ci.md` for the checks and the drift check, and the measured contrast ratios in `docs/accessibility.md`.

### Removed

- The colour hook on status group headers (`data-group`). 1.0.0 made it transparent in the final look. The base's status dot beside a group name, set by its own script, replaces it.
- The `--graphite-*` names and the `--oc-*` overrides, replaced by the tokens in the table below.

### Token names

| 1.0.0 | 2.0.0 |
|---|---|
| `--graphite-page` | `--theme-page` |
| `--oc-white` | `--theme-surface` (and `--theme-redmine-white` for Redmine's own panels) |
| `--oc-gray-0` to `--oc-gray-9` | `--theme-neutral-0` to `--theme-neutral-9` |
| `--graphite-accent-0` to `--graphite-accent-9` | `--theme-accent-0` to `--theme-accent-9` |
| `--graphite-ink` | `--theme-pencil` |
| `--graphite-red` | `--theme-red-pencil` (`--theme-red-pencil-ink` for red text) |
| `--graphite-rail` | `--theme-sidebar-background` |
| `--graphite-rail-width` | `--theme-sidebar-width` |
| `--graphite-rail-line` | `--theme-sidebar-line` |
| `--graphite-rail-ink`, `--graphite-rail-dim` | `--theme-header-link`, `--theme-ink-muted` |
| `--graphite-rail-hover` | `--theme-sidebar-hover-background` |
| `--graphite-rail-selected` | `--theme-sidebar-selected-background` |
| `--graphite-rail-selected-ink` | `--theme-sidebar-selected-ink` |
| `--graphite-rail-field`, `--graphite-rail-field-line` | `--theme-header-field-background`, `--theme-header-field-border` |
| `--graphite-phone-menu`, `--graphite-phone-menu-ink` | `--theme-phone-menu-background`, `--theme-phone-menu-ink` |
| `--graphite-shadow` | `--theme-shadow-popup` |
| `--graphite-hand` | `--theme-title-font` |
| `--graphite-radius` | `--theme-radius-small` |
| `--graphite-hatch` | `--theme-hatch` |
| `--graphite-grain`, `--graphite-blend`, `--graphite-grain-opacity` | `--theme-paper-grain-image`, `--theme-paper-blend`, `--theme-paper-grain-opacity` |
| `--graphite-scribble`, `--graphite-tick`, `--graphite-tape` | `--theme-scribble-image`, `--theme-tick-image`, `--theme-tape-image` |
| `--fonts-main` | `--theme-font` |

## [1.0.0] - 2026-10-26

### Added

- Graphite theme: paper with a fine grain, graphite lines, boxes with uneven corners, hatched shading for the selected menu item, a scribble under page titles and a red pencil for urgent or overdue items. It remaps the Open Color variables Redmine 7 is built on. Headings and menus use handwriting fonts from the visitor's own system, so they differ by machine.
- On screens 1100px and wider, all navigation sits in a left sidebar on the paper, in plain CSS, with a pencil margin line. Narrower screens and the login page keep Redmine's layout.
- The issue list reads as a to-do list: a hand-drawn round check before each subject (ticked when the issue is closed), a hatched circle for the assignee's initials and dotted column lines. The issue itself is a card with a strip of tape.
- `javascripts/theme.js` adds the initials, Issues, Gantt, Calendar and Activity as tabs above the list, and the optional pencil filter. It only reads the page.
- Dark paper (chalk on charcoal) for the system dark setting, in one block at the end of the stylesheet.
- The demo Redmine, the page check, the screenshot script and the recorder.
- Tested on Redmine 7.0.2 and the 7.0 line, in light and dark, at desktop and phone width. No console errors, failed requests or sideways scrolling, and text at AA contrast on the pages checked, including the wiki, the activity page and the to-do page.
