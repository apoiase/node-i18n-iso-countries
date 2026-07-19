# CLAUDE.md

Guidance for Claude Code (claude.ai/code) neste repositório.

## Descrição

`node-i18n-iso-countries` é um **fork** da lib npm `i18n-iso-countries`
(upstream `michaelwittig/node-i18n-iso-countries`, remote `upstream`
configurado). Converte códigos ISO 3166-1 (alpha-2, alpha-3, numeric) e
resolve nomes de país em 46 idiomas (ISO 639-1). Sem dependências de
runtime — `devDependencies` só cobrem lint/test/coverage.

## Comandos

```bash
npm install          # devDependencies (mocha, jshint, madge, istanbul, npmedge)
npm test              # = make test → jshint + madge --circular + mocha
make coverage         # istanbul cover
make outdated         # npmedge (dependências desatualizadas)
```

## Arquitetura

- **Núcleo** (`index.js`, entry point `browser`): carrega `codes.json`
  (~249 territórios, tabela alpha-2/alpha-3/numeric/ISO-3166-2), monta os
  mapas de conversão e expõe `registerLocale`/`toAlpha2`/`toAlpha3`/
  `getName`/`getNames`/`isValid` etc. Não registra idioma nenhum por padrão.
- **Entry point Node** (`entry-node.js`, `main` do package.json): importa
  `index.js` e pré-registra automaticamente os 46 locales de `langs/*.json`
  via `registerLocale` — é o que o `require("i18n-iso-countries")` do lado
  servidor usa.
- **Dados de locale** (`langs/*.json`, 46 arquivos): um JSON por idioma,
  schema `{locale, countries: {AA: "Nome"}}`. Em ambiente browser, o
  consumidor registra só os idiomas que precisa (ver README).
- **Typings** (`index.d.ts`): assinaturas TypeScript espelhando `index.js`.
- **Build/test**: `Makefile` encadeia jshint → madge (dependência circular)
  → mocha (`test/iso-i18n-countries.js`); `.travis.yml` é CI legado (Node
  4-8) sem integração ativa na org GitHub hoje.

## Contexto de domínio

Sem termos de negócio da Apoia.se — é uma lib de dados ISO genérica,
provável dependência de fluxos que precisam de nome/código de país
(cadastro, KYC, endereço). Referência completa: apoiase-context-layer (ler
sob demanda se for mapear quem consome este fork).

## Convenções

- Fork — mudanças de comportamento upstream devem considerar rebase vs.
  patch local; remote `upstream` já configurado.
- Commits do rollout NA-598 em português natural, com `NA-598` no texto.
- Branch do rollout: `big-picture/NA-598-node-i18n-iso-countries`.
- PR só via review humano — nunca merge por API.

## Knowledge graph

- `graphify-out/graph.html` (interativo) · `GRAPH_REPORT.md` (auditoria)
- `.understand-anything/knowledge-graph.json` (layers, tour) — query via
  `/understand-chat`
- Nota: a extração AST bruta produz edges "dangling" (para `codes.json` e os
  46 `langs/*.json`, sem nós próprios — são dados puros, sem função/classe a
  extrair) e ~59 edges espúrias tipo `extends` a partir do array
  `keywords` do `package.json` (quirk do parser AST em arrays JSON). Ambos
  são descartados no build e não aparecem em `graphify-out/graph.json`.
