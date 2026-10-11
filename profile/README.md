 # Hub Escola

  Ecossistema de recrutamento e triagem de candidatos para escolas do DF.

  ## Repositórios

  | Repo | O que é | Stack |
  |---|---|---|
  | **operacao-back** | Backend e serviços - core-ia, worker-email, portal-api, normalizer, message-buffer | Node.js · PostgreSQL · Redis · RabbitMQ |
  | **operacao** | Painel de operação - gestão de candidatos, vagas e triagens | Next.js |
  | **app** | App mobile para candidatos | TypeScript |
  | **site** | Portal público de vagas - [genteescola.com.br](https://genteescola.com.br) | TypeScript |
  | **evonexus-brain** | Automação, agentes de IA e infraestrutura interna | Python |

  ## Arquitetura

  Candidato → [WhatsApp · Gmail · Portal] → Normalizer → Core IA → Triagem
                                                                       ↓
                                                Painel de Operação ← Banco

  ## Infra

  - **VPS** com Docker + Traefik (SSL) + Portainer
  - **CI/CD**: GitHub Actions builda imagens → GHCR → redeploy manual no Portainer

