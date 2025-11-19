# galerie-php

Petit projet PHP/HTML/CSS pour une galerie — fichier README généré.

## Description

Ce dépôt contient une petite page PHP (`index.php`) et des styles dans `assets/css/`.
Le fichier `assets/css/variables.css` contient la palette de variables CSS utilisées par `assets/css/style.css`.

## Arborescence principale

- `index.php` — page d'entrée
- `assets/css/variables.css` — variables CSS (palette)
- `assets/css/style.css` — styles principaux (importe `variables.css`)
- `assets/js/` — scripts (si présents)
- `pages/` — pages supplémentaires

## Prérequis

- Windows (développement local avec Laragon ou autre serveur PHP)
- Navigateur web
- (optionnel) éditeur de code

## Démarrage local (avec Laragon)

1. Placez le dossier `galerie-php` dans le répertoire www de Laragon (ou utilisez votre configuration actuelle).
2. Lancez Laragon et démarrez Apache/Nginx + PHP (bouton `Start All`).
3. Ouvrez dans votre navigateur :

```
http://localhost/galerie-php/
```

(si votre hôte virtuel diffère, adaptez l'URL)

## Utilisation des variables CSS

Deux façons d'utiliser `variables.css` pour que `style.css` y accède :

### 1) Méthode recommandée — lier les deux fichiers dans le HTML

Dans le `<head>` de `index.php`, charger d'abord `variables.css` puis `style.css` :

```html
<link rel="stylesheet" href="assets/css/variables.css" />
<link rel="stylesheet" href="assets/css/style.css" />
```

Cela garantit que les variables sont définies avant l'application des règles de `style.css` et permet un meilleur contrôle du cache et des performances.

### 2) Option directe — `@import` dans `style.css`

En tête de `assets/css/style.css` :

```css
@import "./variables.css";
```

Simple mais peut ajouter une requête CSS supplémentaire et retarder le rendu. Utile si vous préférez garder l'inclusion côté CSS plutôt que HTML.

## Exemple d'utilisation (extrait)

```css
body {
  background: var(--color-bg);
  color: var(--color-text-primary);
}
.btn {
  background: var(--color-primary);
  color: white;
}
```

## Thème sombre (exemple rapide)

Vous pouvez définir des variables alternatives pour un thème sombre et les activer via un attribut `data-theme` :

```css
:root {
  --color-bg: #ffffff;
  --color-text-primary: #111827;
}
[data-theme="dark"] {
  --color-bg: #0b0b0b;
  --color-text-primary: #ffffff;
}
```

Puis dans le HTML :

```html
<html data-theme="dark"></html>
```

Vous pouvez activer/désactiver dynamiquement ce thème en JavaScript en modifiant l'attribut `data-theme` sur l'élément `<html>`.

## Modifier la palette

Éditez `assets/css/variables.css` pour changer les couleurs globales. Les modifications se propageront aux styles qui utilisent `var(--...)`.

## Suggestions / prochaines améliorations

- Ajouter une variante thème sombre complète.
- Ajouter paliers (50/100/200...) pour chaque couleur pour une API de design plus riche.
- Ajouter tests visuels ou un petit guide de composants.

## Contact

Pour questions ou modifications, éditez directement les fichiers et testez localement, ou créez une issue/PR si vous utilisez un dépôt distant.
