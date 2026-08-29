# Logo TH42 — guide d'usage

Ce qu'il faut savoir pour utiliser les fichiers de ce dépôt. Le choix du bon
fichier selon le support est dans le [`README`](../README.md), l'intégration web
détaillée dans [`integration-web.md`](integration-web.md). La charte graphique
complète est un document interne.

## Couleurs

| Rôle | Valeur | Où |
|---|---|---|
| Noir de marque | `#000000` | le « TH » sur fond clair |
| Blanc cassé | `#EDEDED` | le « TH » sur fond sombre |
| Orange bas | `#E17A00` | bas du dégradé du « 42 » |
| Orange haut | `#FFE434` | haut du dégradé du « 42 » |
| Aplat de référence | `#F7AD00` | quand un dégradé est impossible |
| Orange texte | `#AD5200` | **seul** orange admis pour du texte sur blanc |

Les valeurs machine sont dans [`brand/tokens/`](../brand/tokens/) (CSS, SCSS, JSON).

### Le dégradé

Vertical, **foncé en bas, clair en haut**. `linear-gradient(0deg, #E17A00 0%, #FFE434 100%)`.
Le sens ne s'inverse jamais, et le dégradé ne devient jamais horizontal ou diagonal.
Si un support impose de pivoter le logo — kakémono vertical, tranche — ne faites pas
tourner ces fichiers : un gabarit dédié existe, demandez-le.

### Contraste

Sur fond blanc, l'orange du « 42 » plafonne à 1,9:1. Il ne porte donc jamais de texte et
ne sert jamais à distinguer une information essentielle. Pour du texte, `#AD5200` — 5,27:1,
conforme WCAG AA.

## Ce qu'on ne fait pas

- Recolorer le logo, ou remplacer le dégradé par une autre couleur.
- Étirer, comprimer, incliner davantage, ou faire pivoter.
- Poser le logo couleur sur un fond sombre : il existe une version pour ça.
- Reconstruire le logo en texte avec une police. Un traitement typographique cousin est
  prévu pour le contenu courant, il est décrit dans [`integration-web.md`](integration-web.md) —
  mais ce n'est pas le logo et il ne le remplace pas.
- Ajouter une ombre portée, un contour, un halo.

## Zone de respiration

Réserver autour du logo une marge au moins égale à la **hauteur du « T »**. Rien ne vient
dans cette zone : ni texte, ni filet, ni bord de page.

## Tailles minimales

| Support | Minimum |
|---|---|
| Écran | 110 px de large — en dessous, le « 42 » s'efface devant le « TH » |
| Tampon encreur | 20 mm de large |
| Favicon | pas de minimum : les fichiers de `favicon/` sont prévus pour, en acceptant qu'à 16 px le logo complet ne soit plus lisible |
