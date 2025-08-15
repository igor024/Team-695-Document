---
title: Object Files
author: igor023
icon: fluent:markdown-20-filled
createTime: 2024/08/17 01:16:39
permalink: /guide/drawing/File-By-File/
tags:
  - Guide
  - Markdown
---

### Algae.js

- **Class:** `Algae extends DrawableObject`
- **Role:** Selectable algae game piece.
- **Constructor Properties:** `{ctx, x, y, images, renderQueue, isSelected, ge_key, text, isBlue, zIndex, canvasSize}`
- **Key Members:** `isSelected`, `ge_key`, `text`, `color`
- **Main Methods:** `onClick({x, y})`, `sendData()`, `draw()`

---

### AlgaeMap.js

- **Class:** `AlgaeMap`
- **Role:** Manages all algae objects on the field.
- **Constructor Properties:** `{ctx, allianceColor, images, renderQueue, data, canvasSize}`
- **Key Members:** `algae` (array)
- **Main Methods:** `draw()`, `onClick({x, y})`, `sendData()`

---

### Auton.js

- **Class:** `Auton`
- **Role:** Autonomous period controller.
- **Constructor Properties:** `{ctx, allianceColor, data, images, cX, cY}`
- **Key Members:** `canvasSize`, `ctx`, `images`, `renderQueue`, `map`, `path`, `clickable`
- **Main Methods:** (varies by sub-object; sets up all major components)

---

### AutonHeatMap.js

- **Class:** `AutonHeatMap`
- **Role:** Renders autonomous heatmap.
- **Constructor Properties:** `{ctx, allianceColor, data, img, renderQueue, canvasSize}`
- **Key Members:** `renderQueue`, `pieces`
- **Main Methods:** `draw()`, `onClick({x, y})`

---

### coral_screen/CoralScreen.js

- **Class:** `CoralScreen`
- **Role:** Coral scoring UI controller.
- **Constructor Properties:** `{ctx, renderQueue, canvasSize, images}`
- **Key Members:** `reef`, `clickAreas`, `scoreIndicators`, `proceedBtn`
- **Main Methods:** `draw()`, `sendData()`, `onClick({x, y})`

---

### coral_screen/Reef.js

- **Class:** `Reef extends DrawableObject`
- **Role:** Draws reef and letters.
- **Constructor Properties:** `{ctx, renderQueue, canvasSize, zIndex}`
- **Key Members:** `letters` (array)
- **Main Methods:** `draw()`

---

### coral_screen/ClickArea.js

- **Class:** `ClickArea extends DrawableObject`
- **Role:** Interactive coral scoring zone.
- **Constructor Properties:** `{ctx, renderQueue, scored, missed, value, highlight, canvasSize, zIndex}`
- **Key Members:** `highlight`, `scored`, `missed`, `value`
- **Main Methods:** `onClick({x, y})`, `sendData()`, `setValue({value})`, `draw()`

---

### coral_screen/ProceedBtn.js

- **Class:** `ProceedBtn extends DrawableObject`
- **Role:** Animated confirmation button.
- **Constructor Properties:** `{ctx, x, y, sX, sY, zIndex, imgs, renderQueue}`
- **Key Members:** `isSelected`, `unSelectedSX`, `selectedSX`, `lastTick`
- **Main Methods:** `onClick({x, y})`, `draw()`, `render()`

---

### coral_screen/Letter.js

- **Class:** `Letter extends DrawableObject`
- **Role:** Reef letter label.
- **Constructor Properties:** `{ctx, renderQueue, text, color, canvasSize, pos, zIndex}`
- **Key Members:** `color`, `text`
- **Main Methods:** `draw()`

---

### coral_screen/Background.js

- **Class:** `Background`
- **Role:** Dark overlay behind coral screen.
- **Constructor Properties:** *(not implemented)*
- **Key Members:** *(not implemented)*
- **Main Methods:** *(not implemented)*

---

### Counter.js

- **Class:** `Counter extends DrawableObject`
- **Role:** Text counter for score and counts.
- **Constructor Properties:** `{ctx, renderQueue, canvasSize, count, show, x, y}`
- **Key Members:** `count`, `show`
- **Main Methods:** `draw()`

---

### DrawableObject.js

- **Class:** `DrawableObject`
- **Role:** Base class for drawable/interactable canvas objects.
- **Constructor Properties:** `{ctx, x, y, sX, sY, r, img, text, textSize, renderQueue, radius, visible, zIndex, opacity, points}`
- **Key Members:** `x`, `y`, `sX`, `sY`, `img`, `ctx`, `zIndex`, `textSize`, `opacity`, `radius`, `points`, `renderQueue`, `visible`, `r`
- **Main Methods:** `inBoundingBox({x, y})`, `inBoundingRadius({x, y})`, `inBoundingTriangle({x, y})`, `rotate()`, `draw()`, `render()`

---

### Endgame.js

- **Class:** `Endgame`
- **Role:** Endgame UI and logic.
- **Constructor Properties:** `{ctx, allianceColor, robotData, endgamePieceData, images, cX, cY}`
- **Key Members:** `canvasSize`, `ctx`, `map`, `legend`, `clickable`
- **Main Methods:** `onClick({event, leftOffset, topOffset})`, `sendData()`, `draw()`

---

### FeederStation.js

