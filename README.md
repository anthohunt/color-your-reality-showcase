**English** · [Français](README.fr.md)

> Showcase repository: the code and data of this project are private; this README describes it.

# Color Your Reality

A mixed reality application for the Meta Quest headset: you draw the outline of a real object with your finger, the application recognizes and names it, then you color it in.

## The problem

Coloring a real room requires knowing where each object ends. The first versions started from a 3D scan of the room: the outline appeared poorly and slowly, and the color showed the triangles and holes of the mesh instead of filling the object. The application is used to color the objects around you, with your hands or controllers. It runs on the headset fleet of an engineering school.

## How it works

- Right hand, thumb and index pinch held: Draw, Erase (the touched area) and Delete (the whole shape) tools. Thumb and little finger: next tool.
- When the outline loop closes, a green marker, a sound and a tint signal it.
- An image segmentation model analyzes the drawn area and displays the object's name (for example "bed").
- Left hand: touch the shape to color it. Thumb and little finger: next material.
- A button on the left controller, or the left hand system gesture, shows or hides the outlines.
- With controllers: the trigger replaces the pinch, a short press on the grip changes tool or material.

## What is built

Prototype under headset testing.

- Version 1.5.9: a label above each hand shows the selected tool. It is installed on a single test headset and not yet published.
- Version 1.5.8: published to the fleet of 23 headsets.
- Automated tests in the editor: 90 out of 91 pass. The remaining failure comes from a test of the native development kit, cause not proven.
- Play mode tests on the simulator: drawing, naming, eraser, menu, deletion, controllers and labels pass, backed by screenshots.
- Controller gestures and the menu button are validated only by headset trials.

Up to version 1.4.3, the application detected objects from the room scan. After headset trials, this approach gave way to this "drawing version", where the user traces the outline themselves.

## What is public

This page and the screenshots are public. The code and the application remain in the school's private repository.

## Tech stack

- Unity 6
- Meta XR SDK and Meta XR Simulator
- Meta Quest headset, hand tracking and controllers
- QuestRoomScan (room scan)
- YOLO11n-seg in ONNX format (object segmentation and naming)
