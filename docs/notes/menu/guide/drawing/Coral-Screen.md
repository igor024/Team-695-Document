---
title: Coral-Screen 
author: igor023
icon: fluent:markdown-20-filled
createTime: 2024/08/17 01:16:39
permalink: /guide/drawing/Coral-Screen/
tags:
  - Guide
  - Markdown
---

# Coral Screen Drawable Objects Reference

This document describes the main objects/classes used in the `coral_screen` subsystem for the canvas drawing system.

---

## CoralScreen

Represents the coral scoring UI screen. Manages the reef, scoring areas, proceed button, and score indicators.

- **Members:** `reef` (Reef), `clickAreas` (array of ClickArea), `scoreIndicators` (array of DrawableObject), `proceedBtn` (ProceedBtn)
- **Main Methods:** `draw()`, `sendData()`, `onClick({x, y})`

---

## Reef

Displays the reef area and overlays letter labels.

- **Members:** `letters` (array of Letter)
- **Main Methods:** `draw()`

---

## ClickArea

Represents a clickable scoring area.

- **Members:** `highlight` (DrawableObject), `scored`, `missed`, `value`
- **Main Methods:** `onClick({x, y})`, `sendData()`, `setValue({value})`, `draw()`

---

## ProceedBtn

Visually animated button for confirming coral screen input.

- **Members:** `isSelected`, `unSelectedSX`, `selectedSX`, `lastTick`
- **Main Methods:** `onClick({x, y})`, `draw()`, `render()`
- **Animation:** Animates size on click (shrinks smoothly when selected, expands when deselected).

---

## Letter

Represents a circular letter label on the reef.

- **Constructor:** `{ctx, renderQueue, text, color, canvasSize, pos, zIndex}`
- **Draws:** The letter using a circle shape with color and text, sized and positioned using canvas dimensions.
- **Main Methods:** `draw()` (calls parent DrawableObject's draw)

[View source for Letter.js](https://github.com/alexfinger21/scouting-project/blob/01826eec404e1ae4407863e7e1e04bad9cecdf12/client/static/scripts/data_collection/coral_screen/Letter.js)

---

## Background

Intended to make everything behind the coral screen darker for focus.

- **Purpose:** To visually separate the coral screen from the rest of the UI by overlaying a dark layer.
- **Implementation:** (Currently only a comment in the file, actual draw logic may need to be added.)

[View source for Background.js](https://github.com/alexfinger21/scouting-project/blob/01826eec404e1ae4407863e7e1e04bad9cecdf12/client/static/scripts/data_collection/coral_screen/Background.js)

---

For deeper details on each object, see their respective files in `client/static/scripts/data_collection/coral_screen/`.



