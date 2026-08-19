# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Site statique **Quarto** (pages `.qmd`, thème SCSS custom `custom.scss` + `_components.scss`, polices IBM Plex auto-hébergées). Déploiement automatique sur **GitHub Pages** (branche `gh-pages`) via un workflow GitHub Actions à chaque push sur `main`.

## Users

Deux audiences à parts égales, qui évaluent le profil en quelques minutes, souvent via un lien partagé (LinkedIn) :

1. **Cabinets d'audit / expertise comptable** — recruteurs et associés cherchant un profil hybride finance + data.
2. **Équipes data / analytics** — recruteurs data (analytics engineer, data analyst) qui veulent d'abord la preuve de la compétence technique.

Audience secondaire confirmée : **prospects freelance / conseil** (TPE-PME) pour des missions data/finance.

## Product Purpose

Portfolio personnel de **Léo Gouzy**. Il existe pour convaincre qu'un auditeur financier senior qui code (SQL, dbt, Python) est crédible **à la fois** côté finance et côté data. La réussite se mesure à trois objectifs confirmés par l'auteur :

- décrocher / consolider un **poste senior mêlant audit financier et data analytics** ;
- asseoir une **visibilité professionnelle** cohérente avec le parcours **DEC (mémorialiste)** ;
- générer des **opportunités de mission freelance / conseil**.

## Positioning

Le mécanisme différenciant : **un auditeur qui interroge lui-même les bases qui produisent les chiffres** (SQL, dbt, Python) au lieu de s'arrêter à l'échantillon — la double compétence « référentiels comptables + data engineering » qu'un pur profil data ou un pur auditeur ne peut revendiquer honnêtement. Preuves : mémoire DSCG (modèle ML de prévision), certification Analytics Engineer (DataBird), missions grands comptes (> 1 Md€).

## Operating Context

Surface **« Experience »** (portfolio) : l'artefact prime, l'interface s'efface. Consulté depuis un lien, en desktop et mobile. Trois pages : **Accueil**, **Parcours** (expérience / formation / compétences), **Projets**. Le **Parcours est bilingue FR/EN** (bascule + CV téléchargeable dans les deux langues). Contact présent partout (navbar + footer : email, LinkedIn, GitHub).

## Capabilities and Constraints

- **Voix : sobre & pédagogue.** Rigueur d'auditeur + capacité à vulgariser la data (procédé signature : les encadrés « En clair » qui traduisent le jargon). Français par défaut, anglais sur le Parcours.
- **Anti-référence explicite (confirmée) : ne doit pas être un CV-plaquette figé.** Les projets doivent être **navigables et en profondeur** — le site *prouve*, il ne *résume* pas. Corollaire hérité du design system : pas de « look SaaS/IA » (Inter, dégradés, cartes-dans-cartes, tuiles d'icônes arrondies, bordure-accent latérale).
- **Faits à préserver :** identité (Léo Gouzy, Toulouse, Forvis Mazars) ; certifications (DEC en cours, DSCG, Analytics Engineer DataBird) ; stack affichée (SQL · dbt · Python · Power BI) ; contacts (email, LinkedIn, GitHub).
- **Accessibilité visée : WCAG AA** (documentée et outillée dans `custom.scss` — ratios de contraste commentés, information jamais portée par la couleur seule).
