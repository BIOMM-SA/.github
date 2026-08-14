# Guia de Contribuição — BIOMM S/A TI

Este documento define o padrão a ser seguido em todos os repositórios da
organização `biommsa`.

## Nomenclatura de repositórios

Todo repositório novo segue o padrão:

```
<prefixo>-<nome-descritivo>
```

kebab-case (minúsculo, separado por hífen), sem acentos, sem underscore.

| Categoria | Prefixo | Exemplo |
|---|---|---|
| Automação de infraestrutura (RMM, scripts) | `rmm-` | `rmm-scripts` |
| Aplicações web internas (dashboards, portais) | `app-` | `app-dashboard-endpoints` |
| Integrações / APIs (GLPI, Acronis, etc.) | `integ-` | `integ-glpi-acronis` |

Um repositório = um propósito. Não misturar categorias diferentes no mesmo
repositório.

## Visibilidade

Todo repositório novo nasce **privado** por padrão. Só o repositório
`biommsa` (perfil da org) é público. Nenhum outro conteúdo deve ser tornado
público sem aprovação explícita.

## Fluxo de contribuição

1. Criar uma branch a partir de `main` (ex: `feature/nome-da-mudanca`,
   `fix/nome-do-bug`)
2. Commits pequenos e descritivos, em português, no imperativo
   (ex: "Corrige loop infinito na parada do serviço dosvc")
3. Abrir Pull Request para `main`, preenchendo o template
4. Pelo menos **1 aprovação** obrigatória antes do merge
5. Squash merge, mantendo o histórico limpo

## Documentação obrigatória por repositório

Todo repositório deve ter:

- `README.md` — o que o projeto faz, como rodar/instalar, dependências
- Changelog (seção no README ou `CHANGELOG.md`) para mudanças relevantes
- Referência ao ticket de Change Management (GLPI) quando aplicável, em
  automações que afetam produção

## Padrões específicos por categoria

**Automação de infraestrutura (`rmm-`)**
- Scripts PowerShell idempotentes, seguros para reexecução
- Sem auto-elevação (`-Verb RunAs`) em scripts executados em contexto SYSTEM
- Logs em local padronizado, com política de retenção definida
- Nome do plano/rotina documentado seguindo `FUNÇÃO - Frequência - Tipo de
  Dispositivo - Grupo` (convenção interna do Acronis, não do repositório)

**Aplicações web internas (`app-`)**
- Documentar stack utilizada (framework, runtime, dependências principais)
- Variáveis sensíveis via `.env`, nunca commitadas — usar `.env.example`
- Instruções claras de build/deploy no README

**Integrações / APIs (`integ-`)**
- Documentar endpoints consumidos e autenticação utilizada (sem expor
  credenciais ou URLs internas sensíveis no código)
- Tratamento de erro e retry documentados
- Nunca commitar tokens, client secrets ou chaves de API

## Segurança

- Nunca commitar credenciais, tokens ou dados sensíveis de clientes/pacientes
- Secret scanning e push protection habilitados em todos os repositórios
- Dependabot alerts habilitado para monitorar dependências vulneráveis
- Em caso de exposição acidental de credencial, rotacionar imediatamente e
  abrir um ticket no GLPI

## Dúvidas

Contato: [ti@biomm.com](mailto:ti@biomm.com)
