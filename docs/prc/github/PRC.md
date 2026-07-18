# PRC — GitHub (node-i18n-iso-countries)

- Org: `apoiase`, fork mantido do upstream `michaelwittig/node-i18n-iso-countries`.
- Branch default: `master`. Branch desta task: `big-picture/NA-598-node-i18n-iso-countries`.
- Remotos: `origin` (`git@github.com:apoiase/node-i18n-iso-countries.git`) e
  `upstream` (`git@github.com:michaelwittig/node-i18n-iso-countries.git`) —
  configurado para acompanhar o projeto original.
- 341 commits no histórico (herdados do upstream + eventuais forks anteriores).

## Checklist

- [x] Gates consultivos adicionados por este combo
  (`.github/workflows/quality-gates.yml`, `continue-on-error` em todo step)
- [ ] PRC-GH1: `.travis.yml` é CI legado (Node 4-8) sem integração ativa no
  GitHub da org — a suíte só roda localmente via `make test`/`npm test`
- [ ] PRC-GH2: branch protection e reviewers não verificados nesta rodada
- [ ] PRC-GH3: sem processo definido de sincronização com `upstream`
  (rebase/merge) — decisão de negócio, não bloqueante
- [x] Gitleaks (árvore + histórico completo, 341 commits): 0 findings
