---
name: Portfolio Léo Gouzy
description: Éditorial-minimaliste « Graphite & Ardoise » — un auditeur qui code, sobre et pédagogue
colors:
  paper: "#FFFFFF"
  paper-alt: "#F8FAFC"
  ink: "#0F172A"
  ink-secondary: "#475569"
  ink-tertiary: "#94A3B8"
  accent: "#0E6F7A"
  accent-hover: "#0A5A63"
  rule: "#E2E8F0"
  chart-primary: "#1F4E5F"
  chart-context: "#94A3B8"
  chart-context-light: "#CBD5E1"
  chart-favorable: "#1B6E8C"
  chart-unfavorable: "#C2611C"
typography:
  display:
    fontFamily: "IBM Plex Sans, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: "2.73rem"
    fontWeight: 600
    lineHeight: 1.05
    letterSpacing: "-0.02em"
  title:
    fontFamily: "IBM Plex Sans, sans-serif"
    fontSize: "1.953rem"
    fontWeight: 600
    lineHeight: 1.15
    letterSpacing: "-0.015em"
  body:
    fontFamily: "IBM Plex Sans, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.65
    letterSpacing: "normal"
  label:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "0.64rem"
    fontWeight: 400
    lineHeight: 1.4
    letterSpacing: "0.08em"
rounded:
  none: "0px"
spacing:
  unit: "1.5rem"
components:
  tag:
    backgroundColor: "{colors.paper-alt}"
    textColor: "{colors.ink-secondary}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: "0.15rem 0.5rem"
  projet-card-title:
    textColor: "{colors.ink}"
    typography: "{typography.title}"
    rounded: "{rounded.none}"
  en-clair:
    backgroundColor: "{colors.paper-alt}"
    textColor: "{colors.ink-secondary}"
    rounded: "{rounded.none}"
    padding: "0.94rem 1.15rem"
  cta-link:
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.none}"
---

# Design System: Portfolio Léo Gouzy

## Overview

**Creative North Star: « La feuille de calcul devenue éditorial »**

Un système éditorial-minimaliste, taillé pour un auditeur financier qui code. La rigueur du chiffre (alignements tabulaires, filets capillaires, gris qui portent le contexte) rencontre un langage typographique contemporain (IBM Plex Sans + Mono, le mono réservé aux labels). La densité est faible et l'espace généreux : la page respire, l'artefact prime, l'interface s'efface. Aucun effet décoratif — pas d'ombre, pas de dégradé, pas d'arrondi — la crédibilité naît de la retenue et de la précision, pas de l'ornement.

