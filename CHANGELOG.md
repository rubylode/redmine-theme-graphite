# Changelog

Notable changes to this theme. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [1.0.0] - 2026-10-26

### Added

- Graphite theme: paper with a fine grain, graphite lines, boxes with uneven corners, hatched shading for the selected menu item, a scribble under page titles and a red pencil for urgent or overdue items. It remaps the Open Color variables Redmine 7 is built on. Headings and menus use handwriting fonts from the visitor's own system, so they differ by machine.
- On screens 1100px and wider, all navigation sits in a left sidebar on the paper, in plain CSS, with a pencil margin line. Narrower screens and the login page keep Redmine's layout.
- The issue list reads as a to-do list: a hand-drawn round check before each subject (ticked when the issue is closed), a hatched circle for the assignee's initials and dotted column lines. The issue itself is a card with a strip of tape.
- `javascripts/theme.js` adds the initials, Issues, Gantt, Calendar and Activity as tabs above the list, and the optional pencil filter. It only reads the page.
- Dark paper (chalk on charcoal) for the system dark setting, in one block at the end of the stylesheet.
- The demo Redmine, the page check, the screenshot script and the recorder.
- Tested on Redmine 7.0.2 and the 7.0 line, in light and dark, at desktop and phone width. No console errors, failed requests or sideways scrolling, and text at AA contrast on the pages checked, including the wiki, the activity page and the to-do page.
