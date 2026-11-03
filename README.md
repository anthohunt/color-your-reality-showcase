> Showcase repository: the code and data of this project are private; this README describes it. / Dépôt vitrine : le code et les données de ce projet sont privés ; ce README le décrit.

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

---

## Version française

# Color Your Reality

Une application de réalité mixte pour casque Meta Quest : on dessine du doigt le contour d'un objet réel, l'application le reconnaît et le nomme, puis on le colorie.

## Le problème

Colorier une pièce réelle demande de savoir où s'arrête chaque objet. Les premières versions partaient du scan 3D de la pièce : le contour apparaissait mal et lentement, et la couleur restituait les triangles et les trous du maillage au lieu de remplir l'objet. L'application sert à colorier, avec ses mains ou ses manettes, les objets qui nous entourent. Elle tourne sur la flotte de casques d'une école d'ingénieurs.

## Comment ça marche

- Main droite, pincement pouce et index maintenu : outils Dessiner, Effacer (la zone touchée) et Supprimer (la forme entière). Pouce et auriculaire : outil suivant.
- Quand la boucle du contour se ferme, un marqueur vert, un son et une teinte le signalent.
- Un modèle de segmentation d'images analyse la zone dessinée et affiche le nom de l'objet (par exemple « lit »).
- Main gauche : toucher la forme pour la colorier. Pouce et auriculaire : matériau suivant.
- Un bouton de la manette gauche, ou le geste système de la main gauche, affiche ou masque les contours.
- Avec les manettes : la gâchette remplace le pincement, une pression courte sur la poignée change d'outil ou de matériau.

## Ce qui est construit

Prototype en cours d'essai au casque.

- Version 1.5.9 : un label au-dessus de chaque main indique l'outil choisi. Elle est installée sur un seul casque de test et n'est pas encore publiée.
- Version 1.5.8 : publiée sur la flotte de 23 casques.
- Tests automatisés dans l'éditeur : 90 sur 91 passent. L'échec restant vient d'un test du kit de développement natif, cause non prouvée.
- Tests en mode jeu sur le simulateur : dessin, nom, gomme, menu, suppression, manettes et labels passent, avec captures d'écran à l'appui.
- Les gestes aux manettes et le bouton menu ne sont validés que par des essais au casque.

Jusqu'à la version 1.4.3, l'application détectait les objets à partir du scan de la pièce. Après les essais au casque, cette approche a laissé la place à cette « version dessin », où l'utilisateur trace lui-même le contour.

## Ce qui est public

Cette fiche et les captures d'écran sont publiques. Le code et l'application restent dans le dépôt privé de l'école.

## Pile technique

- Unity 6
- Meta XR SDK et Meta XR Simulator
- Casque Meta Quest, suivi des mains et manettes
- QuestRoomScan (scan de la pièce)
- YOLO11n-seg au format ONNX (segmentation et nom des objets)
