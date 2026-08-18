<div align="center">
  <img src="./assets/biomm-logo.png" alt="BIOMM S/A" width="140"/>

  # BIOMM S/A · TI

  **Automações, scripts e ferramentas internas de infraestrutura de TI**

  [![Email](https://img.shields.io/badge/email-ti%40biomm.com-blue?style=flat-square)](mailto:ti@biomm.com)
  [![Website](https://img.shields.io/badge/site-biomm.com-blue?style=flat-square)](https://biomm.com)
  [![Status](https://img.shields.io/badge/status-ativo-brightgreen?style=flat-square)]()
</div>

---

## Sobre

A **BIOMM S/A** é uma biofarmacêutica brasileira. Esta organização reúne os repositórios da equipe de **TI**, responsáveis por automação de infraestrutura, gestão de endpoints e ferramentas internas de suporte.

O conteúdo aqui é majoritariamente voltado à equipe interna. Documentação operacional completa (change management, tickets e runbooks) fica na base interna do **GLPI**.

## Stack e ferramentas

| Área | Ferramenta |
|---|---|
| Automação de endpoints | PowerShell |
| RMM / Cyber Scripting | Acronis Cyber Protect |
| ITSM / Change Management | GLPI |
| Segurança de endpoint | Antivírus/EDR, VPN corporativa |
| CI/CD (quando aplicável) | GitHub Actions |

## Estrutura dos repositórios

| Repositório | Descrição |
|---|---|
| [`rmm-scripts`](https://github.com/BIOMM-SA/rmm-scripts) | Scripts de automação executados via RMM (limpeza de sistema, relatórios, remoção de agentes, etc.) |

> Novos repositórios seguem o mesmo padrão: código versionado, `README.md` próprio explicando o propósito do script/ferramenta, e changelog quando relevante.

## Convenções

Prefixo dos nomes de repositório indica a categoria:

| Prefixo | Uso |
|---|---|
| `rmm-` | Scripts de automação via RMM |
| `app-` | Aplicações internas |
| `integ-` | Integrações entre sistemas |

Planos e rotinas de automação seguem a nomenclatura:
