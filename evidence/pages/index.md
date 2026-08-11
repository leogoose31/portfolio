---
title: Contoso Retail — Pilotage de marge
---

Squelette de démarrage. Le dashboard restitue les marts dbt décrits dans
`projects/contoso-marges/index.qmd` du portfolio (`mart_ventes`, `mart_couts`,
`mart_pnl`) — à connecter dans `sources/` une fois le pipeline dbt disponible
en local ou via DuckDB.

```sql marge_par_canal
select * from mart_pnl
```

<BarChart
    data={marge_par_canal}
    x=canal
    y=marge_nette
    title="Marge nette par canal"
/>
