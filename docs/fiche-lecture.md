# Fiche de lecture critique d'un guide technique

Document analysé : `README.md` du dépôt-modèle `trv-collab-et-doc-tech`
Rédaction : POYET Maxime — Relecture : LEMOINE Benjamin

> Vous ne jugez pas le contenu technique du document : vous jugez sa structure
> et sa capacité à rendre un lecteur autonome.

| # | Critère | Constat | Renvoi (section ou page) |
|---|---|---|---|
| 1 | Objectif annoncé dès l'ouverture | **Non.** Le README présente clairement le rôle de `releve-cli`, mais n'indique pas explicitement ce que le lecteur saura faire à la fin de la lecture. | Introduction, paragraphe de présentation de `releve-cli` |
| 2 | Prérequis explicites | **Non.** Le README indique qu'il faut suivre le guide de démarrage avant la première utilisation, mais ne donne pas lui-même la liste des prérequis nécessaires. | Section « Démarrage », début du README |
| 3 | Contexte et périmètre | **Partiel / non explicite.** Le contexte du dépôt-modèle et le rôle de `releve-cli` sont présentés, mais le périmètre de ce que le README ne traite pas n'est pas défini. | Introduction et sections « Démarrage » / « Configuration » |
| 4 | Étapes numérotées et vérifiables | **Non.** Le README ne contient pas de procédure numérotée permettant de réaliser et vérifier les actions une par une ; il renvoie vers le guide de démarrage. | Section « Démarrage » |
| 5 | Encadrés typés (définition, avertissement, vérification) | **Non.** Aucun encadré clairement identifié comme définition, avertissement ou vérification n'est utilisé dans le document. | Ensemble du README |
| 6 | Liste de contrôle finale | **Non.** Aucun checklist final ne permet au lecteur de vérifier seul qu'il a terminé correctement les actions demandées. | Fin du README, avant « Contribuer » |
| 7 | Lexique et sources datées | **Non.** Aucun lexique n'est fourni pour les termes ou sigles utilisés et les sources citées ne sont pas datées. | Sections « Contribuer » et liens vers les documents complémentaires |

## Le test décisif

Une personne qui n'a jamais vu ce projet peut-elle suivre ce document seule,
jusqu'au bout, sans poser de question ?

**Réponse argumentée : Non.**

Le README donne une présentation générale du projet et indique où trouver plusieurs
documents complémentaires, mais il ne permet pas à lui seul de réaliser le parcours
complet. Il manque notamment des prérequis explicites, des étapes numérotées et
vérifiables, un périmètre clairement défini et une liste de contrôle finale. Le lecteur
doit donc consulter d'autres documents pour terminer correctement la procédure.

## Ce que je corrige dans notre propre documentation

C'est la section qui compte. Deux corrections concrètes, applicables aujourd'hui.

1. **Ajouter un objectif explicite au début de `README.md`.** Le README doit annoncer
   clairement ce que le lecteur doit être capable de comprendre ou de faire après sa
   lecture. **Cette correction est déjà appliquée dans notre dépôt** : une section
   « Objectif » a été ajoutée après la présentation du projet.

2. **Ajouter une section « Prérequis » explicite dans `README.md`.** Elle doit lister
   les éléments nécessaires avant de commencer (matériel, connexion, logiciels ou
   autres conditions utiles) afin que le lecteur puisse vérifier son environnement
   avant de suivre le guide de démarrage. Cette correction reste à appliquer.

Correction déjà appliquée dans le dépôt : ajout de la section `## Objectif` dans
`README.md`.
