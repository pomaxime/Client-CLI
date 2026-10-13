# Service Cloud-Serveur nantais

Ce projet permet de paramétrer un serveur local de Cloud personnel.
Si vous possédez un vieux PC, tournez-le dès maintenant en interface de gestion de votre cloud personnel.

## Objectif

À la fin de la lecture de cette documentation, le lecteur doit pouvoir comprendre le rôle du serveur Cloud-Serveur nantais, préparer le matériel nécessaire, suivre les étapes de mise en place et accéder aux fichiers stockés à distance.

## Installation et démarrage

Prérequis : 
- Tour centrale de PC
- Hard Disk Drive sup.
- Connexion Internet

1. Première étape

    Réparations si nécessaire (changement de pièces)

2. Deuxième étape

    Ajout disque dur supplémentaire

3. Troisième étape

    Connexion internet et mise en route/installation serveur sur la tour 

Résultat attendu :

- Accès aux fichiers à distance depuis n'importe quel appareil

Le lancement de l'outil est détaillé dans `docs/demarrage.md`.

## Usage

### Hébergement à usage personnel

Stockage de fichiers sur un serveur distant, accessible à distance via SSH. 
Le serveur est configuré pour permettre l'accès à un utilisateur unique, qui 
peut y déposer et récupérer des fichiers.

### Consommation des fichiers

Utilisation du serveur pour récupérer des fichiers stockés par soi à partir de 
n'importe quel appareil en reseau local ou externe.

## Architecture

Le système repose sur un serveur distant, qui sert de point d'entrée unique pour 
stocker les fichiers et les rendre récupérables à distance. Les opérations de 
dépôt et de consultation sont orchestrées par un petit ensemble de composants : 
l'accès distant, l'espace de stockage, et les commandes de gestion des fichiers, 
qui assurent le flux entre le poste source et le serveur.

Dans le cas d’un usage personnel, l’utilisateur envoie ses fichiers vers le serveur 
depuis son environnement local ; dans le cas de la consommation, il récupère ensuite 
ces fichiers depuis n’importe quel appareil connecté au réseau.

Le schéma de ces échanges n'est pas encore produit. Le fichier `docs/architecture.md`
et la fiche de décision `docs/adr/0001-format-du-rapport.md` portent sur `releve-cli`,
l'outil de l'Atelier Logiciel Nantais étudié comme fil rouge du module, et non sur
le Cloud-Serveur.

## Organisation du dépôt

| Chemin | Contenu |
| --- | --- |
| `README.md` | Cette page : présentation, installation, usage, architecture. |
| `docs/demarrage.md` | Guide détaillé de démarrage. |
| `docs/reglages.md` | Référence des réglages disponibles. |
| `docs/architecture.md` | Schéma d'architecture de `releve-cli` (fil rouge du module). |
| `docs/adr/` | Fiches de décision technique (ADR), une par décision. |
| `docs/fiche-lecture.md` | Fiche de lecture critique du README du dépôt-modèle. |
| `docs/tableau-repartition.md` | Répartition du travail : qui rédige, qui relit chaque fichier. |
| `docs/journal-revue.md` | Journal de traitement des retours reçus en revue croisée. |
| `.gitignore` | Fichiers exclus du dépôt, dont la configuration réelle `config.txt`. |

Le code source (`src/`) n'est pas encore présent dans le dépôt.

## Contribution

- Une branche par sujet, préfixée `doc/`, `feat/` ou `fix/` (exemple : `doc/architecture`).
- Un message d'enregistrement préfixé par `[ADD]`, `[FIX]`, `[DOCS]` ou `[CHORE]`, suivi de ce que fait le changement.
- Toute modification passe par une demande de fusion (au format PR) vers `main`, relue par un autre membre et étiquetée (label `documentation`, `bug`, `enhancement`…).
- Aucune valeur réelle de configuration n'est enregistrée dans le dépôt.

## Contact

Selfispace - © - ADAM Jérémie | POYET Maxime | AUNE Amaury | LEMOINE Benjamin