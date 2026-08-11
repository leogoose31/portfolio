# CLAUDE.md

Instructions permanentes pour toute session de travail sur ce dépôt.
Lis ce fichier avant toute modification.

---

## 1. Ce qu'est ce projet

Portfolio personnel statique, construit avec **Quarto** et déployé sur **GitHub Pages**.

Objectif unique : qu'un recruteur ou un manager comprenne en moins de 90 secondes
qui je suis, ce que je sais faire, et ait envie d'ouvrir un projet.

Ce n'est **pas** un blog, **pas** un site académique, **pas** une vitrine technologique.
Chaque décision (contenu, design, code) se juge à l'aune de cet objectif.

---

## 2. Audience et registre

Lecteur type : recruteur ou manager opérationnel. Il scanne, il ne lit pas. Il n'est pas ingénieur.

Règles d'écriture :

- Un titre est un **résultat ou une question métier**, jamais un nom de technologie.
  Bien : « Où part la marge : décomposition d'un écart de 4 points ».
  Mal : « Analyse de variance avec dbt et DuckDB ».
- Chaque projet répond à quatre questions, dans cet ordre : quel problème, quelle approche,
  quel résultat chiffré, quelles limites.
- Voix active, phrases courtes, pas de superlatif, pas de jargon non défini.
- Bannis : « passionné par la data », « solutions innovantes », « leverage », « game changer »,
  toute formulation qui pourrait figurer sur n'importe quel autre portfolio.
- Le code est une **preuve**, pas le sujet. Il est accessible en un clic (lien vers le dépôt),
  jamais déversé dans la page.

---

## 3. Stack et contraintes techniques

- **Quarto** (projet de type `website`), sortie HTML.
- Le rendu HTML de Quarto repose sur **Bootstrap 5** et sur un système de couches SCSS.
  Ordre de fusion : `uses` → `functions` → `defaults` (variables) → `mixins` → `rules`.
- Déploiement : GitHub Pages.
- **Pas** de framework JS, pas de build Node, aucune dépendance à l'exécution.
- Contrainte de performance : maximum 2 familles typographiques, images compressées,
  aucune librairie chargée pour un seul effet visuel.

---

## 4. Arborescence

```
.
├── _quarto.yml          # configuration du site (navbar, listings, thème)
├── index.qmd            # accueil : positionnement + projets mis en avant
├── about.qmd            # parcours détaillé
├── projects/
│   ├── index.qmd        # listing des projets
│   └── <slug>/
│       ├── index.qmd    # la page projet
│       └── img/
├── custom.scss          # UNIQUE fichier de style
├── assets/              # cv.pdf, images globales
└── _site/               # GÉNÉRÉ — ne jamais éditer
```

Ne jamais modifier `_site/`, `docs/`, `.quarto/` : ce sont des artefacts de build.

---

## 5. Règles de style — non négociable

Tout le style passe par le système SCSS de Quarto, jamais par du CSS d'override.

- Un seul fichier de thème : `custom.scss`, déclaré via `theme: [<base>, custom.scss]`
  dans `_quarto.yml`.
- Deux régions uniquement :
  - `/*-- scss:defaults --*/` → **exclusivement** des variables Sass
  - `/*-- scss:rules --*/` → les règles CSS, après compilation de Bootstrap
- La région `defaults` se structure en deux blocs :
  1. les tokens du projet (palette, familles typographiques, échelle, espacements)
  2. le mapping vers les variables Quarto / Bootstrap :
     `$body-bg`, `$body-color`, `$primary`, `$link-color`, `$navbar-bg`, `$navbar-fg`,
     `$navbar-hl`, `$footer-bg`, `$code-bg`, `$code-color`,
     `$font-family-sans-serif`, `$headings-font-family`, `$h1-font-size`…

### Interdits stricts

- `!important` : interdit. Si une règle ne prend pas, c'est qu'une variable Sass existe
  pour ça — la chercher dans la documentation Quarto/Bootstrap avant d'écrire du CSS.
- Aucune valeur hexadécimale, aucune taille de police, aucune valeur d'espacement en dur
  dans `scss:rules`. Uniquement des variables définies dans `scss:defaults`.
