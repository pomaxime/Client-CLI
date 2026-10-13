# Architecture de releve-cli

> Dernière révision : 13 octobre 2026 — Statut : version finale du module
> Rédaction : LEMOINE Benjamin — Relecture : POYET Maxime

## Ce que ce document décrit

Une vue d'ensemble de releve-cli, l'outil en ligne de commande de l'Atelier Logiciel
Nantais : quels éléments le composent, ce qui circule entre eux, et par quel moyen.
Ce document ne décrit pas le code source ligne à ligne, ni le service de dépôt distant.

## Hors périmètre

Le service de dépôt des rapports : il est hébergé hors de l'atelier, qui ne le maintient pas.
Seul le flux qui y mène est représenté. La production du fichier de relevés CSV n'est pas
couverte non plus : le schéma part du fichier déjà présent sur le poste.

## Vue d'ensemble

```
+----------------------+
|  Fichier de relevés  |
|  (CSV horodaté)      |
+----------------------+
           |
           |  lecture ligne à ligne
           v
+----------------------+
|  releve-cli          |
|  (lecture + calcul)  |
+----------------------+
      |          |
      |          |  HTTPS, sortant :
      |          |  rapport en JSON
      |          v
      |    (--------------------)
      |    (  Service de dépôt  )
      |    (  hors périmètre    )
      |    (--------------------)
      |
      |  écriture fichier :
      |  rapport texte tabulaire
      v
+----------------------+
|  rapports/           |
+----------------------+

Légende : [ ] élément du projet
          ->  flux sortant
          ( ) élément hors périmètre
```

Le choix des deux formats de sortie (texte et JSON) est justifié dans
`docs/adr/0001-format-du-rapport.md`.

## Tableau des éléments

| Élément | Rôle | Remplaçable par | Contrainte connue |
|---|---|---|---|
| Fichier de relevés (CSV) | Donnée d'entrée : une mesure horodatée par ligne | Tout fichier CSV au même format | Une mesure par ligne, séparateur virgule |
| releve-cli | Lit le fichier, calcule la synthèse, écrit le rapport texte et envoie le JSON | Aucun : c'est le cœur du projet | Lit tout le fichier en mémoire |
| Dossier rapports/ | Conserve les rapports texte produits | Tout dossier accessible en écriture | Seul releve-cli y écrit |
| Service de dépôt | Reçoit les rapports au format JSON | Aucun : imposé et hébergé hors de l'atelier | Hors périmètre de l'atelier |
