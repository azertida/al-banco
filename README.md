# Al banco

Application web pour suivre un budget mensuel de cafés et de dépenses au club.

Elle fonctionne dans le navigateur, sans compte ni serveur. Les données restent sur l'appareil, dans le stockage local du navigateur, et ne sont transmises nulle part.

## Ce qu'elle fait

- Afficher le reste du budget du mois dans un anneau, avec le montant dépensé, le montant disponible par jour et les jours restants
- Prévenir quand il reste moins de 20 % du budget, et signaler un dépassement
- Ajouter une dépense en un geste grâce aux raccourcis (café, boisson, repas), ou saisir une autre dépense
- Annuler le dernier ajout, supprimer une dépense
- Parcourir les mois précédents et comparer leur total au budget
- Modifier le budget mensuel et les raccourcis
- Sauvegarder et restaurer l'ensemble des données

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | L'application entière : structure, styles et script |
| `sw.js` | Service worker, pour l'utilisation hors ligne |
| `manifest.webmanifest` | Déclaration PWA (nom, icônes, couleurs) |
| `apple-touch-icon.png` | Icône utilisée par iOS sur l'écran d'accueil |
| `icon-192.png`, `icon-512.png` | Icônes pour Android et le manifeste |

Tous les fichiers vont à la racine du dépôt. Les chemins sont relatifs : un sous-dossier casserait la mise en cache.

## Mise en ligne

1. Déposer les six fichiers à la racine d'un dépôt.
2. Settings → Pages → Source : *Deploy from a branch*, branche `main`, dossier `/ (root)`.
3. Ouvrir l'adresse publiée, puis, sur mobile, l'ajouter à l'écran d'accueil.

## Après chaque modification

Incrémenter `VERSION` dans `sw.js` — `v1` devient `v2`, et ainsi de suite. Sans ça, les appareils qui ont déjà installé l'application continueront de servir l'ancienne version depuis leur cache.