- **Class:** `FeederStation extends DrawableObject`
- **Role:** Feeder station scoring area.
- **Constructor Properties:** `{x, y, ctx, count, renderQueue, canvasSize, points, showCounter, counterX, counterY}`
- **Key Members:** `color`, `count`, `counter`, `lastClickTick`, `lastAnimTick`, `oldTimeout`, `points`
- **Main Methods:** `onClick({x, y}, isTeleop)`, `sendData()`, `draw()`

---

### GamePiece.js

- **Class:** `GamePiece extends DrawableObject`
- **Role:** Scorable game piece.
- **Constructor Properties:** `{x, y, ctx, img, color, renderQueue, isSelected, ge_key, text, isBlue, zIndex, canvasSize}`
- **Key Members:** `isSelected`, `selectedColor`, `unselectedColor`, `lastTick`
- **Main Methods:** `draw()`

---

### Legend.js

- **Class:** `Legend extends DrawableObject`
- **Role:** Informational text box.
- **Constructor Properties:** `{ctx, renderQueue, img, canvasSize, text}`
- **Key Members:** `text`, `canvasSize`, `isSelected`
- **Main Methods:** `render()`, `draw()`, `onClick({x, y})`

---

### Map.js

- **Class:** `Map extends DrawableObject`
- **Role:** Field background.
- **Constructor Properties:** `{ctx, img, canvasSize, renderQueue}`
- **Key Members:** *(inherits from DrawableObject)*
- **Main Methods:** *(inherits from DrawableObject)*

---

### Net.js

- **Class:** `Net extends DrawableObject`
- **Role:** Net scoring area.
- **Constructor Properties:** `{x, y, ctx, count, renderQueue, canvasSize, showCounter}`
- **Key Members:** `color`, `opacity`, `count`, `counter`, `lastClickTick`, `lastAnimTick`, `oldTimeout`
- **Main Methods:** `onClick({x, y}, isTeleop)`, `sendData()`, `draw()`

---

### Path.js

- **Class:** `Path extends DrawableObject`
- **Role:** Draws a path using quadratic curves.
- **Constructor Properties:** `{ctx, path, renderQueue, canvasSize}`
- **Key Members:** `path`
- **Main Methods:** `draw()`

---

### PiecesHeatMap.js

- **Class:** `PiecesHeatMap`
- **Role:** Heatmap visualization of piece activity.
- **Constructor Properties:** `{ctx, allianceColor, data, img, renderQueue, canvasSize}`
- **Key Members:** `renderQueue`, `pieces`
- **Main Methods:** `draw()`, `onClick({x, y})`

---

### PiecesMap.js

- **Class:** `PiecesMap`
- **Role:** Manages and draws game pieces.
- **Constructor Properties:** `{ctx, isAuton, renderQueue, allianceColor, img, canvasSize}`
- **Key Members:** `pieces` (array)
- **Main Methods:** `draw()`, piece selection methods

---

### Processor.js

- **Class:** `Processor extends DrawableObject`
- **Role:** Processor scoring area.
- **Constructor Properties:** `{ctx, canvasSize, count, renderQueue, showCounter, x, y}`
- **Key Members:** `count`, `color`, `counter`, `lastClickTick`, `lastAnimTick`, `oldTimeout`
- **Main Methods:** `onClick({x, y}, isTeleop)`, `sendData()`, `draw()`

---

### QuadraticLine.js

- **Class:** `QuadraticLine extends DrawableObject`
- **Role:** Draws a quadratic curve.
- **Constructor Properties:** `{ctx, start, end, control, renderQueue, color, width, zIndex}`
- **Key Members:** `start`, `end`, `control`, `color`, `width`
- **Main Methods:** `draw()`

---

### RenderQueue.js

- **Class:** `RenderQueue`
- **Role:** Draw order manager.
- **Constructor Properties:** `{ctx, canvasSize, dpr}`
- **Key Members:** `queue`, `canvasSize`, `dpr`
- **Main Methods:** `insert(obj)`, `pop()`, `sort()`, `render()`

---

### Robot.js

- **Class:** `Robot extends DrawableObject`
- **Role:** Draggable and selectable robot.
- **Constructor Properties:** `{ctx, x, y, sX, sY, img, allianceColor, renderQueue, draggable, zIndex, containerImg, isSelected, canvasSize, pos, value}`
- **Key Members:** `clickable`, `draggable`, `isSelected`, `canvasSize`, `pos`, `value`
- **Main Methods:** `onClick({x, y})`, `onMouseDown({x, y})`, `onMouseUp({x, y})`, `onMouseMove({x, y})`, `getRobotPosition()`, `sendData()`, `draw()`

---

### RobotMap.js

- **Class:** `RobotMap`
- **Role:** Manages robot positions and interaction.
- **Constructor Properties:** `{ctx, renderQueue, allianceColor, images, robotStartingPercent, stagePositions, canvasSize}`
- **Key Members:** `robots`, `stagePositions`, `bargePositions`
- **Main Methods:** `draw()`, robot interaction, `sendData()`

---

### Teleop.js

- **Class:** `Teleop`
- **Role:** Teleoperated period controller.
- **Constructor Properties:** `{ctx, allianceColor, data, images, cX, cY}`
- **Key Members:** `canvasSize`, `dpr`, `ctx`, `images`, `renderQueue`, `map`, `clickable`, `legend`
- **Main Methods:** (varies by sub-object; sets up all major components)

---

