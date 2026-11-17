**English** · [Français](README.fr.md)

# Color Your Reality

**Draw the outline of a real object in a Meta Quest headset: the app names it, then you color it in.** Everything runs on the headset, object recognition included.

[![Drawing around a bed, naming it and coloring it, step by step on the architecture (click for the full video)](docs/demo.gif)](https://drive.google.com/file/d/1zLNwWatbaI9cSe1nty7TUV8rVXNCQdTr/view)

<details><summary>French version</summary>

[![Contour d'un lit, nom, coloriage, étape par étape sur l'architecture (cliquer pour la vidéo complète)](docs/demo.fr.gif)](https://drive.google.com/file/d/1avJORNWjeER0pkDFkrrs19hgJAGHAO3R/view)

</details>

*Drawing around a bed, naming it, coloring it, in the Meta XR Simulator. [Full video (1:16)](https://drive.google.com/file/d/1zLNwWatbaI9cSe1nty7TUV8rVXNCQdTr/view)*

## Using it

- **Draw.** Right hand, thumb and index pinch held: trace around an object. The marker turns green when releasing will close the loop; a sound confirms it. With controllers, the trigger replaces the pinch.
- **Name.** YOLO11n-seg reads the camera image; the mask that best covers the loop names the object, in French (*lit* for a bed). Only common objects get a name (bed, chair, screen, table…).
- **Color.** Left hand: touch the shape to fill it with the current material. Thumb and little finger: next material.
- **Edit.** Thumb and little finger on the right hand cycle Draw, Erase (the part the pinch passes over) and Delete (the whole shape). A label above each hand shows its tool.
- **Hide.** The left controller's menu button, or the left hand's system gesture, hides or shows the outlines; the color stays.
- **Resume.** Shapes, strokes and paint are saved on the headset, anchored to the room. At launch: resume or start a new room.

## Architecture

![Color Your Reality architecture: the right hand draws a contour, YOLO11n-seg names it from the headset camera image, the left hand colors the shape, the state is saved on the headset; the APK reaches the headset fleet through Wagon and Meta HMS](docs/architecture.svg)

<details><summary>French version</summary>

![Architecture de Color Your Reality : la main droite dessine un contour, YOLO11n-seg le nomme à partir de l'image de la caméra du casque, la main gauche colorie la forme, l'état est enregistré dans le casque ; l'APK rejoint la flotte de casques par Wagon et Meta HMS](docs/architecture.fr.svg)

</details>

*App labels are in French.*

## Status

- **Headsets.** Version 1.5.8 is published to the school's Quest fleet through Meta Horizon Managed Services, the APK hosted on the school's file share (Wagon). Version 1.5.9 (hand labels) is on one test headset. State as of October 2026.
- **Tests.** 90 of 91 editor tests pass. Play-mode scenarios run on the Meta XR Simulator; controller gestures and the menu button are checked on a real headset.
- **Versions.** Up to 1.4.3 the app detected objects by itself in the room scan; outlines came out slow and ragged, so later versions let the user draw them.
- **Stack.** Unity 6, Meta XR SDK, QuestRoomScan, Unity Inference Engine (GPU), YOLO11n-seg in ONNX.

---

**Anthony Hunt** · [ingevision.cloud](https://ingevision.cloud/?lang=en&p=color-your-reality) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [GitHub](https://github.com/anthohunt)

The code and the app stay in the school's private repository.
