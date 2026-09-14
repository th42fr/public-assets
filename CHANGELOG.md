# Journal des assets

Format : [Keep a Changelog](https://keepachangelog.com/fr/1.1.0/).
Les versions sont taguées et servent de point d'épinglage jsDelivr.

## [Non publié]

### Ajouté
- `brand/logo/lockups/` : les **lockups de sous-marques** — TH42 Labs et TH42 Games,
  chacun en trois variantes (`th42-<nom>.svg`, `-dark`, `-auto`), mêmes mécanismes de
  couleur que le logo. Descripteur Chivo Mono 700 vectorisé (aucune fonte à charger),
  corps 14 % de la largeur du logo, interlettrage 0,30 em, centré sur l'axe optique,
  à 80 % de la hauteur de capitale sous l'encre. Lockup en 1,293:1. Liste fermée :
  une sous-marque existe quand son lockup est publié ici.

### Corrigé
- `brand/logo/lockups/` : l'écart vertical logo-descripteur, d'abord publié à
  ½ hauteur du « T » (259 unités — le mot tombait beaucoup trop bas), ramené à
  80 % de la hauteur de capitale (69,6 unités), conformément aux maquettes
  validées. Le lockup passe de 889,7 à 700,3 unités de haut.
- `docs/declinaisons.md` : guide d'usage des déclinaisons — fichiers, cotes relatives,
  règle de taille (≥ 110 px, comme le logo), zone de respiration sur le lockup complet.

## [2.1.0] — 2026-08-30

### Ajouté
- `brand/tokens/` : doctrine du fond sombre — fond de référence `#121212` (plage admise
  `#000000` à `#1A1A1A`, neutres), orange texte sur sombre = `#F7AD00` (9,75:1 mesuré ;
  `#AD5200` reste réservé au fond clair, 3,55:1 sur sombre), registre « attention »
  (`#312300` / `#F7AD00`, 7,97:1). Contrastes mesurés WCAG 2.1 annotés dans `th42.json`.
- `brand/tokens/` : gamme d'ambiance pour fonds et décors —
  `color-mix(in srgb, #F7AD00, white P%)`, P ∈ [35 %, 75 %], bornes `#FACA59` → `#FDEABF` ;
  jamais de texte dans ces couleurs ; dégradés 2 stops max, angle libre sauf la
  configuration verticale foncé-en-bas, réservée au logo.
- `th42.json` : versionné (`$version`), listes fermées `usage`/`interdit` et seuils AA
  (texte 4,5:1, texte large 3:1) pour vérification en CI par les consommateurs.

### Modifié
- `docs/charte.md` : la marque carrée `th42-mark.svg` est déclarée **variante compacte
  officielle** — règle à trois bandes (logo complet ≥ 110 px, marque carrée de 32 à
  110 px, `favicon/` en dessous) ; sections fond sombre et gamme d'ambiance.

## [2.0.0] — 2026-08-29

### Ajouté
- Nouvelle génération du logo, en vectoriel : `brand/logo/` — version couleur, fond sombre,
  bascule automatique clair/sombre, monochromes noir et blanc, marque carrée.
- `brand/tampon/th42-tampon.svg` — version pleine une encre pour tampon encreur.
- `brand/logo/png/` — exports 256, 512 et 1024 px, fond transparent.
- `brand/tokens/` — palette de marque en CSS, SCSS et JSON.
- `favicon/maskable-192x192.png` et `favicon/maskable-512x512.png` — icônes recadrables
  Android, avec la marge de sécurité que le manifeste exigeait sans la fournir.
- `docs/charte.md` et `docs/integration-web.md`.
- `LICENSE` — tous droits réservés.
- `.gitattributes` — fins de ligne normalisées en LF ; sans lui, tout clone Windows
  affichait trois fichiers modifiés dès le départ.

### Modifié
- `favicon/favicon.svg` : contenait un PNG 1024×1024 encodé en base64, soit **1,87 Mo**
  pour une icône de 16 px, et représentait l'ancien logo sur fond gris. Remplacé par un
  vrai tracé de 3 Ko — une division par 610.
- `favicon/favicon.ico`, `favicon-96x96.png`, `apple-touch-icon.png`,
  `web-app-manifest-192x192.png`, `web-app-manifest-512x512.png` : nouveau dessin, mêmes
  chemins. Les icônes sont carrées dans les deux générations, les consommateurs existants
  sont donc mis à jour sans rupture.
- `site.webmanifest` et `favicon/site.webmanifest` : les deux icônes étaient déclarées en
  `purpose: "maskable"` uniquement, ne laissant au système aucune icône non recadrée, et
  leurs chemins pointaient à la racine alors que les fichiers sont dans `favicon/`.
  Corrigé, avec un jeu `any` et un jeu `maskable`. `theme_color` passe de `#ffffff`
  (valeur par défaut du générateur) à `#000000`.

### Gelé
- `logo-th42-classic-1024x1024.png`, `logo-th42-modern-1024x1024.png`,
  `logo-th42-modern-white-1024x1024.png` : ancienne génération, format d'image différent
  de la nouvelle. Ni déplacés, ni supprimés, ni écrasés — des supports extérieurs peuvent
  encore pointer dessus.
