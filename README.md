# Rubylode Graphite for Redmine

<p><img src="docs/thumbnail.png" alt="Rubylode Graphite theme" width="160"></p>

A pencil-drawing theme for Redmine 7 and up: graphite greys on a cool near-white sheet, sketched double-stroke outlines, hatching in place of shadows, handwritten titles, and the project menu as a sidebar on wide screens.

It is plain CSS plus one small script (`javascripts/theme.js`), with no plugin, no build step and no change to Redmine itself.
The script only reads the page: it puts a status dot beside the group name in an issue list grouped by status and hatched initials beside assignees in lists. It also
adds Issues, Gantt, Calendar and Activity as tabs above the issue list, and the filter that makes the sidebar's margin line slightly
uneven. Without it the theme still works, with plainer lists. The dark set follows your system setting (see [Dark mode](#dark-mode)). It is built on the shared
Rubylode theme base, which also gives it the pages and plugin blocks listed below.

![A walk through Rubylode Graphite: the project, the issue list, an issue, the wiki, the to-do page and the new issue form](docs/demo/walkthrough-light.gif)

| | |
|---|---|
| ![The issue list](docs/screenshots/issues-light.png) | ![An issue](docs/screenshots/issue-light.png) |
| ![The new issue form](docs/screenshots/new-issue-light.png) | ![The project overview, with the Rubylode Projects plugin](docs/screenshots/project-light.png) |
| ![The projects list, with the Rubylode Projects plugin](docs/screenshots/projects-light.png) | ![The home page, with the Rubylode Home plugin](docs/screenshots/home-light.png) |
| ![My page, with the Rubylode Home plugin](docs/screenshots/my-page-light.png) | ![A status block, with the Rubylode Uptime Kuma plugin](docs/screenshots/service-status-light.png) |
| ![The Stats page, with the Rubylode Stats plugin](docs/screenshots/stats-light.png) | ![Sign in](docs/screenshots/login-light.png) |

Dark mode:

![A walk through Rubylode Graphite in dark mode](docs/demo/walkthrough-dark.gif)

| | |
|---|---|
| ![The issue list in dark mode](docs/screenshots/issues-dark.png) | ![An issue in dark mode](docs/screenshots/issue-dark.png) |
| ![The new issue form in dark mode](docs/screenshots/new-issue-dark.png) | ![The project overview in dark mode](docs/screenshots/project-dark.png) |
| ![The projects list in dark mode](docs/screenshots/projects-dark.png) | ![The home page in dark mode](docs/screenshots/home-dark.png) |
| ![My page in dark mode](docs/screenshots/my-page-dark.png) | ![A status block in dark mode](docs/screenshots/service-status-dark.png) |
| ![The Stats page in dark mode](docs/screenshots/stats-dark.png) | ![Sign in in dark mode](docs/screenshots/login-dark.png) |

The screenshots come from the demo Redmine in this repository; the people, projects and issues in it are made up.

## Contents

- [What it looks like](#what-it-looks-like)
- [Install](#install)
- [What is covered](#what-is-covered)
- [Rubylode plugins](#rubylode-plugins)
- [Customising](#customising)
- [Fonts](#fonts)
- [Dark mode](#dark-mode)
- [Accessibility](#accessibility)
- [Compatibility](#compatibility)
- [Development](#development)
- [Checks and releases](#checks-and-releases)
- [License](#license)

## What it looks like

- The page is a flat, cool near-white sheet in light and dark graphite in dark. There is no tint and no texture, and every colour in the chrome is a grey from light pencil to near-black. The one colour left is a muted red pencil for overdue dates and error text.
- Buttons, fields, messages, the issue card and the sign-in card are outlined with sketched strokes: double lines, uneven weight and corners that overshoot. They are SVG border images, so they stretch to any size.
- Depth is hatching, not shadow: the issue card and the sign-in card have cross-hatching along two edges, the issue card has a strip of grey tape, and the selected sidebar item is filled with diagonal strokes.
- The primary button is dark graphite with light text (the other way round in dark). Links are graphite with a pencil underline. Focus is a dotted graphite outline.
- From 1100px up, the project is a sidebar down the left: a hatched tile, the project name in handwriting, the "+" button and the menu, with a margin line down the edge of the sheet. The global links, the New issue button, the search, the project switcher and your avatar are one bar across the top. Below 1100px the project name and tabs sit in a bar under the top bar, as in Redmine.
- Titles, menus, table headings and buttons are in handwriting, taken from your system's own fonts (Segoe Print, Bradley Hand, Chalkboard SE, Marker Felt, Comic Sans MS or the generic cursive), so they differ from one machine to the next. Running text is Noto Sans. The page title has a pencil stroke under it.
- The issue list reads as a to-do list: table rules are drawn strokes, each subject has a hand-drawn circle that is ticked when the issue is closed, the status is a circle (empty, hatched or filled), the priority is a flag (filled for Urgent and Immediate), the tracker is a small square and the assignee is a hatched circle with initials.
- Issues, Gantt, Calendar and Activity are tabs above the issue list.
- The phone slide-out menu is dark, in light mode too.

## Install

1. Download the zip attached to the latest release (the Releases page of this repository) and unzip it inside the `themes` folder of your Redmine, so that `themes/graphite/stylesheets/application.css` exists. Or clone this repository and copy (or link) its `graphite` folder into `themes/`.
2. Restart Redmine.
3. In Administration, Settings, Display, choose **Rubylode Graphite** as the theme and save.

To go back, choose another theme on the same page. Nothing is written to the database apart from that setting.

The theme folder holds the stylesheets, `javascripts/theme.js`, a mark and the bundled fonts (see [Fonts](#fonts)).

## What is covered

The page check loads these pages, in light and dark, at desktop and phone width: sign in, the home page, the project
overview (Redmine's own and the Rubylode Projects plugin's), the projects list, the issue list (plain and grouped), activity, the
roadmap, an issue, an issue with subtasks, a child issue, the edit and new issue forms, the to-do page, the Stats page, the pages
of the four status plugins, My page (Redmine's own and the Rubylode Home plugin's), a wiki page and its editor, spent time, Gantt,
the calendar, project settings and administration.
Flash messages, tabs, the right-click menu, dropdowns, pagination, the text editor and the phone slide-out menu are styled as well.

<!-- rubylode-plugins:start -->
## Rubylode plugins

Rubylode Graphite styles the Rubylode plugins' blocks natively. Each plugin draws with its own CSS custom properties, and one section of the
theme, `graphite/stylesheets/plugins.css`, points them at Rubylode Graphite's tokens, so the blocks follow the theme in light and dark:

- [Rubylode Projects](https://github.com/rubylode/redmine-rubylode-projects) (`--rubylode-projects-*`): the overview cards and the projects list.
- [Rubylode Home](https://github.com/rubylode/redmine-rubylode-home) (`--rubylode-home-*`): My page and the welcome page.
- [Rubylode To-do](https://github.com/rubylode/redmine-rubylode-todo) (`--todo-*`): the to-do page.
- [Rubylode Uptime Kuma](https://github.com/rubylode/redmine-rubylode-uptime-kuma) (`--rubylode-uptime-kuma-*`),
  [Rubylode GlitchTip](https://github.com/rubylode/redmine-rubylode-glitchtip) (`--rubylode-glitchtip-*`),
  [Rubylode Windmill](https://github.com/rubylode/redmine-rubylode-windmill) (`--rubylode-windmill-*`) and
  [Rubylode Beszel](https://github.com/rubylode/redmine-rubylode-beszel) (`--rubylode-beszel-*`): the status blocks.
- [Rubylode Stats](https://github.com/rubylode/redmine-rubylode-stats) (`--stats-tooltip-*`): the chart tooltip.
- [Rubylode New issue button](https://github.com/rubylode/redmine-rubylode-new-issue-button): a rounded primary button beside the search.
  Plugins load their stylesheets after the theme's, so these rules start with `body #header` to win whatever the order.

None of them is needed. Without a plugin its rules match nothing.
<!-- rubylode-plugins:end -->

## Customising

Every colour, corner, shadow, font and a few sizes are custom properties in `graphite/stylesheets/tokens.css` (light values) and
`graphite/stylesheets/dark.css` (dark values). Change them there, or override them from a stylesheet of your own. The names
start with `--theme-` and are the same in every Rubylode theme. The main ones:

| Token | What it is |
|---|---|
| `--theme-page`, `--theme-surface`, `--theme-surface-sunken`, `--theme-surface-hover` | the sheet, the panels, stripes and the attribute panel, hovered rows |
| `--theme-line`, `--theme-line-soft`, `--theme-line-strong` | panel borders and row lines, column lines, field borders |
| `--theme-ink`, `--theme-ink-soft`, `--theme-ink-muted` | text, secondary text, labels and notes |
| `--theme-accent-0` to `--theme-accent-9` | the graphite ramp, light pencil to near-black |
| `--theme-primary`, `--theme-primary-hover` | dark graphite: the main action button, the New issue button, the current page |
| `--theme-sidebar-width`, `--theme-sidebar-background`, `--theme-sidebar-selected-background` | the sidebar and its hatched selected item |
| `--theme-status-new`, `-in-progress`, `-resolved`, `-feedback`, `-closed`, `-rejected` | status colours, by Redmine's default status ids 1 to 6 |
| `--theme-radius-small`, `--theme-radius`, `--theme-radius-panel` | corners of fields, cards and panels |
| `--theme-font-size` | the size of running text (16px); every other text size follows it |
| `--theme-font`, `--theme-font-monospace`, `--theme-title-font`, `--theme-title-weight` | the text, code and heading fonts |

The rest (messages, avatars, diffs, the Gantt chart, the header heights, the icons drawn in the stylesheet) are listed with a
comment each in `tokens.css`.

Graphite adds a few tokens of its own at the end of `tokens.css`: `--theme-pencil` and its soft and dotted variants,
`--theme-red-pencil-ink`, `--theme-hatch` and `--theme-crosshatch`, the sketched border image, the row and heading rules and the
tape. The drawn circles, flags and underline are masks at the top of `flourishes.css`. `--theme-title-font` is a handwriting stack; set it to
`var(--theme-font)` for plain titles.

What the tokens cannot say is in `graphite/stylesheets/flourishes.css`: the paper, the margin line, the pencil outlines, the
to-do list look of the issue list, the tape and the dark phone menu.

Status, priority and tracker looks are matched by Redmine's default ids (statuses 1 New to 6 Rejected, priorities 1 Low to 5
Immediate, trackers 1 Bug to 3 Support). If yours differ, change the ids in the "issue list" section of
`graphite/stylesheets/structure.css` and in the fourth section of `flourishes.css`.

The labels "Parent" and "Ancestor" above an issue's subject are drawn by CSS, so they are in English only.

## Fonts

Graphite ships its own text and code fonts, so they look the same on every system and nothing is loaded from another site: Noto Sans for
text and Noto Sans Mono for code, as woff2 files in `graphite/fonts/` (latin and latin-ext). Both are under the SIL Open
Font License 1.1; the licence texts are in the same folder. A browser downloads a file only when a page uses it. To use other
fonts, change `--theme-font` and `--theme-font-monospace` in `graphite/stylesheets/tokens.css`. The size of running text is
`--theme-font-size` (16px), and every other text size follows it.

The handwriting of titles, menus and buttons is not shipped. It is a stack of fonts that come with the system (see
`--theme-title-font`), so it is a different hand on Windows, macOS and Linux.

## Dark mode

Dark mode follows your system setting (`prefers-color-scheme`): light chalk-grey lines on a dark graphite sheet, with the primary
button light and its text dark. Code blocks stay light, since Redmine's syntax colours are made for a light background. To keep
Graphite light-only, remove the line `@import url(dark.css);` from `graphite/stylesheets/responsive.css`; every dark value is in
that one file.

## Accessibility

Text and controls meet WCAG AA in both modes. The page check measures every visible text against the colour behind it on every
page; the tokens were also measured one by one, including the parts the check cannot see (field borders, outlines, flags). The
measured ratios are in [docs/accessibility.md](docs/accessibility.md). In short: body text at least 13.2:1 in light and 8.8:1 in
dark, secondary text at least 10.7:1 and 9.2:1, muted text at least 5.8:1 and 5.2:1, light text on the primary 13.6:1 and 13.9:1,
every status chip at least 5.1:1.

## Compatibility

Redmine 7.0 and newer. Tested on 7.0.2, from both the `7.0.2` and the `7.0` image tags (on 2026-11-02 the 7.0 line was at 7.0.2). Older versions are not expected to work: Redmine 7 reads a theme from `themes/<name>` and is
built on the Open Color variables this theme remaps.

Browsers: current Chrome, Edge, Firefox and Safari. The theme uses `:has()` and `color-mix()` (Chrome 111, Firefox 121,
Safari 16.4 and newer); an older browser shows plainer chips and keeps the rest.

## Development

You need Docker, Ruby, Node and Chrome.

```
npm install
ruby bin/demo up        # a throwaway Redmine with demo data at http://localhost:3108 (admin / admin)
npm run check           # loads every page in light and dark, at desktop and phone width
npm run screenshots     # docs/screenshots
npm run record          # docs/demo, a GIF of a walk through the pages
ruby bin/demo reset     # wipe the demo
```

If copies of the Rubylode plugins listed above sit next to this repository (`../redmine-rubylode-todo` and so on, or in a folder
named in `RUBYLODE_PLUGINS_DIR`), the demo mounts them and the check, screenshots and recording show their pages. The demo points
the status plugins at an address where nothing answers, so their pages show the "unavailable" state. Without the plugins the
demo is plain Redmine, and the check skips their pages.

The stylesheets other than `flourishes.css`, `javascripts/theme.js`, `test/`, `bin/demo` and `docker-compose.yml` are generated from
the base all Rubylode themes share, so a fix there reaches every theme. If you send a change to one of them, I will carry it over to the base.

The check fails on console errors, failed requests, sideways scrolling and text below WCAG AA contrast. `REDMINE_TAG=7.0 ruby bin/demo up`
runs it against another Redmine version. After you change a stylesheet, run `ruby bin/demo restart` and reload: Redmine caches theme
files until it restarts.

## Checks and releases

Every push starts a real Redmine from its Docker image (7.0.2 and the 7.0 line), loads every page of the theme in light and dark at desktop and phone width, and fails on console errors, failed requests, sideways scrolling and low text contrast. On GitHub that is `.github/workflows/check.yml`, on GitHub's own runners, and it also runs on pull requests. On a self-hosted Gitea it is `.gitea/workflows/check.yml`, which runs only on pushes to `main`, because that runner works on the host with Docker access and must only run code that is already merged.

A tag such as `v2.0.0` runs the same check, builds `graphite-<version>.zip` holding the theme folder, and attaches it to a release with the matching section of `CHANGELOG.md` as its notes (`release.yml` in the same folders). The tag needs a section for that version in the changelog. More on both, and on the drift check against the shared base, in [docs/ci.md](docs/ci.md).

## License

GPL version 2 or later, the same as Redmine. See `LICENSE`. Copyright (C) 2026  Nick Gorbikoff.

No warranty, as the GPL says. Try it on a copy of your tracker before the real one.
