# Journal de traitement des retours de revue

Équipe : ADAM Jérémie, AUNE Amaury, LEMOINE Benjamin, POYET Maxime (dépôt `pomaxime/Client-CLI`)
Relue par : Romain-g-make, timeoblrynov, Lodgia, WayeNot (comptes GitHub des relecteurs)
Date : 13 octobre 2026

> Une ligne par retour reçu. Aucun retour ne reste sans ligne.
> Écarter un retour est permis : la raison s'écrit ici et à l'endroit du retour.
> Quand une synthèse contient plusieurs remarques, chaque remarque a sa ligne.

| Retour reçu | Portée | Décision | Trace |
|---|---|---|---|
| [#12](https://github.com/pomaxime/Client-CLI/issues/12) — Merges manquants : fichiers vides ou absents sur `main` | bloquant (aucune étiquette donnée, attribuée par nous) | Corrigé : les PR #9, #10 et #11 avaient été fusionnées dans `Fusion` au lieu de `main` ; la PR #18 ramène ces fichiers sur `main` | [PR #18](https://github.com/pomaxime/Client-CLI/pull/18) |
| [#13](https://github.com/pomaxime/Client-CLI/issues/13) — Documents annoncés dans le README introuvables, `demarrage.md` et `reglages.md` vides | bloquant | Corrigé : fichiers ramenés sur `main` (PR #18), `reglages.md` complété par la fusion de la branche `Maxime`, renvois du README alignés sur les fichiers réels (PR #20) | [PR #18](https://github.com/pomaxime/Client-CLI/pull/18), [PR #20](https://github.com/pomaxime/Client-CLI/pull/20) |
| [#14](https://github.com/pomaxime/Client-CLI/issues/14) — Accents manquants dans l'introduction du README | détail | Corrigé | commit `3bb96a5`, [PR #18](https://github.com/pomaxime/Client-CLI/pull/18) |
| [#15](https://github.com/pomaxime/Client-CLI/issues/15) (1/4) — « Résultat attendu » du README affiché comme du code | détail | Corrigé : remplacé par une liste à puces | [PR #20](https://github.com/pomaxime/Client-CLI/pull/20) |
| [#15](https://github.com/pomaxime/Client-CLI/issues/15) (2/4) — Des PR n'ont pas d'étiquette (label) | suggestion | Retenu : règle ajoutée dans la section « Contribution » du README ; les PR #19, #20 et #21 portent l'étiquette `documentation` | [PR #20](https://github.com/pomaxime/Client-CLI/pull/20) |
| [#15](https://github.com/pomaxime/Client-CLI/issues/15) (3/4) — Intitulés de commits peu clairs (`[FIX]`, `[MERGE]`) | suggestion | Écarté : renommer des commits déjà publiés sur `main` impose une réécriture de l'historique et un push forcé, qui casserait les liens des PR et issues existantes et les clones des relecteurs. La convention de nommage est précisée dans le README et s'applique aux prochains commits | [Réponse écrite sur #15](https://github.com/pomaxime/Client-CLI/issues/15) |
| [#15](https://github.com/pomaxime/Client-CLI/issues/15) (4/4) — Coquille « READMEEEEEEEEEEEEE » dans l'issue #1 | détail | Corrigé : texte de l'issue #1 modifié | [Issue #1](https://github.com/pomaxime/Client-CLI/issues/1) |
| [#16](https://github.com/pomaxime/Client-CLI/issues/16) — « Manque de documents, orthographe à revoir » | synthèse (reprend #13 et #14) | Corrigé : voir les lignes #13 et #14 | [PR #18](https://github.com/pomaxime/Client-CLI/pull/18), [PR #20](https://github.com/pomaxime/Client-CLI/pull/20) |
| [#16](https://github.com/pomaxime/Client-CLI/issues/16) — README très clair, propos cohérents | bravo | Retenu : la structure du README est conservée, seuls les renvois cassés ont été corrigés | [PR #20](https://github.com/pomaxime/Client-CLI/pull/20) |
| [#17](https://github.com/pomaxime/Client-CLI/issues/17) — `docs/demarrage.md` est vide, l'utilisateur n'est pas guidé | bloquant | Corrigé : le fichier est rempli sur `main` depuis la PR #18 ; la PR #20 ajoute les prérequis, la commande de clonage et un avertissement sur `startCloud.py`, absent du dépôt | [PR #18](https://github.com/pomaxime/Client-CLI/pull/18), [PR #20](https://github.com/pomaxime/Client-CLI/pull/20) |
| [#17](https://github.com/pomaxime/Client-CLI/issues/17) — `docs/architecture.md` très réussi | bravo | Retenu : le schéma est conservé ; seul le tableau des éléments a été corrigé (des noms de membres figuraient dans les colonnes « Rôle » et « Remplaçable par ») | [PR #20](https://github.com/pomaxime/Client-CLI/pull/20) |

## Les deux décisions que nous justifierons à l'oral

### Décision 1 — Ramener la documentation sur `main` par une seule PR depuis `Fusion`

- Contrainte : les PR #9, #10 et #11 avaient été fusionnées dans `Fusion` au lieu de `main` ;
  les relecteurs trouvaient un dépôt vide (issues #12 et #13).
- Options envisagées : rouvrir une PR par document vers `main`, ou une seule PR `Fusion` → `main`.
- Critère retenu : débloquer la revue en cours le plus vite possible sans perdre l'historique
  des PR déjà relues.
- Coût assumé : la PR #18 regroupe 12 commits, plus longue à relire qu'une PR par sujet.

### Décision 2 — Ne pas réécrire l'historique des commits

- Contrainte : des intitulés de commits peu parlants (`[FIX]`, `[MERGE]`) sont déjà publiés sur `main`.
- Options envisagées : réécrire l'historique (rebase interactif puis push forcé), ou le conserver
  et appliquer la convention aux commits suivants.
- Critère retenu : ne casser aucune référence existante (PR, issues, clones des relecteurs).
- Coût assumé : les anciens intitulés restent visibles dans l'historique.
