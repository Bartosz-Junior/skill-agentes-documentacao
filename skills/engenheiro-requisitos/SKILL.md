---
name: engenheiro-requisitos
description: "Use APOS a skill analisador-repositorios. Transforma a analise tecnica do codigo em Requisitos Funcionais (RF) e Requisitos Nao Funcionais (RNF) no padrao corporativo. Mapeia regras de negocio, endpoints, modelos e middlewares para requisitos formais. Ideal para documentacao de sistemas, contratos e apresentacoes a gestores. Modo passivo: nenhum arquivo do repositorio original e alterado."
---

# Skill-Requirements-Engine — Engenheiro de Requisitos

## Responsabilidade
Receber a analise tecnica da Skill-Analyzer e transformar cada descoberta em Requisitos Funcionais (RF) e Requisitos Nao Funcionais (RNF) formais, rastreaveis e em linguagem de negocio.

Nenhum arquivo do repositorio original e lido ou alterado diretamente por esta skill. Toda a entrada vem da Skill-Analyzer.

## Procedimento Obrigatorio

### 1. Mapeamento de Requisitos Funcionais (RF)

A partir dos dados fornecidos pela Skill-Analyzer, extraia e catalogue cada funcionalidade:

| ID | Nome do Requisito | Descricao Detalhada | Modulo Relacionado | Atores | Regra de Negocio Associada |
|---|---|---|---|---|---|
| RF001 | Autenticacao JWT | Sistema deve permitir login via JWT com refresh token | Seguranca/Auth | Administrador, Usuario | Token expira em 15 min; refresh em 7 dias |
| RF002 | Gestao de Viaturas | CRUD completo de viaturas com fotos e documentos | Frota | Administrador | Apenas admin pode excluir |

**Regras de numeracao:** `RF001`, `RF002`, `RF003`... em ordem crescente.

**Fontes de extracao:**
- Endpoints de API -> RFs de integracao.
- Models/Entities -> RFs de gestao de dados (CRUD).
- Middlewares -> RFs de seguranca/controle de acesso.
- Regras em services/use-cases -> RFs de negocio.
- Telas/Componentes -> RFs de interface.

### 2. Mapeamento de Requisitos Nao Funcionais (RNF)

Classifique por categorias e descreva como o codigo atende:

| Categoria | ID | Descricao do RNF | Como e Atendido no Codigo | Evidencia |
|---|---|---|---|---|
| Seguranca | RNF001 | Tokens JWT com expiracao curta | Middleware `auth_required` verifica token a cada request | `middleware/auth.py:15` |
| Performance | RNF002 | Respostas em ate 200ms para 95% das requisicoes | Uso de Redis para cache de consultas frequentes | `services/cache.py` |
| Usabilidade | RNF003 | Interface responsiva (mobile + desktop) | Tailwind CSS com breakpoints e grid system | `styles/global.css` |
| Disponibilidade | RNF004 | Sistema disponivel 99.9% do tempo | Health check endpoint + Docker Swarm replicas | `deploy/docker-compose.yml` |
| Manutenibilidade | RNF005 | Codigo modular seguindo Clean Architecture | Separacao em camadas (domain, application, infrastructure) | Estrutura de pastas |

**Categorias obrigatorias a considerar:**
- Seguranca (autenticacao, autorizacao, criptografia, headers HTTP)
- Performance (caching, indices DB, lazy loading, compressao)
- Usabilidade (UX, responsividade, acessibilidade)
- Disponibilidade (health checks, replicacao, fallback)
- Manutenibilidade (architecture pattern, testes, lint)
- Portabilidade (Docker, cloud-agnostic, cross-platform)
- Compliance (LGPD, logs de auditoria, consentimento)

### 3. Saida para a Skill-TechWriter-Doc

Forneca os dados de RFs e RNFs em formato Markdown estruturado com tabelas, pronto para ser consolidado no documento final corporativo pela Skill-TechWriter-Doc.
