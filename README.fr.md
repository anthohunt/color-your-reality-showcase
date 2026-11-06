[English](README.md) · **Français**

**Anthony Hunt** · [Fiche du projet sur ingevision.cloud](https://ingevision.cloud/?p=color-your-reality) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [Profil GitHub](https://github.com/anthohunt)

> Dépôt vitrine : le code et les données de ce projet sont privés ; ce README le décrit.

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
