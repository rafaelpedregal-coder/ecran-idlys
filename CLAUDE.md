# Écran TV iD.LYS Contrôles – consignes pour Claude

Page affichée en boucle sur la télé de l'agence (Yodeck) : https://rafaelpedregal-coder.github.io/ecran-idlys/
GitHub Pages publie la branche **claude/ecran**, qui est aussi la branche par défaut du dépôt.

## Règles Git (impératives)
- Toujours partir de l'état distant : `git fetch origin && git checkout claude/ecran && git reset --hard origin/claude/ecran`.
- Ne jamais recréer la branche à partir de `main`, ne jamais la supprimer, ne jamais faire de push forcé (`--force`).
- Pousser avec `git push origin claude/ecran`. Si le push est refusé : `git pull --rebase origin claude/ecran` puis repousser.
- Pas de pull request, pas d'autre branche.

## Fichier
Tout est dans `index.html`. Les contenus modifiables sont en haut du <script> :
- `MESSAGES` : informations internes `{ du: "AAAA-MM-JJ", au: "AAAA-MM-JJ", titre: "…", titreBleu: "…", texte: "…" }` (titreBleu = fin du titre en bleu, optionnelle).
- `ANNIVERSAIRES` : `{ prenom, jour: "MM-JJ" }` (mis à jour chaque lundi depuis PayFit).
- `VEILLE` : mis à jour automatiquement chaque jour ouvré par la routine « Écran iD.LYS – veille du jour ». Ne pas y toucher à la main.
- `MOMENTS` : moments de sympathie (Noël, nouvelle année, congés d'été, rentrée).
- `FETES` : fête du jour.

## Règles de contenu
- Quand Rafael demande de publier une information interne : TOUJOURS lui demander pendant combien de jours (et à partir de quand) avant de publier. `du` = date de début, `au` = du + durée − 1.
- Retirer les informations dont la date `au` est passée.
- Ne modifier que le bloc concerné. Vérifier la syntaxe (extraire le <script> et `node --check`).
- Le dépôt et la page sont PUBLICS : jamais de données sensibles (pas d'année de naissance, de données RH, de noms de clients, de stratégie commerciale).
- Commit en français, ex. « Information interne : réunion d'équipe (3 jours) ».
