# Raccoon Rampage

**Play:** https://lilith568.github.io/raccoon-rampage/ (open it in the Meta Quest Browser and tap **Enter VR**; it also works on desktop with a mouse)

Raccoon Rampage is a WebXR arcade game for Meta Quest, built with Meta's **Immersive Web SDK (IWSDK)**.
It looks like a pop-up comic book you can step into. You play a hungry raccoon behind a picnic table at a busy campsite at night. Throw marshmallows, cans,
pinecones and apples at the campers to knock their snacks loose. The snacks fly into your stash.

## How to play

| | Meta Quest (VR) | Desktop |
|---|---|---|
| Pick up an item | Reach into the tray, hold **grip** or **trigger** | – |
| Throw | Swing your arm and let go | Aim with the mouse, **click** / Space |
| Duck | Physically duck behind the table | Hold **C** (or Ctrl / S) |

* **Tutorial:** hit Ted, the camper by the fire, to start the night.
* **Wave 1: Snack Thieves.** Quick hits in a row build a combo multiplier.
* **Wave 2: Rush Hour.** Fast kids are worth double.
* **Wave 3: Flashlights.** When a beam swings your way, duck, or you lose snacks.
* **Boss: Ranger Rick.** He drives his jeep across the camp and throws nets at you. A hit on his hat counts double.
  At half health he gets angry, drives faster and switches on a searchlight.

Your best score is saved on your device.

## Tech

* Meta Immersive Web SDK (`@iwsdk/core`) with ECS systems, WebXR controller grip poses and gamepad input
* Everything is drawn in code: the comic characters, props and the pop-up campsite are painted onto canvases at
  start-up (thick ink outlines, flat colours, halftone shadows) and shown as paper cut-outs and puppets in 3D space.
  The static backdrop is merged into a few draw calls. Sound effects are synthesized with the Web Audio API.
  There are no model, image or audio files to download.
* Throwing uses the controller's velocity history plus a light aim assist (about 14°), so throws feel fair.
* Tested in the IWSDK Meta Quest 3 emulator (IWER).

This repository contains the compiled web build that GitHub Pages serves.

© 2026 Lilith Moritz. All rights reserved.
