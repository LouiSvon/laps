# LAPS

**Plus de temps pour traverser.** Laps prolonge le vert piéton, à la demande, pour les personnes qui marchent plus lentement (seniors, personnes à mobilité réduite, groupes scolaires). Un boîtier se pose sur les feux existants et ne se déclenche que quand quelqu'un en a besoin.

Projet du défi **Pépite Provence 36h Chrono** (équipe BG5). Ville pilote visée : **Salon-de-Provence**.

> État : prototype de hackathon, version de travail. Les données d'usage du tableau de bord sont **simulées**. Aucune solution n'est installée sur un vrai carrefour.

## Contenu

| Dossier | Quoi |
|---|---|
| [`index.html`](index.html) | Landing page : problème, mini-jeu de traversée, chiffres, solution, boîtier en 3D, prix, collectivité, Salon-de-Provence. |
| [`dashboard/`](dashboard/index.html) | Tableau de bord pour la collectivité (une page HTML, sans serveur). |
| [`modele-3d/`](modele-3d/boitier.stl) | Modèle 3D du boîtier (STL, fait avec OpenSCAD). Aussi converti dans `assets/boitier-stl.js` pour la landing. |
| [`identite/`](identite/) | Logos (SVG et PNG), couleurs, typographie, charte PDF (version test). |
| [`data/`](data/donnees-salon-de-provence.md) | Rapport de données sur Salon-de-Provence, chaque chiffre avec sa source. |

## Lancer en local

Aucune installation : ce sont des pages statiques.

```bash
git clone https://github.com/LouiSvon/laps.git
cd laps
open index.html            # landing page (macOS ; sinon double-clic sur le fichier)
open dashboard/index.html  # tableau de bord
```

La landing charge la police DM Sans (Google Fonts) et la bibliothèque three.js (jsDelivr) pour afficher le boîtier en 3D : une connexion est nécessaire pour ces deux éléments. Le tableau de bord fonctionne hors ligne, avec Arial à la place de DM Sans si la police n'est pas disponible.

## Ce qui est réel, ce qui est simulé

- **Réel :** les 18 carrefours à feux (regroupés à la main depuis OpenStreetMap, un minimum), les 43 établissements scolaires (Éducation nationale), les chiffres de population (INSEE), les statistiques nationales citées sur la landing (ONISR, Cerema, LTA Singapour). Les sources sont listées en bas de la landing et dans [`data/`](data/donnees-salon-de-provence.md).
- **Simulé :** les demandes de temps supplémentaire, les largeurs de chaussée, les durées de vert, les incidents du tableau de bord, et les vitesses de marche du mini-jeu (1,3 m/s adulte, 0,8 m/s senior, 0,8 m/s groupe : hypothèses de démonstration).
- **Prix :** 250 € par boîtier et 72 € par an d'abonnement par boîtier, affichés sur la landing, sont les prix fixés par l'équipe. Les totaux et les coûts par habitant sont des calculs à partir de ces deux prix.
- **Non vérifié :** le cadre réglementaire pour modifier les temps de feu, le gestionnaire des feux de Salon-de-Provence, l'identification de l'usager sur le réseau local.

## Technique

HTML, CSS et JavaScript sans framework, un seul fichier par page. Les graphiques du tableau de bord sont du SVG dessiné à la main, avec une simulation déterministe (générateur pseudo-aléatoire à graine fixe). Le modèle 3D est lu avec three.js (`STLLoader`, `OrbitControls`). Les composants électroniques affichés dans le boîtier (ESP32, module NB-IoT, relais, lecteur NFC) sont des blocs schématiques ajoutés par code : formes et positions indicatives, pas un plan de montage.

## Données et licences tierces

- Carrefours : © contributeurs [OpenStreetMap](https://www.openstreetmap.org/copyright), licence ODbL, extraction du 12/11/2026.
- Établissements scolaires : [Annuaire de l'éducation](https://data.education.gouv.fr/explore/dataset/fr-en-annuaire-education/), Éducation nationale (données ouvertes, licence à confirmer sur la page du jeu de données).
- Polices : DM Sans et DM Mono (SIL Open Font License), via Google Fonts.
- three.js : licence MIT.

## Droits

© 2026 Équipe BG5. **Tous droits réservés** : le code, les logos et la marque LAPS ne sont pas sous licence libre. Le dépôt est public pour être consulté ; toute réutilisation nécessite l'accord de l'équipe.
