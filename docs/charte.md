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

### Sur fond sombre

Fond de référence `#121212` ; plage admise : sombres **neutres** de `#000000` à `#1A1A1A`.
Sur fond sombre, l'orange texte est l'aplat `#F7AD00` (9,75:1 sur `#121212`, mesuré) —
`#AD5200` y échoue (3,55:1) et reste réservé au fond clair. L'aplat et le dégradé du
« 42 » sont inchangés sur fond sombre. Registre « attention » : fond `#312300`, texte
`#F7AD00` (7,97:1). Les valeurs et les contrastes mesurés sont dans
[`brand/tokens/`](../brand/tokens/).

### Gamme d'ambiance

Pour les fonds et décors, une gamme dérivée est admise : toute couleur d'ambiance vaut
`color-mix(in srgb, #F7AD00, white P%)` avec P ∈ [35 %, 75 %] (`#FACA59` → `#FDEABF`).
Fonds et décor **uniquement** — jamais de texte dans ces couleurs, jamais dans la zone de
respiration du logo ; sur un fond d'ambiance, le texte est en noir. Dégradés d'ambiance :
deux stops maximum pris dans la gamme, angle libre **sauf** vertical avec le stop bas plus
foncé que le stop haut — cette configuration est la signature du logo, elle lui est
réservée.

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

## Tailles : la règle à deux niveaux

La marque carrée [`th42-mark.svg`](../brand/logo/th42-mark.svg) est la **variante
compacte officielle**. Trois bandes, à l'écran :

| Largeur disponible | Forme obligatoire |
|---|---|
| ≥ 110 px | logo complet — en dessous, le « 42 » s'efface devant le « TH » |
| 32 à 110 px | marque carrée (navbar, signature, pastille) |
| < 32 px | fichiers de `favicon/` uniquement, jamais de redimensionnement maison |

Le logo complet ne descend jamais sous 110 px : réduit davantage, il n'est plus le logo.

Hors écran : tampon encreur, 20 mm de large minimum.
