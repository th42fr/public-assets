# Déclinaisons de sous-marques — guide d'usage

Les sous-marques TH42 (« Labs », « Games », …) existent sous forme de **lockups
officiels** : le logo, intact, accompagné d'un descripteur typographique. Les
fichiers de [`brand/logo/lockups/`](../brand/logo/lockups/) sont **figés** :
on les utilise tels quels, on ne compose jamais un lockup soi-même — ni en
texte à côté du logo, ni en recollant des morceaux.

## Les fichiers

| Sous-marque | Fond clair | Fond sombre | Bascule automatique |
|---|---|---|---|
| TH42 Labs | `th42-labs.svg` | `th42-labs-dark.svg` | `th42-labs-auto.svg` |
| TH42 Games | `th42-games.svg` | `th42-games-dark.svg` | `th42-games-auto.svg` |

La liste est **fermée** : une sous-marque existe quand son lockup est publié
ici, pas avant. Mêmes règles de couleur que le logo : jamais recoloré, jamais
pivoté, dégradé du « 42 » intouchable.

## Construction (pour information — ne pas reproduire)

Toutes les cotes sont relatives à la largeur **L** du logo :

| Paramètre | Valeur |
|---|---|
| Descripteur | Chivo Mono 700, capitales, tracés vectorisés (aucune fonte à charger) |
| Corps | 14 % de L (plancher 12 % pour les mots longs) |
| Interlettrage | 0,30 em |
| Largeur du mot | toujours ≤ ⅔ de L |
| Position | centré sur l'axe optique du logo, sous l'encre, à ½ hauteur du « T » |
| Couleur | celle du « TH » du fichier — le descripteur est monochrome |
| Proportions du lockup | 1,018:1 (quasi carré — 905,5 × 889,7 unités) |

## Tailles

La règle du logo s'applique au lockup entier : **minimum 110 px de large**.
En dessous, ne réduisez pas le lockup : utilisez la marque carrée
(`../brand/logo/th42-mark.svg`) ou les fichiers de `../favicon/` — c'est le
contexte qui nomme la sous-marque.

## Zone de respiration

Comme pour le logo : une marge au moins égale à la hauteur du « T », mesurée
autour du **lockup complet**, descripteur compris.
