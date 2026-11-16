[English](README.md) · **Français**

# Color Your Reality

**Dessiner du doigt le contour d'un objet réel dans un casque Meta Quest : l'application nomme l'objet, puis on le colorie.** Tout tourne dans le casque, reconnaissance de l'objet comprise.

[![Le parcours dans l'architecture, étape par étape, avec de vraies captures du Meta XR Simulator (cliquer pour la vidéo complète)](docs/demo.gif)](https://drive.google.com/file/d/1kWA1k3qNKd74l4XSTBcGAOnyaYIjJpeD/view)

*Chaque étape allume son chemin dans le schéma, à côté d'une vraie capture des tests en mode jeu sur le Meta XR Simulator. [Vidéo complète (1:16)](https://drive.google.com/file/d/1kWA1k3qNKd74l4XSTBcGAOnyaYIjJpeD/view)*

## Ce qu'on en fait

- **Dessiner.** Main droite, pincement pouce et index maintenu : on trace autour d'un objet. Un marqueur vert annonce que relâcher fermera la boucle ; un son le confirme.
- **Nommer.** YOLO11n-seg lit l'image de la caméra ; le masque qui recouvre le mieux la boucle donne le nom de l'objet (par exemple « lit »).
- **Colorier.** Main gauche : toucher la forme la remplit du matériau en cours. Pouce et auriculaire : matériau suivant.
- **Retoucher.** Pouce et auriculaire de la main droite font défiler Dessiner, Effacer (la partie touchée) et Supprimer (la forme entière). Une étiquette au-dessus de chaque main indique son outil.
- **Masquer.** Le bouton menu de la manette gauche, ou le geste système de la main gauche, masque ou affiche les contours ; la couleur reste.
- **Reprendre.** Formes, traits et couleurs sont enregistrés dans le casque, ancrés à la pièce. Au lancement : reprendre ou repartir d'une pièce neuve. Aux manettes, la gâchette remplace le pincement.

## Architecture

![Architecture de Color Your Reality : la main droite dessine un contour, YOLO11n-seg le nomme à partir de l'image de la caméra du casque, la main gauche colorie la forme, l'état est enregistré dans le casque ; l'APK rejoint la flotte de casques par Wagon et Meta HMS](docs/architecture.svg)

## Déploiement

- **Casques.** La version 1.5.8 est publiée sur la flotte de casques Quest de l'école par Meta Horizon Managed Services, l'APK hébergée sur le partage de fichiers de l'école (Wagon). La version 1.5.9 (étiquettes des mains) est sur un seul casque de test (octobre 2026).
- **Tests.** 90 tests de l'éditeur sur 91 passent ; l'échec vient d'un test du kit natif, cause non établie. Les scénarios en mode jeu tournent sur le Meta XR Simulator. Les gestes aux manettes et le bouton menu ne sont vérifiés qu'au casque.
- **Historique.** Jusqu'à la 1.4.3, l'application détectait seule les objets dans le scan de la pièce ; les contours sortaient lents et irréguliers, alors les versions suivantes laissent l'utilisateur les dessiner.
- **Pile.** Unity 6, Meta XR SDK, QuestRoomScan, Unity Inference Engine (GPU), YOLO11n-seg au format ONNX.

---

**Anthony Hunt** · [ingevision.cloud](https://ingevision.cloud/?p=color-your-reality) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [GitHub](https://github.com/anthohunt)

Le code et l'application restent dans le dépôt privé de l'école.
