<p align="center">
  <a href="https://alopex-db.github.io/alopex-ui-pages/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/alopex-db/alopex-db.github.io/main/docs/assets/images/brand/submark-dataui-dark-192.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/alopex-db/alopex-db.github.io/main/docs/assets/images/brand/submark-dataui-192.png">
      <img alt="Alopex Data UI" src="https://raw.githubusercontent.com/alopex-db/alopex-db.github.io/main/docs/assets/images/brand/submark-dataui-192.png" width="112">
    </picture>
  </a>
</p>

<h1 align="center">Alopex Data UI</h1>

<h3 align="center">One interface, wherever the data moves.</h3>

<p align="center">
  <b>A consistent UI model for data applications.</b><br>
  Forms, grids, charts, graphs, and maps evolve as one system, because they all
  speak to a single DataSource contract instead of to your backend.
</p>

<p align="center">
  <a href="https://alopex-db.github.io/alopex-ui-pages/">Site</a> &bull;
  <a href="https://alopex-db.github.io/alopex-ui-pages/ja/">日本語</a> &bull;
  <a href="#the-model">The model</a> &bull;
  <a href="#components">Components</a> &bull;
  <a href="https://github.com/alopex-db/alopex">Alopex DB</a> &bull;
  <a href="https://github.com/sponsors/asopitech">Sponsor</a>
</p>

<p align="center">
  <img alt="Status" src="https://img.shields.io/badge/status-early%20development-orange">
  <img alt="Packages" src="https://img.shields.io/badge/packages-%40alopex--data--ui%2F*-5FB4C9">
  <a href="https://github.com/sponsors/asopitech"><img alt="Sponsor" src="https://img.shields.io/badge/sponsor-%E2%9D%A4-db61a2"></a>
  <a href="https://github.com/alopex-db/alopex-ui/stargazers"><img alt="Stars" src="https://img.shields.io/github/stars/alopex-db/alopex-ui?style=flat&color=7EC8E3"></a>
</p>

> **Early development.** The concept and component model are published; the
> packages are not released yet. This describes product direction, not fixed
> delivery dates. Watch or star the repository to see the first release.

---

## The problem

Backend choices should not reshape the product experience. When queries,
schema conversion, filters, and selection state are wired directly to a
backend, infrastructure decisions leak into the interface — and swapping a
database, a grid engine, or a chart library turns into an application rewrite.

Alopex Data UI keeps that complexity at the boundary.

## The model

**Different backends. One way of building.**

Adapters translate schema, queries, filters, selections, and editable records
into one **DataSource contract**. Components work against that contract, and
backend-specific behavior stays behind the boundary.

```
Backends (Alopex DB / DuckDB / API / file / service)
        │
        ▼  adapters
┌──────────────────────────────┐
│      DataSource contract     │   ← the stable boundary
└──────────────────────────────┘
        │
        ▼  one consistent interaction model
Forms · Grids · Charts · Graphs · Maps · Exploration
```

Whether data arrives from Alopex DB, DuckDB, an API, a file, or an internal
service, the component tree keeps the same shape. Only the boundary knows how
the data is reached.

**Proven UI engines, a stable data boundary.** Rendering, controls,
virtualization, charts, maps, graph layouts, and editors stay with mature
libraries. Alopex Data UI does not replace your database or your UI
libraries — it keeps them replaceable, behind shared application contracts.

## Components

| Component | What it does |
| --- | --- |
| **Filters** | Build typed conditions from schema information and pass the same filter to every connected view |
| **Grid** | Connect a DataSource to virtualized grid engines through one consistent grid contract |
| **Forms** | Generate editable forms from schema, and keep validation and update flows consistent |
| **Charts** | Map dimensions, measures, filters, and selections to the chart engine you choose |
| **Pivot** | Explore grouping, aggregation, and pivot analysis without coupling the UI to a database |
| **Graph** | Visualize large relationship datasets with GPU-accelerated graph engines |
| **Maps** | Connect geographic data to MapLibre GL and deck.gl through the shared source model |
| **Workspace** | Combine filters, grids, charts, schema inspection, and record detail in one reusable surface |

## Use cases

- **Data exploration** — search, filter, compare, and visualize large datasets
- **Operational surfaces** — forms, live lists, charts, and status views in one place
- **Knowledge graphs** — explore connected data at scale
- **Database tooling** — inspect schemas and query results, then edit records without changing UI conventions

## Principles

- Keep backend-specific behavior behind the DataSource boundary
- Change grid or chart engines without rewriting application state
- Let schema information drive forms, filters, columns, and formats
- Use virtualization, Canvas, WebGL, and GPU engines where each performs best

## Repositories

| Repository | What it holds |
|:--|:--|
| **alopex-ui** | This repo — the component model and packages (`@alopex-data-ui/*`) |
| [**alopex-ui-pages**](https://github.com/alopex-db/alopex-ui-pages) | The bilingual product site published at [alopex-db.github.io/alopex-ui-pages](https://alopex-db.github.io/alopex-ui-pages/) |

## The Alopex family

| Project | What it is |
|:--|:--|
| [**alopex**](https://github.com/alopex-db/alopex) | The unified engine — SQL + vector (HNSW) + columnar, embedded to cluster |
| [**alopex-skulk**](https://github.com/alopex-db/alopex-skulk) | Time-series storage, ingest, and embedded PromQL / SQL-TS |
| [**alopex-chirps**](https://github.com/alopex-db/alopex-chirps) | Gossip and messaging mesh over UDP/QUIC |
| **alopex-ui** | This repo |

Documentation for the family: <https://alopex-db.github.io>.

## Contributing

The component model is still taking shape, which is the best time to argue
with it. Open an issue with the data application you are trying to build and
where the contract does not fit. The organization
[contributing guide](https://github.com/alopex-db/.github/blob/main/CONTRIBUTING.md)
covers the rest.

## Sponsor

Alopex Data UI is built in the open by
[@asopitech](https://github.com/asopitech). GitHub Sponsors funds continued
development across the Alopex family, and higher tiers follow the work before
it is public — $3/month OSS Support, $12/month Early Access, $99/month
Enterprise-focused Early Access.

<p align="center">
  <a href="https://github.com/sponsors/asopitech?metadata_source=alopex_ui_readme&metadata_campaign=sponsor_early_access&metadata_content=readme_sponsor_section"><img alt="Sponsor @asopitech on GitHub Sponsors" src="https://img.shields.io/badge/GitHub%20Sponsors-%E2%9D%A4%20Sponsor%20%40asopitech-db61a2?logo=githubsponsors&logoColor=white&style=for-the-badge"></a>
  <a href="https://buymeacoffee.com/asopitechia"><img alt="Buy Me a Coffee" src="https://img.shields.io/badge/Buy%20Me%20a%20Coffee-%E2%98%95-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black"></a>
</p>
