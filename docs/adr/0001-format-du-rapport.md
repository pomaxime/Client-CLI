# 0001 — Produire le rapport en texte tabulaire pour la lecture et en JSON pour le dépôt distant

Statut : accepté — 13 octobre 2026
Rédaction : LEMOINE Benjamin — Relecture : AUNE Amaury

## Contexte

Les faits connus au moment du choix, sans argument ni opinion.

- Le rapport de synthèse est d'abord lu par des humains, dans un terminal.
- Le service de dépôt distant accepte les rapports au format JSON.
- L'atelier ne dispose d'aucun outil de visualisation pour lire un fichier JSON.
- Le schéma d'architecture (`docs/architecture.md`) prévoit deux sorties distinctes :
  un fichier écrit dans `rapports/` et un envoi HTTPS vers le service de dépôt.

## Options examinées

### Option 1 — Texte tabulaire uniquement

- Ce qu'elle apporte : le rapport se lit directement dans le terminal, sans aucun outil.
- Ce qu'elle coûte : le service de dépôt ne l'accepte pas ; chaque dépôt demande une
  conversion manuelle en JSON, source d'erreurs de recopie.

### Option 2 — JSON uniquement

- Ce qu'elle apporte : le rapport est accepté tel quel par le service de dépôt ; un seul
  format à produire et à tester.
- Ce qu'elle coûte : le rapport devient pénible à lire dans un terminal (accolades,
  guillemets, pas d'alignement), et l'atelier n'a aucun outil pour le mettre en forme.

### Option 3 — Texte tabulaire dans `rapports/` et JSON pour l'envoi

- Ce qu'elle apporte : chaque destinataire reçoit le format qu'il sait lire, l'humain
  comme le service de dépôt.
- Ce qu'elle coûte : deux sorties à écrire, à maintenir et à tester, avec un risque
  d'écart entre elles.

## Décision

Option retenue : option 3, texte tabulaire dans `rapports/` et JSON pour l'envoi.
Critère qui a fait pencher la balance : c'est la seule option qui sert les deux lecteurs
du rapport (un humain dans un terminal, le service de dépôt) sans étape manuelle.

## Conséquences

- Ce que cela rend facile : lire un rapport sans outil supplémentaire, et le déposer
  sans conversion manuelle.
- Ce que cela rend difficile : toute évolution du contenu du rapport (nouveau
  champ, nouveau calcul) doit être faite deux fois, dans le texte et dans le JSON, et
  testée deux fois.
- Ce qu'il faudra surveiller : que les deux sorties contiennent toujours les mêmes
  valeurs (nombre de mesures, moyenne, minimum, maximum, doublons).

---

> Une fiche ne se réécrit pas. Si la décision change, créez la fiche suivante
> et passez celle-ci au statut « remplacé », avec un renvoi vers la nouvelle.
