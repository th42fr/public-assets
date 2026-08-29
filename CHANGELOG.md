# Journal des assets

Format : [Keep a Changelog](https://keepachangelog.com/fr/1.1.0/).
Les versions sont taguées et servent de point d'épinglage jsDelivr.

## [Non publié]

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
