# amusoire-simulateur-dist

Artefact de build du **simulateur de chiffre d'affaires Amusoire**, publié ici
dans le seul but d'être servi par un CDN.

## Ne pas modifier ce repo

Le code source vit dans le repo privé `ludobourgoin/amusoire`. Toute correction
se fait là-bas, puis le résultat de `pnpm build` est republié ici sous un
nouveau tag. Une modification faite directement dans ce repo serait écrasée à
la publication suivante, et divergerait silencieusement de la source.

## Utilisation

Le site Webflow Amusoire charge ces fichiers au niveau du site, ce qui permet
de poser le composant simulateur sur n'importe quelle page sans y ajouter de
custom code.

```html
<!-- dans le head du site -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/ludobourgoin/amusoire-simulateur-dist@v1.0.0/dist/index.css" />

<!-- avant la fermeture du body -->
<script defer src="https://cdn.jsdelivr.net/gh/ludobourgoin/amusoire-simulateur-dist@v1.0.0/dist/index.js"></script>
```

**Toujours référencer un tag précis, jamais `@latest`.** Avec `@latest`, un
commit défectueux partirait en production sans aucune intervention.

## Contraintes

- **Une seule instance du simulateur par page.** Le script cible ses éléments
  par identifiant HTML : deux instances dans un même document casseraient la
  seconde, sans message d'erreur.

## Licence

Tous droits réservés. Ce dépôt est public pour permettre la distribution par
CDN, ce qui ne vaut pas autorisation de réutilisation, de copie ou de
modification.
