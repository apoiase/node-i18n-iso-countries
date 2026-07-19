# PRC — AWS (node-i18n-iso-countries)

Lib pura de dados/conversão ISO 3166-1 — sem `serverless.yml`, sem SDK AWS,
sem referência a recurso em código. Validado contra o inventário estático da
task NA-598 (`inventario/02-aws/`, Steampipe `sa_automation_ro`): **0
recursos** com nome `node-i18n-iso-countries`.

## Checklist

- [x] Nenhum recurso AWS órfão associado ao repo (confirmado no inventário)
- [x] Nenhuma credencial AWS em código (gitleaks 0 findings; sem
  dependencies de runtime)
- [x] N/a — repo é dependência de dados, não serviço deployável

## Observação de consumo

Não foi mapeado nesta rodada quem na frota consome este fork como
dependência (npm) — se necessário para o big-picture completo, cruzar com
`package.json`/`package-lock.json` de outros repos apoiase que declarem
`i18n-iso-countries`.
