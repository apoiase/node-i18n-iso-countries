# PRC — Observability (node-i18n-iso-countries)

Repo sem runtime próprio — é consumido como dependência de código por outros
serviços. Não há logs, métricas ou alertas a validar aqui; observabilidade
relevante fica no serviço consumidor.

## Checklist

- [x] N/a — sem deploy, sem serviço próprio a observar
- [ ] OBS1: `.travis.yml` legado não gera alerta de falha de CI — mas também
  não roda de fato hoje (PRC-GH1), então não há sinal a perder