Rejets visuels confirmés : le « look SaaS/IA » (Inter, dégradés violet-bleu, cartes-dans-cartes, tuiles d'icônes arrondies, bordure-accent latérale) ; et le CV-plaquette figé (le site prouve en profondeur, il ne résume pas).

**Key Characteristics :**
- Un seul accent (teal), employé avec parcimonie.
- Zéro arrondi, filets 1px, deux graisses (400/600).
- Mono réservé aux eyebrows, labels, tags, méta et chiffres.
- `tabular-nums` généralisé (réflexe d'audit).
- Le gris porte le contexte, la couleur porte le propos.

## Colors

Palette « Graphite & Ardoise » : des blancs et des slates froids très désaturés, un unique accent teal.

### Primary
- **Teal accent** (`#0E6F7A`): l'unique accent d'interface — liens (au survol), état actif de nav, boutons de bascule, eyebrow d'accent. Rare par doctrine.

### Neutral
- **Ink** (`#0F172A`): texte courant et titres — un slate profond, jamais du noir pur.
- **Ink secondary** (`#475569`): méta, légendes, sous-titres, labels — seul gris autorisé pour du texte lisible (AA).
- **Ink tertiary** (`#94A3B8`): usage graphique/décoratif uniquement (contraste ~2,6:1, sous le seuil AA en texte).
- **Rule** (`#E2E8F0`): filets, séparateurs, bordures.
- **Paper / Paper-alt** (`#FFFFFF` / `#F8FAFC`): fond principal / fond des blocs discrets (tags, encadrés « En clair », note méthodologique).

### Graphiques (palette séparée de l'accent d'interface)
- **Chart primary** (`#1F4E5F`): série unique d'un graphique.
- **Chart context** (`#94A3B8`) + **context-light** (`#CBD5E1`): séries de contexte (gris).
- **Favorable / Unfavorable** (`#1B6E8C` / `#C2611C`): remplissages et grands chiffres uniquement, jamais du texte courant.

### Named Rules
**La règle de l'accent unique.** Le teal est le seul accent et n'apparaît que sur une fraction minime de l'écran ; sa rareté est le propos. Le gris tertiaire ne porte jamais de texte lisible.

**La règle « contexte / propos ».** Dans un graphique, le gris porte le contexte et la couleur porte le propos — une seule série colorée par défaut ; sur deux séries, gris (contexte) + teal (propos).

## Typography

**Display / Body Font:** IBM Plex Sans (avec `-apple-system, BlinkMacSystemFont, sans-serif`)
**Label / Mono Font:** IBM Plex Mono (avec `ui-monospace, SFMono-Regular, monospace`)

**Character:** un couple sans/mono d'ingénierie, sobre et contemporain ; le mono en petits labels majuscules crée un rythme identifiable « dev/éditorial ». Deux graisses seulement (400, 600). Échelle Major Third (ratio 1.25). Polices auto-hébergées, aucune dépendance réseau.

### Hierarchy
- **Display / Hero** (600, ~2,73rem, 1.05, `-0.02em`): le nom sur l'accueil.
- **Title / h1** (600, 1.953rem, 1.15, `-0.015em`): titre de page.
- **Section / h2** (mono, 0.8rem, majuscules, `0.1em`, ink-secondary): intertitre-label.
- **Body** (400, 1rem, 1.65, `max-width: 68ch`): texte courant.
- **Label / eyebrow / tag / méta** (mono, 0.64–0.8rem, `0.08em`, majuscules): repères, tags, dates, en-têtes de tableau.

### Named Rules
**La règle du mono-label.** Le monospace est réservé aux labels, eyebrows, tags, méta et chiffres — jamais au texte courant. Tout label mono majuscule partage le même `letter-spacing` (0.08em).

## Layout

Colonne unique centrée, largeur de lecture plafonnée (`max-width: 68ch` sur le corps). Rythme vertical piloté par une **unité d'espacement unique** (`$sp = 1.5rem`) déclinée en `calc()` — pas de valeurs d'espacement en dur. Densité faible, marges généreuses. Responsive : nav qui se replie en menu, tableaux qui reflowent, tags qui passent à la ligne ; aucun débordement horizontal (vérifié à 390px).

## Elevation & Depth

**Aucune ombre, jamais.** La profondeur est portée exclusivement par des **filets 1px** (`{colors.rule}`) et de légers aplats de fond (`{colors.paper-alt}`). Les surfaces sont plates au repos comme en interaction. La hiérarchie vient du contraste typographique et de l'espace, pas de l'élévation.

## Shapes

**Rayon de bordure : zéro, partout** (`0px`). Aucun coin arrondi sur aucun élément (boutons, tags, encadrés, images, champs). Le langage de forme est strictement orthogonal : filets droits, aplats rectangulaires. Les bordures sont des filets 1px `{colors.rule}` ou, pour un bouton affirmé, 1px `{colors.ink}`.

## Components

### Liens & CTA
- **Corps de texte** : couleur teal, souligné **au survol seulement** (`border-bottom` transparent → accent au hover).
- **CTA de navigation** (`.cta-links`, `.cv-download`) : plus affirmés — libellé + chevron `→` ou bouton bordé 1px `{colors.ink}` qui s'inverse en teal au survol.

### Chips / Tags
- **Style :** fond `{colors.paper-alt}`, texte `{colors.ink-secondary}`, mono, **zéro arrondi**, pas de bordure. Taille ≥ 11px (plancher de lisibilité).

### Cards / Containers
- **Carte projet** (`.projet-card`) : séparée par un **filet supérieur 1px**, pas de fond ni d'ombre ni d'arrondi ; titre en `title` (h2), description en `ink-secondary`, rangée de tags.
- **Encadré « En clair »** (composant signature) : fond `{colors.paper-alt}`, padding généreux, **aucune bordure latérale accent** (proscrite). Amorce en gras « En clair : », contenu de vulgarisation.
- **Note méthodologique** : filet haut + bas, fond `{colors.paper-alt}`.

### Navigation
- Navbar claire, liens `ink-secondary` → `ink` au survol, page active en `ink` gras ; icônes de contact (LinkedIn / GitHub / email) à droite ; repli en menu sur mobile. Footer avec copyright + liens de contact.

### Composants métier signature
- **Tableau financier** (`.table-financial-wrap`) : défilement horizontal contenu plutôt que compression — un chiffre n'est jamais tronqué ; en-têtes mono majuscules, `tabular-nums`.
- **Bloc KPI** (`.kpi`) et **delta favorable/défavorable** (`.delta`) : le signe +/− porte l'information (repère non-textuel), la couleur n'est qu'un renfort.

## Do's and Don'ts

- **Do** garder un seul accent teal, employé avec parcimonie.
- **Do** aligner tous les chiffres en `tabular-nums`.
- **Do** réserver le mono aux labels/eyebrows/tags/méta.
- **Do** styler tout graphique à la palette maison : série unique `{colors.chart-primary}` ; deux séries = gris contexte + teal propos, avec légende.
- **Do** plafonner la largeur de lecture (~68ch) et laisser respirer.
- **Don't** utiliser d'ombre, de dégradé ou d'arrondi.
- **Don't** mettre une **bordure-accent latérale** sur un bloc (tell « IA » proscrit).
- **Don't** porter du texte lisible en `ink-tertiary` (sous AA).
- **Don't** saturer le corps de texte de tirets cadratins (cadence « IA ») — virgules, deux-points, parenthèses.
- **Don't** coller d'export de graphique par défaut (Plotly périwinkle, légendes standard) : toujours re-styler à la charte.
