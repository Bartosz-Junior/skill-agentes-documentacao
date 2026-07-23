---
name: analisador-repositorios
description: "Use para analisar repositorios de codigo-fonte (Backend, Frontend ou Full Stack) em modo estritamente read-only. Varre recursivamente a estrutura de pastas, identifica stack tecnologica, descobre rotas de API / Controllers, modelos de dados, middlewares, regras de negocio e estrutura de diretorios. ESSENCIAL para qualquer skill ou fluxo que precise de analise aprofundada de projetos de software antes de gerar documentacao ou requisitos. PROIBIDO modificar qualquer arquivo no repositorio analisado."
---

# Skill-Analyzer — Analisador Passivo de Repositorios

## Regra de Ouro: Strictly Read-Only

**PROIBICAO ABSOLUTA DE ALTERACOES.** Sob nenhuma hipotese esta skill pode editar, sobrescrever, mover, criar ou deletar qualquer arquivo ou pasta dentro do repositorio analisado.

O projeto de origem deve ser tratado como uma base de dados de apenas leitura (Read-Only). Toda saida deve ser gerada exclusivamente na pasta de destino separada informada pelo usuario.

## Responsabilidade
Varrer recursivamente o diretorio informado (apenas leitura) e extrair metadados tecnicos do projeto.

## Procedimento Obrigatorio

Sempre que esta skill for ativada, realize os passos abaixo de forma **sistematica e documentada**:

### 1. Identificacao da Stack Tecnologica
- Examine `package.json`, `requirements.txt`, `Pipfile`, `pyproject.toml`, `cargo.toml`, `go.mod`, `composer.json`, `Gemfile`, `build.gradle`, `pom.xml` e similares (apenas leitura).
- Framework principal (Django, React, Angular, Vue, Next.js, Express, FastAPI, Spring Boot etc.)
- Banco de dados (PostgreSQL, MySQL, MongoDB, SQLite, Redis etc.)
- ORM / ODMs (Prisma, TypeORM, Sequelize, SQLAlchemy, Mongoose, Entity Framework)
- Bibliotecas auxiliares relevantes (JWT, Swagger, Celery, Socket.IO, Axios etc.)

### 2. Mapeamento de Rotas / Controllers (Backend)
- Procure por arquivos de definicao de rotas: `routes/`, `controllers/`, `views/`, `api/`, `urls.py`, `router.*`, `handlers/`, `endpoints/`.
- Liste: **Verbo HTTP**, **Endpoint**, **Descricao curta**, **Middleware de autenticacao**.
- Detecte Blueprints, Routers, ou grupos de rotas por modulo.

### 3. Estrutura de Telas e Componentes (Frontend)
- Identifique frameworks de UI (React, Angular, Vue, Svelte).
- Mapeie: **Rota/Path**, **Componente Principal**, **Descricao da Tela**, **Autenticacao requerida**.
- Gerencie estado (Redux, Zustand, Pinia, NgRx, Context API).
- Bibliotecas de componentes (Material UI, Ant Design, PrimeNG, Tailwind, Bootstrap).

### 4. Modelos de Banco de Dados
- Encontre schemas, migrations, models, entities.
- Extraia: **Nome da entidade**, **Campos principais**, **Relacionamentos**, **Indices**.

### 5. Regras de Negocio e Middlewares
- Identifique middlewares (auth, logging, rate-limit, error-handling).
- Detecte regras de negocio em services, use-cases, helpers, handlers.

### 6. Estrutura de Pastas
- Gere uma arvore simplificada da estrutura de diretorios do projeto.
- Destaque modulos funcionais, shared, core, features.

## Formato de Saida (para uso interno do Orquestrador)
Sua saida deve ser estruturada em secoes Markdown, cada uma com uma tabela ou lista, pronta para consumo pela Skill-Requirements-Engine e pela Skill-TechWriter-Doc.

NAO gere o documento final — esta skill e APENAS para coleta e analise tecnica.
Passe o resultado estruturado adiante no pipeline.
