# Écran d'agence iD.LYS Contrôles

Ce dépôt contient **une seule page** : `index.html`, affichée sur la TV de l'agence par Yodeck.
Adresse publiée : https://rafaelpedregal-coder.github.io/ecran-idlys/

## Règle n° 1 : une seule branche, `main`

- GitHub Pages publie **uniquement la branche `main`**. Ne jamais changer ce réglage.
- Toujours modifier `index.html` sur `main`.
- Si la session ne permet pas de pousser directement sur `main` (branche `claude/...` imposée) : pousser la branche, ouvrir une pull request vers `main` et donner le lien à Rafael pour qu'il la fusionne. Une modification qui n'est pas dans `main` n'apparaît pas à l'écran.
- Ne jamais demander de publier depuis une autre branche.

## Ce qui peut être modifié

Uniquement la zone entre `CONTENU DE L'ÉCRAN` et `Fin de la partie à modifier` dans le `<script>`.
Ne pas toucher au reste (mise en page, logique de défilement, logo).

| Tableau | Usage | Format des dates |
|---|---|---|
| `MESSAGES` | Informations internes : nouveaux clients, points d'attention, réunions… | `du` / `au` en `AAAA-MM-JJ` |
| `VEILLE` | Actualité réglementaire (RE2020, perméabilité, ventilation, accessibilité, CEE…) | `du` / `au` en `AAAA-MM-JJ` |
| `MOMENTS` | Moments de sympathie (fêtes, vacances, rentrée) | `MM-JJ` (chaque année) ou `AAAA-MM-JJ` |
| `FETES` | Fête du jour | clé `MM-JJ` |
| `ANNIVERSAIRES` | **Ne pas modifier à la main** : mis à jour automatiquement chaque lundi depuis PayFit | — |

Champs d'un message : `du`, `au`, `rubrique` (facultatif, « Information interne » par défaut, ex. « Nouveau client », « Point d'attention »), `titre`, `titreBleu` (suite du titre en bleu, facultatif), `texte`.
Champs d'une actu de veille : `du`, `au`, `statut` (ex. « Publié JO », « EN PROJET – non publié au JO », « Presse »), `titre`, `titreBleu`, `texte`, `source`.

## Règle n° 2 : toujours demander la durée d'affichage

Avant d'ajouter **chaque** information (`MESSAGES`, `VEILLE`, ou `MOMENTS` ponctuel) :

1. Demander : « Pendant combien de temps faut-il afficher cette information ? » (ex. aujourd'hui seulement, 3 jours, 1 semaine, jusqu'à une date précise).
2. Renseigner `du` (aujourd'hui par défaut) et `au` (dernier jour d'affichage, inclus). Ne jamais laisser `au` vide.
3. Récapituler à Rafael ce qui sera affiché et jusqu'à quand avant de publier.

L'information disparaît d'elle-même de l'écran après la date `au`. À chaque modification, supprimer aussi des tableaux les entrées dont la date `au` est passée.

## Contenu

- Page **publique** : rien de confidentiel (pas de coordonnées, montants, données personnelles au-delà du prénom et du jour/mois d'anniversaire).
- Marque à utiliser : **iD.LYS Contrôles** (NRJ Diags est la raison sociale, à ne pas afficher).
- Textes courts : un titre et deux phrases maximum par écran.

## Après publication

Vérifier que le commit est bien sur `main`, puis donner le lien de contrôle avec un paramètre anti-cache, par exemple `https://rafaelpedregal-coder.github.io/ecran-idlys/?v=AAAAMMJJHHMM`. La TV se met à jour en 15 à 25 minutes environ.
