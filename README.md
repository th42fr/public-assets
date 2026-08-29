# public-assets

Assets publics de **TH42** : logo et ses déclinaisons, favicons, palette de marque.
Ce dépôt est la source de vérité. Tout support — site, signature, réseaux, impression —
consomme ces fichiers plutôt que d'en garder une copie.

## Que prendre, selon le besoin

| Besoin | Fichier |
|---|---|
| Site, fond clair | `brand/logo/th42-logo.svg` |
| Site, fond sombre | `brand/logo/th42-logo-dark.svg` |
| Site qui suit le thème système | `brand/logo/th42-logo-auto.svg` |
| Impression N&B, document administratif | `brand/logo/th42-logo-black.svg` |
| Slide sombre, photo, bandeau | `brand/logo/th42-logo-white.svg` |
| Avatar, icône, format carré | `brand/logo/th42-mark.svg` |
| Tampon encreur | `brand/tampon/th42-tampon.svg` |
| Outils qui refusent le SVG (Office, réseaux) | `brand/logo/png/` |
| Favicon et PWA | `favicon/` |
| Couleurs de la marque | `brand/tokens/` |

Le mode d'emploi détaillé est dans [`docs/integration-web.md`](docs/integration-web.md).
Les règles de la marque — couleurs, sens du dégradé, ce qu'on ne fait pas — sont dans
[`docs/charte.md`](docs/charte.md).

## Servir ces fichiers

`raw.githubusercontent.com` n'est pas un CDN : pas de garantie de cache, et il est bloqué
sur beaucoup de réseaux d'entreprise. Passe par **jsDelivr**, qui sert directement depuis
ce dépôt, gratuitement et sans compte :

```
https://cdn.jsdelivr.net/gh/th42fr/public-assets@v2.0.0/brand/logo/th42-logo.svg
```

Règle d'épinglage :

- **Épingle un tag** (`@v2.0.0`) pour tout ce qui doit rester figé — en particulier les
  images de signature mail : un message envoyé il y a deux ans rappelle l'URL à chaque
  ouverture, et une image écrasée modifierait rétroactivement tous les envois passés.
- **N'épingle pas** (`@main`) pour ce qui doit suivre la marque, comme le favicon d'un site.
  Attention : une URL non épinglée est mise en cache un moment, la mise à jour n'est pas
  instantanée après un push.

## Chemins gelés

Ces fichiers sont l'ancienne génération du logo. Des supports extérieurs peuvent encore
pointer dessus et leur format d'image diffère de la nouvelle version : **ils ne sont ni
déplacés, ni supprimés, ni écrasés.**

```
logo-th42-classic-1024x1024.png
logo-th42-modern-1024x1024.png
logo-th42-modern-white-1024x1024.png
```

Le dossier `favicon/`, lui, garde ses chemins **et** reçoit le nouveau dessin : les icônes
sont carrées dans les deux générations, un consommateur existant est donc mis à jour sans
rien casser. C'est le comportement souhaité pour un favicon.

## Licence

© 2026 TH42. Tous droits réservés — voir [`LICENSE`](LICENSE).
Aucune autorisation d'usage n'est accordée par la publication de ce dépôt.
