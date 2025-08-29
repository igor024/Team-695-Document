---
title: header.js
author: kjch
icon: fluent:markdown-20-filled
createTime: 2024/08/17 01:16:39
permalink: /guide/pages/Header/
tags:
  - Guide
  - Markdown
---

# header.js Documentation

---

## Overview

**File:** `header.js`  
**Location:** Typically found in `client/static/scripts/` or similar directory.

---

## Purpose

`header.js` manages the behavior and dynamic elements of the site’s header, which is rendered using `header.ejs`. It is responsible for user interface interactions, dynamic username display, dropdown menu logic, and navigation actions at the top of the application.

---

## Required HTML Structure (in `header.ejs`)

To ensure `header.js` works correctly, the following HTML structure must be present in `header.ejs`:

```html
<div id="headerlogin">
  <div class="container">
    <img id="logo" src="...">
    <p id="headertext"><b>...</b></p>
    <p id="username-holder" class="unselectable"></p>
    <button id="dropdown">
      <img id="dropdownImg" src="...">
    </button>
    <div id="dropdown-content">
      <!-- Buttons & links below must match IDs referenced in header.js -->
      <button id="admin-page-button">Admin Page</button>
      <button id="match-verify-button">Match Verify</button>
      <button id="alliance-input-button">Alliance Input</button>
      <button id="alliance-selector-button">Alliance Selector</button>
      <button id="team-details-button">Team Details</button>
      <a href="..." target="_blank">Pit-Scouting Dashboard</a>
      <button id="data-accuracy-button">Data Accuracy</button>
      <a href="..." target="_blank">Team Page</a>
      <a href="..." target="_blank">Team Stats</a>
      <a href="..." target="_blank">Tear Sheet</a>
      <a href="..." target="_blank">Game Simulation</a>
      <button id="log-out-button">Log Out</button>
    </div>
  </div>
</div>
```

**Key requirements:**
- The outer div must have `id="headerlogin"`.
- The username display must use `id="username-holder"`.
- The dropdown menu must use `id="dropdown"` for the button and `id="dropdown-content"` for menu.
- All buttons and links referenced by header.js (see below) must have the correct `id` attributes.

---

## Main Features & Responsibilities

- **User Info Display:**  
  Populates the header with the logged-in user's name and role.

- **Dropdown Menu Management:**  
  Controls the visibility and actions of the dropdown navigation/menu (e.g., admin tools, alliance selector, team details, logout).

- **Navigation:**  
  Handles redirects and UI state changes when header buttons are clicked.

- **Event Listeners:**  
  Registers click and toggle events for header elements (dropdown, buttons).

---

## Key Members

- `usernameHolder`: DOM element for displaying the username.
- `dropdown`: Dropdown button element.
- `dropdownContent`: Dropdown content container.
- Various button elements for navigation:  
  - `admin-page-button`
  - `match-verify-button`
  - `alliance-input-button`
  - `alliance-selector-button`
  - `team-details-button`
  - `data-accuracy-button`
  - `log-out-button`
  - External links (pit scouting, team page, stats, etc.)

---

## Main Methods

- **Initialization:**  
  Sets up the header on page load, including dynamic data population and event listeners.

- **showUsername(name):**  
  Updates the username display in the header.

- **toggleDropdown():**  
  Shows/hides the dropdown menu when the dropdown button is clicked.

- **handleNavigation(event):**  
  Redirects or updates application state when a header button is clicked.

- **logout():**  
  Handles user logout process and redirects to the login page.

---

## Usage Example

Include `<%- include("../static/partials/header") %>` in your EJS layout files.  
`header.js` should be loaded as a module at the top of your HTML, e.g.:

```html
<script type="module" src="../static/scripts/header.js" defer></script>
```

---

## Notes

- `header.js` works closely with the HTML structure defined in `header.ejs`.
- Ensure proper data (user info, admin status) is injected server-side for full header functionality.
- For styling, refer to the associated CSS files (e.g., `universal.css`).

