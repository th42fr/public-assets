# Intégrer le logo TH42 sur un site

## Choisir le fichier

Trois cas, trois fichiers.

**Le site est en clair, et le reste.** `brand/logo/th42-logo.svg`.

**Le site est en sombre, et le reste.** `brand/logo/th42-logo-dark.svg` : le « TH » y est
en `#EDEDED`, le fond reste transparent. Il n'y a volontairement pas de plaque noire dans
le fichier — le logo doit pouvoir se poser sur n'importe quel sombre, pas seulement du
noir pur.

**Le site suit le thème du système.** `brand/logo/th42-logo-auto.svg`. Le fichier embarque
sa propre règle `prefers-color-scheme` et bascule seul :

```html
<img src="https://cdn.jsdelivr.net/gh/th42fr/public-assets@v2.0.0/brand/logo/th42-logo-auto.svg"
     alt="TH42" width="120" height="71">
```

Cela fonctionne dans une balise `<img>`, en `background-image` et via `next/image` : le
navigateur propage la préférence de thème au SVG, qui applique sa propre feuille de style.

**La limite à connaître.** Ce fichier suit la préférence du **système**, pas un thème
choisi dans l'interface. Si le site a son propre interrupteur clair/sombre, un visiteur
en OS clair qui choisit le thème sombre verra le logo rester noir. Dans ce cas, deux
options :

- servir `th42-logo.svg` ou `th42-logo-dark.svg` selon l'état de l'interrupteur ;
- ou inliner le SVG, remplacer `fill="#000000"` par `fill="currentColor"` sur le groupe du
  « TH », et laisser le CSS commander. C'est l'option propre en React ou Next.js.

## Proportions

Le logo est en **1,693 : 1**. Toute intégration qui fixe une largeur *et* une hauteur doit
respecter ce rapport, sinon l'image est déformée. Pour une hauteur donnée `h`, la largeur
est `h × 1,693`.

```
hauteur  24 px  ->  largeur  41 px
hauteur  37 px  ->  largeur  63 px
hauteur  48 px  ->  largeur  81 px
```

Attention si tu remplaces un logo existant : l'ancienne version en une ligne était en
2,708 : 1. Reprendre les mêmes attributs `width`/`height` déformerait le nouveau de 37 %.

## Favicon et PWA

Les fichiers sont dans `favicon/`. Dans le `<head>` :

```html
<link rel="icon" href="/favicon/favicon.ico" sizes="32x32">
<link rel="icon" href="/favicon/favicon.svg" type="image/svg+xml">
<link rel="apple-touch-icon" href="/favicon/apple-touch-icon.png">
<link rel="manifest" href="/site.webmanifest">
```

Sous Next.js App Router, les conventions de fichiers ne détectent ces images que dans
`src/app/` : `favicon.ico`, `icon.png`, `apple-icon.png`. Placées ailleurs — dans
`public/icons/` par exemple — elles sont servies mais aucune balise `<link>` n'est
générée, et « Ajouter à l'écran d'accueil » sur iOS retombe sur une capture d'écran.

Le manifeste déclare **deux jeux d'icônes** : `purpose: "any"` et `purpose: "maskable"`.
Les versions maskable sont volontairement plus petites dans leur carré (68 % au lieu de
90 %) parce qu'Android recadre en cercle ou en squircle. Déclarer uniquement `maskable`
laisse le système sans icône non recadrée.

## Écrire « TH42 » dans le contenu

Le logo est une image. Pour le nom écrit dans un titre ou un paragraphe, il existe un
traitement typographique cousin — même pente, même dégradé, hiérarchie rappelée par un
contraste d'échelle. **Ce n'est pas le logo et il ne le remplace pas.**

```html
<span class="th42">TH<span>42</span></span>
```

```css
.th42 {
  font-family: var(--font-urbanist), sans-serif;
  font-weight: 900;
  letter-spacing: -.05em;
  white-space: nowrap;
  display: inline-block;
  transform: skewX(-12deg);
}
.th42 > span {
  font-size: .88em;
  background: linear-gradient(0deg, #e17a00 0%, #ffe434 100%);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}
@media (forced-colors: active) {
  .th42 > span { background: none; color: CanvasText; }
}
```

Trois choses à savoir :

- **`skewX` plutôt que `font-style: italic`.** `font-style` ne permet pas de choisir
  l'angle : `italic` déclenche la pente synthétique du navigateur (13,4°) et
  `oblique 12deg` est purement ignoré. Surtout, la pente synthétique n'élargit pas la
  boîte de l'élément : le haut du « 2 » dépasse de 0,106 em et se fait tronquer par tout
  parent qui coupe. `skewX` pivote autour du centre et reste dans sa boîte.
- **Pas de décalage vertical du « 42 ».** Dans le logo, le « 42 » descend parce que la
  haste du « H » descend avec lui et lui sert d'appui. En texte, cet appui n'existe pas :
  le « 42 » pend dans le vide et se lit comme un indice chimique.
- **En dessous de 20 px, ne pas l'utiliser.** Le dégradé et le contraste d'échelle ne se
  lisent plus, et le résultat ressemble à un défaut d'affichage. Réserver aux titres et
  aux mentions en corps de texte ; jamais dans la navigation ni les mentions légales.

## En e-mail

Aucun de ces procédés ne fonctionne dans un mail : Outlook desktop ne rend pas le SVG,
ne charge pas de police et ignore `background-clip`. Dans une signature, « TH42 » est un
PNG, pas du texte. Le gabarit de signature et ses contraintes feront l'objet d'un ajout ultérieur.
