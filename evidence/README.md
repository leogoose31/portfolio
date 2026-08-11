# Contoso Retail — Evidence

Squelette minimal (pas de `node_modules`, à installer localement).

```bash
cd evidence
npm install
npm run sources   # une fois sources/ configuré
npm run dev
```

## Thème

`evidence.config.yaml` reprend les jetons Graphite & Ardoise de `custom.scss`
(couleurs d'interface + palette graphique). Vérifié contre le schéma actuel
d'Evidence (`evidence-dev/template`, `evidence-dev/themes`, GitHub, 2026-08).

**Limite connue** : Evidence ne documente aucun mécanisme de configuration de
police au niveau projet (`evidence.config.yaml` ne couvre que les couleurs).
IBM Plex Sans/Mono n'est donc **pas encore appliqué** ici — seule la palette
de couleurs l'est. Pour la typographie, il faudra soit surcharger le CSS via
un point d'extension à confirmer dans la doc au moment de l'implémentation
(`.evidence/customization` ne couvre aujourd'hui que le formatage des
nombres, pas les polices), soit accepter la police par défaut d'Evidence.
Ne pas deviner un mécanisme non vérifié.
