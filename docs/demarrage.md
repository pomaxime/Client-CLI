# Démarrage de l'interface

> Dernière révision : 13 octobre 2026

## Prérequis

- La machine est préparée comme décrit dans `README.md`, section « Installation et
  démarrage » : réparations faites, disque dur supplémentaire installé, connexion Internet.
- Git est installé (`git --version` affiche un numéro de version).
- Python 3 est installé (`python3 --version` affiche un numéro de version).

## Étapes

1. Cloner le dépôt de l'équipe, puis se placer dans le dossier du projet :

   ```
   git clone https://github.com/pomaxime/Client-CLI.git
   cd Client-CLI
   ```

2. Lancer l'outil :

   ```
   python3 startCloud.py
   ```

   > **Avertissement :** `startCloud.py` n'est pas encore présent dans le dépôt. Dans
   > l'état actuel, cette commande s'arrête sur l'erreur
   > `can't open file '.../startCloud.py': [Errno 2] No such file or directory`.
   > Cette étape décrit le lancement prévu.

   Résultat attendu : dans le terminal, un menu de sélection permet de paramétrer l'outil :

   ```
   [] - Sélection de la mémoire
   [] - Configuration des ports
   [] - Monitoring
   ```

Les réglages proposés par ce menu sont décrits dans `docs/reglages.md`.
