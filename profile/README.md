# Hub Escola

Ecossistema de recrutamento e triagem de candidatos para escolas do DF.

## Repositórios

| Repo | O que é | Stack |
|---|---|---|
| **operacao-back** | Backend e serviços - core-ia, worker-email, portal-api, normalizer, message-buffer | Node.js · PostgreSQL · Redis · RabbitMQ |
| **operacao** | Painel de operação - gestão de candidatos, vagas e triagens | Next.js |
| **portal-escola** | Portal da escola - vagas, candidatos e faturas ([escola.genteescola.com.br](https://escola.genteescola.com.br)) | TypeScript |
| **site** | Portal público de vagas - [genteescola.com.br](https://genteescola.com.br) | TypeScript |
| **app** | Portal público de vagas - [app.genteescola.com.br](https://app.genteescola.com.br) | TypeScript |
| **mapa-hub** | Mapa do Hub: o projeto inteiro numa página | - |
| **cto-hub** | CTO de IA: conversa com tetos de gasto, custos e análise de código somente leitura | - |
| **evonexus-brain** | Automação, agentes de IA e infraestrutura interna | Python |

## Arquitetura

Candidato → [WhatsApp · Gmail · Portal] → Normalizer → Core IA → Triagem
                                                                     ↓
                                              Painel de Operação ← Banco

Escolas acompanham vagas, candidatos e faturas pelo **portal-escola**.

## Infra

- **VPS** com Docker + Traefik (SSL) + Portainer
- **CI/CD**: GitHub Actions builda imagens → GHCR → redeploy manual no Portainer
