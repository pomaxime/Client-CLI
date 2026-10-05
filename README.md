# releve-cli — Atelier Logiciel Nantais

[Une à deux phrases : ce que fait releve-cli, à qui il s'adresse, dans quel
contexte l'atelier l'utilise. Remplacez ce paragraphe, crochets compris.]

## Installation et démarrage

Prérequis : [matériel, compte ou programme à avoir avant de commencer].

1. [Première étape.]

   ```
   [commande à copier, une par ligne]
   ```

2. [Deuxième étape.]
3. [Troisième étape.]

Résultat attendu : [ce que le lecteur doit constater à la fin].

## Usage
 
### Herbegement à usage personnel

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
ces fichiers depuis n’importe quel appareil connecté au réseau. Le schéma détaillé 
de ces échanges est présenté dans `docs/architecture.md`.

Schéma détaillé : `docs/architecture.md` (produit en séance 3, pas encore présent).

## Organisation du dépôt

| Chemin                 | Contenu                                                                                    |
| ---------------------- | ------------------------------------------------------------------------------------------ |
| `README.md`            | Cette page : présentation, installation, usage, architecture.                              |
| `docs/reglages.md`     | Référence des réglages disponibles.                                                        |
| `docs/demarrage.md`    | Guide détaillé de démarrage.                                                               |
| `docs/architecture.md` | Schéma d'architecture détaillé (à venir, séance 3).                                        |
| `CHANGELOG.md`         | Journal des versions du projet (chapitre 3 : retirez cette ligne si vous ne le créez pas). |
| `config.example.txt`   | Modèle de configuration, sans valeur réelle.                                               |

## Contribution

- Une branche par sujet, nommée `docs/…`, `feat/…` ou `fix/…`.
- Un message d'enregistrement préfixé par `feat`, `fix`, `docs` ou `chore`.
- Toute modification passe par une demande de fusion relue par un autre membre.
- Aucune valeur réelle de configuration n'est enregistrée dans le dépôt.

## Contact

[Nom du binôme] — pour toute question, ouvrez une issue sur ce dépôt.
