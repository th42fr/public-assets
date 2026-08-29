# Charte graphique TH42

## Le logo

« TH42 » en composition étagée : le « 42 » descend sous la ligne du « T », et le pied du
« H » vient se poser au même niveau que le bas du « 42 ». Écriture penchée à **11,8°**.

Le **haut de la barre horizontale du « 4 » est aligné sur le pied du « T »**. C'est la
règle de construction du logo ; elle ne se règle pas à l'œil.

## Couleurs

| Rôle | Valeur | Où |
|---|---|---|
| Noir de marque | `#000000` | le « TH » sur fond clair |
| Blanc cassé | `#EDEDED` | le « TH » sur fond sombre |
| Orange bas | `#E17A00` | bas du dégradé du « 42 » |
| Orange haut | `#FFE434` | haut du dégradé du « 42 » |
| Aplat de référence | `#F7AD00` | quand un dégradé est impossible |
| Orange texte | `#AD5200` | **seul** orange admis pour du texte sur blanc |

Les valeurs machine sont dans `brand/tokens/` (CSS, SCSS, JSON).

### Le dégradé

Vertical, **foncé en bas, clair en haut**. `linear-gradient(0deg, #E17A00 0%, #FFE434 100%)`.

Le sens ne s'inverse jamais, et le dégradé ne devient jamais horizontal ou diagonal.
C'est ce qui porte la lecture du logo : une montée du brut vers le clair. Le jour où le
logo est pivoté — kakémono vertical, tranche — c'est le **support** qui pivote, pas le
dégradé : on repart d'un fichier dédié plutôt que de faire tourner celui-ci.

### Contraste

Sur fond blanc, l'orange du « 42 » plafonne à 1,9:1. Il ne porte donc jamais de texte et
ne sert jamais à distinguer une information essentielle. Pour du texte, `#AD5200` — 5,27:1,
conforme WCAG AA.

## Ce qu'on ne fait pas

- Recolorer le logo, ou remplacer le dégradé par une autre couleur.
- Étirer, comprimer, incliner davantage, ou faire pivoter.
- Poser le logo couleur sur un fond sombre : il existe une version pour ça.
- Reconstruire le logo en texte avec une police. Un traitement typographique cousin est
  prévu pour le contenu courant, il est décrit dans `docs/integration-web.md` — mais ce
  n'est pas le logo et il ne le remplace pas.
- Ajouter une ombre portée, un contour, un halo.

## Zone de respiration

Réserver autour du logo une marge au moins égale à la **hauteur du « T »**. Rien ne vient
dans cette zone : ni texte, ni filet, ni bord de page.

## Tailles minimales

| Support | Minimum | Pourquoi |
|---|---|---|
| Écran | 110 px de large | en dessous, le « 42 » s'efface devant le « TH » |
| Tampon encreur | 20 mm de large | l'écart le plus étroit entre deux lettres vaut 2,73 % de la largeur ; à 20 mm cela fait 0,55 mm, au-dessus du seuil de gravure |
| Favicon | pas de minimum | le fichier `favicon/` est prévu pour, mais à 16 px le logo complet n'est plus lisible : c'est assumé |
