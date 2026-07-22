# Alopex Data UI

> One interface, wherever the data moves.

A consistent UI model for data applications. Alopex Data UI keeps backend differences out of the interface, so forms, grids, charts, graphs, maps, and exploration tools can evolve as one coherent system.

🌐 **Site**: <https://alopex-db.github.io/alopex-ui-pages/> ([日本語](https://alopex-db.github.io/alopex-ui-pages/ja/))

## The Problem

Backend choices should not reshape the product experience. When queries, schema conversion, filters, and selection state are tied directly to a backend, infrastructure decisions spill into the product. Alopex Data UI keeps that complexity at the boundary.

## The Model

**Different backends. One way of building.**

Adapters translate schema, queries, filters, selections, and editable records into one **DataSource contract**. Components work with that contract, while backend-specific behavior stays behind the boundary.

```
Backends (AlopexDB / DuckDB / API / file / service)
        │
        ▼  adapters
┌──────────────────────────────┐
│      DataSource contract     │   ← the stable boundary
└──────────────────────────────┘
        │
        ▼  one consistent interaction model
Forms · Grids · Charts · Graphs · Maps · Exploration
```

Whether data arrives from AlopexDB, DuckDB, an API, a file, or an internal service, the component tree keeps the same shape. Only the boundary knows how the data is reached.

**Proven UI engines. A stable data boundary.** Rendering, controls, virtualization, charts, maps, graph layouts, and editors stay with mature libraries. Alopex Data UI does not replace your database or UI libraries — it keeps them replaceable through shared application contracts.

## Components

| Component | What it does |
| --- | --- |
| **Filters** | Build typed conditions from schema information and pass the same filter to every connected view |
| **Grid** | Connect a DataSource to virtualized grid engines through one consistent grid contract |
| **Forms** | Generate editable forms from schema and keep validation and update flows consistent |
| **Charts** | Map dimensions, measures, filters, and selections to the chart engine you choose |
| **Pivot** | Explore grouping, aggregation, and pivot analysis without coupling the UI to a database |
| **Graph** | Visualize large relationship datasets with GPU-accelerated graph engines |
| **Maps** | Connect geographic data to MapLibre GL and deck.gl through the shared source model |
| **Workspace** | Combine filters, grids, charts, schema inspection, and record detail in one reusable workspace |

## Use Cases

- **Data exploration** — search, filter, compare, and visualize large datasets
- **Operational surfaces** — bring forms, live lists, charts, and status views into one surface
- **Knowledge graphs** — explore connected data and knowledge graphs at scale
- **Database tooling** — inspect schemas and query results, then edit records without changing UI conventions

## Principles

- Keep backend-specific behavior behind the DataSource boundary
- Change grid or chart engines without rewriting application state
- Let schema information drive forms, filters, columns, and formats
- Use virtualization, Canvas, WebGL, and GPU engines where they perform best

## Status

Early development. The published site describes **product direction, not a promise of fixed delivery dates**.

## The Alopex Family

- [alopex](https://github.com/alopex-db/alopex) — the unified database engine (SQL + Vector + columnar)
- [alopex-skulk](https://github.com/alopex-db/alopex-skulk) — time-series database on Alopex Core
- [alopex-chirps](https://github.com/alopex-db/alopex-chirps) — gossip & messaging mesh
- [Documentation](https://alopex-db.github.io)

## Support

- ❤️ GitHub Sponsors: <https://github.com/sponsors/asopitech>
- ☕ Buy Me a Coffee: <https://buymeacoffee.com/asopitechia>
