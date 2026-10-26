# Changelog

All notable changes to this theme. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added

- Graphite: a pencil drawing. Paper with a fine grain and soft light, graphite lines, hand-drawn looking boxes with uneven corners, hatched shading for the selected menu item, a scribble under page titles, handwriting type for headings and menus (from the computer's own fonts, so it differs by machine), and a red pencil for what is urgent or overdue, in the Open Color variables Redmine 7 is built on.
- On screens 1100px and wider, all navigation moves into a left sidebar on the paper, in plain CSS, with a pencil margin line. Narrower screens and the login page keep Redmine's own layout.
- The issue list reads as a to-do list on paper: a hand-drawn round check before each subject, ticked in pencil when the issue is closed, a hatched circle for the assignee's initials, dotted column lines, and Issues, Gantt, Calendar and Activity as tabs above the list. The issue itself is a card with a strip of tape. The initials, the tabs and the optional wobbly pencil filter come from one small script, `javascripts/theme.js`, which only reads the page.
- Dark paper (chalk on charcoal) for the system dark setting, in one block at the end of the stylesheet.
- The theme skeleton, the demo Redmine, the page check, the screenshot script and the recorder.
- Tested on Redmine 7.0.2 and the 7.0 line, in light and dark, at desktop and phone width: no console errors, no failed requests, no sideways scrolling, and text at AA contrast on the pages that matter, including the wiki, the activity page and the Rubylode to-do page.
