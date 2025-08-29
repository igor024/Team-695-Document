---
title: Ejs Files
author: kjch
icon: fluent:markdown-20-filled
createTime: 2024/08/17 01:16:39
permalink: /guide/pages/EjsFiles/
tags:
  - Guide
  - Markdown
---

## client/templates/alliance-input.ejs

**Role:**  
Renders the UI for alliance input, allowing users to select teams for each alliance position (captain, 1st, 2nd) across multiple alliances.

**Dynamic Data:**  
- `data`: Array of alliance objects containing team assignments.
- `teams`: Array of available team numbers.

**Layout/Features:**  
- Table to select captain, 1st, and 2nd for each alliance.
- Select boxes populated dynamically from `teams`.
- Pre-selects teams already assigned in `data`.

---

## client/templates/alliance-selector.ejs

**Role:**  
Displays alliance picks and suggestions for the alliance selection process.

**Dynamic Data:**  
- `data`: Array of alliance objects containing team assignments.

**Layout/Features:**  
- Table of alliances with captain, 1st, and 2nd displayed.
- Table of alliance suggestions (with team # and suggestion columns).
- Section for available teams and a sort-by selector.

---

## client/templates/admin-page.ejs

**Role:**  
Admin UI for assigning users to scouting positions and downloading reports.

**Dynamic Data:**  
- `team`: Array of user objects (display, id).
- `assignedUsers`: Array of assigned user objects.

**Layout/Features:**  
- Select boxes for assigning users to "Red", "Blue", and "7th" positions.
- Buttons for saving assignments and downloading reports.

---

## client/templates/columnSummary.ejs

**Role:**  
Displays a summary for a data column, formatting values as needed.

**Dynamic Data:**  
- `list`: Array of values/pairs for the summary.
- `header`: The header value for the column.
- `alwaysShow`: Boolean controlling visibility.

**Layout/Features:**  
- Shows formatted header and values, separated by "/".

---

## client/templates/data-collection.ejs

**Role:**  
Main data entry form for match scouting.

**Dynamic Data:**  
- `assignment`: Assignment object for the user/team/match.
- `selectedPage`: Active tab/page ("scouting-page" or "comments-page").

**Layout/Features:**  
- Tabs for "Scout" and "Comments".
- Form for entering match data.
- Displays assigned team, match number, and pregame/autonomous inputs.

---

## client/templates/event-data.ejs

**Role:**  
Displays a scrollable list of all matches for an event.

**Dynamic Data:**  
- `teams`: Array of match/team objects.
- `runningMatch`: Index of the current match.
- `lastPlayedMatch`: Used for scrolling to last played match.
- `isAdmin`: Boolean flag for admin controls.

**Layout/Features:**  
- Match cards/tables showing numbers, times, scores.
- Admin-only start/stop buttons.

---

## client/templates/game-strategy.ejs

**Role:**  
Displays strategy charts and scenario comparisons for matches.

**Dynamic Data:**  
- Chart data and labels provided via JS.

**Layout/Features:**  
- Split view: charts on the left, scenario details on the right.
- Strategy key/legend.
- Canvas elements for rendering charts.

---

## client/templates/old.ejs

**Role:**  
Legacy match summary and stats page.

**Dynamic Data:**  
- `gameNumbers`: Array of match numbers.
- `matchup`: Array of team/matchup objects.
- `info`: Object with score information.
- `match`: Current match number.

**Layout/Features:**  
- Match selection drop-down.
- Table showing teams, names, stats.
- Displays predicted and actual scores for red and blue teams.

---

## client/static/partials/header.ejs

**Role:**  
Reusable header partial shown at the top of most pages.

**Dynamic Data:**  
- `isAdmin`: Flag for showing admin controls.

**Layout/Features:**  
- Logo and team name.
- Username display.
- Dropdown menu with navigation and action buttons (conditional on admin status).

---

## client/static/partials/footer.ejs

**Role:**  
Reusable footer partial shown at the bottom of most pages.

**Layout/Features:**  
- Navigation bar with buttons for: Matches, Data Entry, Strategy, Teams, Rankings.
- Icons and descriptive subtexts.

