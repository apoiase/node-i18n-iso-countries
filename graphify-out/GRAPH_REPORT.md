# Graph Report - .  (2026-07-18)

## Corpus Check
- Corpus is ~36,330 words - fits in a single context window. You may not need a graph.

## Summary
- 58 nodes · 67 edges · 12 communities (7 shown, 5 thin omitted)
- Extraction: 99% EXTRACTED · 1% INFERRED · 0% AMBIGUOUS · INFERRED: 1 edges (avg confidence: 0.95)
- Token cost: 1,850 input · 0 output

## Community Hubs (Navigation)
- API Pública e Entry Point
- Metadados do Pacote npm
- Dependências de Desenvolvimento
- Conversão para Alpha-2
- Conversão para Alpha-3
- Typings TypeScript
- Autoria do Pacote
- Repositório Upstream
- Pipeline de Teste (Make + Travis)
- Registro de Locale
- Issues Upstream
- Engine Node Suportada

## God Nodes (most connected - your core abstractions)
1. `numericToAlpha3()` - 4 edges
2. `toAlpha3()` - 4 edges
3. `toAlpha2()` - 4 edges
4. `formatNumericCode()` - 3 edges
5. `alpha3ToAlpha2()` - 3 edges
6. `alpha2ToAlpha3()` - 3 edges
7. `numericToAlpha2()` - 3 edges
8. `getAlpha3Code()` - 3 edges
9. `author` - 3 edges
10. `repository` - 3 edges

## Surprising Connections (you probably didn't know these)
- `Padrão de registro de locale sob demanda (registerLocale)` --conceptually_related_to--> `registerLocale()`  [INFERRED]
  README.md → index.js
- `Matriz de CI legado Travis (Node 4-8)` --references--> `test`  [EXTRACTED]
  .travis.yml → package.json

## Import Cycles
- None detected.

## Communities (12 total, 5 thin omitted)

### Community 1 - "Metadados do Pacote npm"
Cohesion: 0.18
Nodes (10): browser, contributors, dependencies, description, keywords, license, main, name (+2 more)

### Community 2 - "Dependências de Desenvolvimento"
Cohesion: 0.29
Nodes (7): devDependencies, assert-plus, istanbul, jshint, madge, mocha, npmedge

### Community 3 - "Conversão para Alpha-2"
Cohesion: 0.33
Nodes (6): alpha3ToAlpha2(), alpha3ToNumeric(), formatNumericCode(), getName(), numericToAlpha2(), toAlpha2()

### Community 4 - "Conversão para Alpha-3"
Cohesion: 0.50
Nodes (5): alpha2ToAlpha3(), getAlpha2Code(), getAlpha3Code(), numericToAlpha3(), toAlpha3()

### Community 6 - "Autoria do Pacote"
Cohesion: 0.67
Nodes (3): author, email, name

### Community 7 - "Repositório Upstream"
Cohesion: 0.67
Nodes (3): repository, type, url

### Community 8 - "Pipeline de Teste (Make + Travis)"
Cohesion: 0.67
Nodes (3): scripts, test, Matriz de CI legado Travis (Node 4-8)

## Knowledge Gaps
- **25 isolated node(s):** `LocalizedCountryNames`, `LocaleData`, `name`, `version`, `description` (+20 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **5 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `devDependencies` connect `Dependências de Desenvolvimento` to `Metadados do Pacote npm`?**
  _High betweenness centrality (0.100) - this node is a cross-community bridge._
- **Why does `author` connect `Autoria do Pacote` to `Metadados do Pacote npm`?**
  _High betweenness centrality (0.036) - this node is a cross-community bridge._
- **Why does `repository` connect `Repositório Upstream` to `Metadados do Pacote npm`?**
  _High betweenness centrality (0.036) - this node is a cross-community bridge._
- **What connects `LocalizedCountryNames`, `LocaleData`, `name` to the rest of the system?**
  _26 weakly-connected nodes found - possible documentation gaps or missing edges._