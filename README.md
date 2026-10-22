# Raccoon Rampage

**Play:** https://lilith568.github.io/raccoon-rampage/ (open it in the Meta Quest Browser and tap **Enter VR**; it also works on desktop with a mouse)

Raccoon Rampage is a **hands-first** WebXR arcade game for Meta Quest, built with Meta's **Immersive Web SDK (IWSDK)**.
It looks like a pop-up comic book you can step into. You play a hungry raccoon behind a picnic table at a busy campsite at night.
Throw marshmallows, cans, pinecones and apples at the campers to knock their snacks loose. The snacks fly into your stash.

No controllers needed, and it is designed to be played **seated**: every interaction works within arm's reach.

## How to play

| | Meta Quest: hands (default) | Meta Quest: controllers (optional) | Desktop |
|---|---|---|---|
| Pick up a snack | **Pinch** (thumb + index) over the table | Hold **grip** or **trigger** | – |
| Throw | Swing your hand and **let go of the pinch** | Swing and release | Aim with the mouse, **click** / Space |
| Hide from lights and nets | **Cover your eyes with both paws** or duck a little (about 15 cm) | Duck a little | Hold **C** (or Ctrl / S) |

* **Tutorial:** hit Ted, the camper by the fire, to start the night.
* **Wave 1: Snack Thieves.** Quick hits in a row build a combo multiplier.
* **Wave 2: Rush Hour.** Fast kids are worth double.
* **Wave 3: Flashlights.** When a beam swings your way, hide, or you lose snacks.
* **Boss: Ranger Rick.** He drives his jeep across the camp and throws nets at you. A hit on his hat counts double.
  At half health he gets angry, drives faster and switches on a searchlight.

A full night takes about 4 minutes. Your best score is saved on your device.

## Tech

* Meta Immersive Web SDK (`@iwsdk/core`): ECS game system, WebXR **hand tracking** (pinch detection from the thumb-tip and
  index-tip joints, with the WebXR select event as a fallback), hand grip poses for throwing, and controller support.
* Seated-friendly: the resting head height is calibrated per session, so a small duck counts whether you sit or stand,
  and covering your eyes with your paws is an alternative that needs no body movement at all.
* Everything is drawn in code: the comic characters, props and the pop-up campsite are painted onto canvases at
  start-up (thick ink outlines, flat colours, halftone shadows) and shown as paper cut-outs and puppets in 3D space.
  Your hands become raccoon paws. The static backdrop is merged into a few draw calls. Sound effects are synthesized
  with the Web Audio API. There are no model, image or audio files to download.
* Throwing uses the hand's velocity history plus a light aim assist (about 14°), so throws feel fair.
* Tested in the IWSDK Meta Quest 3 emulator (IWER) with emulated hand tracking.

This repository contains the compiled web build that GitHub Pages serves.

© 2026 Lilith Moritz. All rights reserved.
