# Estimation des coûts et de l'ingénierie - Projet LAPS
**Cas d'usage : Déploiement dans une ville type Salon-de-Provence**

Ce document récapitule les coûts matériels par unité ainsi que les frais globaux de développement nécessaires pour passer du prototype au produit industriel déployable sur la voirie.

## 1. Composants matériels du boîtier (Coûts unitaires estimés)

*   **Microcontrôleur (MCU) de traitement :** 
    Environ 1,64 € HT par unité pour une puce de grade industriel (type ESP32).
*   **Module de connectivité IoT (NB-IoT / LTE-M) :** 
    Entre 8 € et 11 € pour un module électronique nu. Les versions intégrées prêtes à l'emploi (cartes de développement ou émetteurs industriels) coûtent entre 38,58 € HT et 144,00 € HT.
*   **Interface de commande (Module relais 5V ou Optocoupleur) :** 
    Entre 1,61 € HT et 4,96 € HT. Ce composant est indispensable pour commuter le signal vers l'entrée "demande piéton" du contrôleur de feu tricolore sans risque de court-circuit.
*   **Module de lecture NFC/RFID (normes ISO 14443 / Calypso) :** 
    Un kit RFID standard pour le prototypage (Phase 1) coûte environ 6,99 €. En revanche, un lecteur NFC de grade industriel, totalement étanche et sécurisé pour l'extérieur, se situe autour de 288 €.
*   **Enveloppe externe (Plasturgie - Boîtier IP67 / IK10) :** 
    Entre 135,25 € et 153,50 € pour un boîtier extérieur pré-équipé, résistant aux intempéries (étanchéité IP67) et aux chocs/vandalisme (IK10).

## 2. Frais annexes de développement, d'ingénierie et de certification (Coûts fixes et globaux)

Lors du passage à la Phase 2 (Industrialisation) évoquée dans votre business model, de nombreux coûts d'ingénierie s'ajoutent au simple prix des pièces :

*   **Frais d'ingénierie non récurrents (NRE) et outillages :** 
    La conception pour la fabrication (DFM) et surtout la création des moules d'injection plastique pour créer votre propre design de boîtier sur mesure peuvent coûter de quelques milliers d'euros à plus de 100 000 €, selon la complexité et les volumes prévus.
*   **Certification CE (Laboratoire agréé) :** 
    Le passage en laboratoire (LCIE, LNE, Emitech...) pour les tests de compatibilité électromagnétique (CEM) et radio (essentiel pour le NFC et la 4G/IoT) coûte entre 3 000 € et 8 000 €. Ce montant peut atteindre 20 000 € si l'architecture radio est complexe.
*   **Constitution du dossier technique et achat des normes :** 
    L'externalisation de la conformité réglementaire (cabinet d'experts) coûte généralement entre 1 000 € et 3 000 €. Il faut y ajouter l'achat obligatoire des normes AFNOR/ISO spécifiques, représentant souvent plusieurs centaines à milliers d'euros.
*   **Préséries et essais de validation sur site (POC) :** 
    La fabrication de la première petite série (Phase 3 avec les 30 premiers boîtiers) génère des surcoûts liés à l'assemblage manuel, aux ajustements de la chaîne et aux tests de terrain (de quelques milliers à plusieurs dizaines de milliers d'euros).
*   **Études de marché et tests d'usage :** 
    Prévoyez de 1 500 € à 4 000 € pour l'analyse fine de la viabilité et l'évaluation des usagers lors du déploiement pilote.
*   **Coûts de déploiement et de maintenance (Installation) :** 
    Ne pas oublier le coût de la main-d'œuvre de l'entreprise de voirie pour la pose et le raccordement de chaque boîtier au contrôleur du feu (environ 200 € à 400 € de main-d'œuvre par carrefour).