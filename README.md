**English** · [Français](README.fr.md)

# Color Your Reality

**Draw the outline of a real object in a Meta Quest headset: the app names the object, then you color it in.** Everything runs on the headset, the object recognition included.

[![The flow through the architecture, step by step, with real captures from the Meta XR Simulator (click for the full video)](docs/demo.gif)](https://drive.google.com/file/d/1kWA1k3qNKd74l4XSTBcGAOnyaYIjJpeD/view)

*Each step lights up its path in the diagram, next to a real capture from play-mode tests on the Meta XR Simulator. [Full video (1:16)](https://drive.google.com/file/d/1kWA1k3qNKd74l4XSTBcGAOnyaYIjJpeD/view)*

## Using it

- **Draw.** Right hand, thumb and index pinch held: trace around an object. A green marker shows when releasing will close the loop; a sound confirms it.
- **Name.** YOLO11n-seg reads the camera image; the mask that best covers the loop names the object, in French (*lit* for a bed).
- **Color.** Left hand: touch the shape to fill it with the current material. Thumb and little finger: next material.
- **Edit.** Thumb and little finger on the right hand cycle Draw, Erase (the part touched) and Delete (the whole shape). A label above each hand shows its tool.
- **Hide.** The menu button of the left controller, or the left hand's system gesture, hides or shows the outlines; the color stays.
- **Resume.** Shapes, strokes and paint are saved on the headset, anchored to the room. At launch: resume or start a new room. With controllers, the trigger replaces the pinch.

## Architecture

![Color Your Reality architecture: the right hand draws a contour, YOLO11n-seg names it from the headset camera image, the left hand colors the shape, the state is saved on the headset; the APK reaches the headset fleet through Wagon and Meta HMS](docs/architecture.svg)

*Diagram and app labels are in French.*

## Deployment

- **Headsets.** Version 1.5.8 is published to the school's Quest fleet through Meta Horizon Managed Services, the APK hosted on the school's file share (Wagon). Version 1.5.9 (hand labels) is on one test headset (October 2026).
- **Tests.** 90 of 91 editor tests pass; the failure is in a native SDK test, cause not established. Play-mode scenarios run on the Meta XR Simulator. Controller gestures and the menu button are checked only on a real headset.
- **History.** Up to 1.4.3 the app detected objects by itself from the room scan; outlines came out slow and ragged, so later versions let the user draw them.
- **Stack.** Unity 6, Meta XR SDK, QuestRoomScan, Unity Inference Engine (GPU), YOLO11n-seg in ONNX.

---

**Anthony Hunt** · [ingevision.cloud](https://ingevision.cloud/?lang=en&p=color-your-reality) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [GitHub](https://github.com/anthohunt)

The code and the app stay in the school's private repository.
