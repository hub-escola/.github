 # Hub Escola

  Ecossistema de recrutamento e triagem de candidatos para escolas do DF.

  ## Repositórios

  | Repo | O que é | Stack |
  |---|---|---|
  | **HubEscolas** | Backend e serviços - core-ia, worker-email, portal-api, normalizer, message-buffer | Node.js · PostgreSQL · Redis · RabbitMQ |
  | **opercao-hubescola** | Painel de operação - gestão de candidatos, vagas e triagens | Next.js |
  | **app.genteescola** | App mobile para candidatos | TypeScript |
  | **gente-escola** | Portal público de vagas - [genteescola.com.br](https://genteescola.com.br) | TypeScript |
  | **evonexus-brain** | Automação, agentes de IA e infraestrutura interna | Python |

  ## Arquitetura

  Candidato → [WhatsApp · Gmail · Portal] → Normalizer → Core IA → Triagem
                                                                       ↓
                                                Painel de Operação ← Banco

  ## Infra

  - **VPS** com Docker + Traefik (SSL) + Portainer
  - **CI/CD**: GitHub Actions builda imagens → GHCR → redeploy manual no Portainer