- Pas de `styles.css` en parallèle du SCSS. Une seule source de vérité.
- Pas de `style="..."` inline dans les `.qmd`.
- Pas de HTML brut dans le contenu quand une construction Quarto existe.

---

## 6. Système de design

Toutes les valeurs ci-dessous vivent dans `scss:defaults` et nulle part ailleurs.

| Token | Rôle |
|---|---|
| `$paper` | fond de page |
| `$ink` | texte courant |
| `$ink-muted` | métadonnées, légendes |
| `$accent` | **un seul** accent : liens, éléments actifs |
| `$rule` | filets, bordures, séparateurs |

Principes d'exécution :

- Échelle typographique modulaire (un ratio unique), pas de taille arbitraire.
- Mesure de ligne entre 65 et 75 caractères sur le contenu long.
- Rythme vertical construit sur une unité d'espacement unique et ses multiples.
- Un seul rayon de bordure pour tout le site (y compris 0).
- Aucune ombre portée décorative, aucun dégradé, aucune animation qui ne serve pas la lecture.
- La sobriété n'est pas une absence de parti pris : la précision de l'espacement et de la
  typographie **est** le parti pris. Une seule audace visuelle, à un seul endroit.

---

## 7. Utiliser le natif Quarto avant d'écrire du markup

Avant de produire du HTML custom, vérifier qu'une fonctionnalité Quarto ne fait pas le travail :

- `listing:` en YAML (avec template EJS si nécessaire) plutôt qu'une grille de cartes à la main
- `::: {.grid}` / `.g-col-*` plutôt qu'un système de colonnes maison
- `.column-page`, `.column-screen` pour les largeurs
- callouts, `about:` templates, `title-block-banner`

Si du HTML brut est réellement nécessaire, l'isoler dans un partial (`_includes/`),
jamais au milieu du contenu rédactionnel.

---

## 8. Structure imposée d'une page projet

Toute page dans `projects/<slug>/index.qmd` suit exactement ce plan :

1. **Titre** — le résultat ou la question, pas la technologie
2. **Chapô** — une phrase, ce que le lecteur va apprendre
3. **Bloc méta** — rôle, période, stack, lien dépôt / démo
4. **Le problème** — 3 à 5 lignes, contexte et enjeu
5. **L'approche** — un schéma vaut mieux qu'un paragraphe
6. **Le résultat** — chiffré, avec le point de comparaison
7. **Limites** — ce qui ne tient pas, ce que je ferais différemment
8. **Reproduire** — lien vers le dépôt et les données

Cible : 600 à 900 mots, 3 visuels maximum, aucun bloc de code de plus de 15 lignes.

---

## 9. Comment travailler sur ce dépôt

- **Planifier avant de coder.** Pour toute tâche de style : lister d'abord les variables Sass
  qui seront utilisées, puis identifier ce qui ne peut pas être obtenu par variable et
  nécessitera une règle CSS. Attendre validation avant d'éditer.
- **Une tâche = un commit atomique**, message à l'impératif.
- **Pas de refonte non demandée.** Ne pas « améliorer » au passage un fichier hors périmètre.
- **Ne jamais inventer de contenu factuel me concernant** : chiffres, missions, résultats,
  dates, clients. En cas d'information manquante, écrire `[À COMPLÉTER]` et me le signaler.
  C'est une règle absolue : une donnée inventée sur un portfolio est un risque professionnel.
- Poser une question quand le brief est ambigu plutôt que de combler le vide par défaut.

---

## 10. Definition of done

Une tâche n'est pas terminée tant que les six points suivants ne sont pas vérifiés :

1. `quarto render` passe sans erreur ni warning
2. le rendu a été vérifié en mode clair et en mode sombre si les deux sont configurés
3. le rendu a été vérifié en largeur mobile
4. le diff ne contient aucun `!important`, aucun hex hors `scss:defaults`
5. contraste texte/fond conforme WCAG AA, focus clavier visible
6. tous les liens internes et externes ajoutés répondent

---

## 11. Commandes

```bash
quarto preview                 # serveur local avec rechargement
quarto render                  # build complet
quarto publish gh-pages        # déploiement
```