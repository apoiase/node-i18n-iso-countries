# PRC — Security (node-i18n-iso-countries)

## Checklist

- [x] SEC1: gitleaks na árvore + histórico completo (341 commits): 0 findings
- [x] SEC2: sem secret hardcoded; sem dependencies de runtime (só
  devDependencies de lint/test/coverage)
- [ ] SEC3: sem SECURITY.md — política de disclosure não definida (fork de
  lib de dados, baixo risco de exposição)
- [ ] SEC4: sem pre-commit/hooks locais de defesa
- [x] SEC5: gate consultivo deste combo cobre gitleaks/semgrep/trivy em PR
  (`.github/workflows/quality-gates.yml`)
- [ ] SEC6 (dependências): `devDependencies` desatualizadas (mocha 4.0.1,
  istanbul 0.4.5, jshint 2.9.5 — versões de 2017-2018); sem Renovate/Dependabot
  configurado neste fork; baixo risco por serem só ferramentas de dev, não
  runtime, mas vale considerar upgrade ou substituição por Vitest/Biome no
  padrão do golden path atual
