---
name: redator-tecnico
description: "Use APOS as skills analisador-repositorios e engenheiro-requisitos. Consolida analise tecnica e requisitos em um documento corporativo em Markdown (.md) com formatacao profissional, capa executiva, tabelas e estrutura comercial pronta para gestores. ESSENCIAL para geracao do relatorio final de documentacao de sistemas. O documento e salvo EXCLUSIVAMENTE na pasta de destino externa informada pelo usuario."
---

# Skill-TechWriter-Doc — Redator Tecnico & Comercial

## Responsabilidade
Consolidar a analise tecnica (Skill-Analyzer) e os requisitos (Skill-Requirements-Engine) em um documento corporativo unico, elegante e profissional, formatado em Markdown (.md).

## Isolamento da Documentacao
Toda e qualquer escrita deve ser feita exclusivamente dentro do arquivo de documentacao gerado na pasta de destino separada informada pelo usuario. Nada e escrito no repositorio original.

## Template Padrao do Documento

O arquivo final DEVE seguir **rigorosamente** a estrutura abaixo:

### Capa / Cabecalho Executivo

```
---
Sistema: [NOME_DO_SISTEMA]
Tipo: [Backend | Frontend | Full Stack]
Data de Geracao: [DD/MM/AAAA]
Versao do Documento: 1.0
Equipe Responsavel: Time de Arquitetura / Documentacao
Gerado por: Orquestrador de Documentacao OpenCode (Skill-TechWriter-Doc)
Modo de Analise: Strictly Read-Only (nenhum arquivo original foi alterado)
---
```

### Secao 1 — Visao Geral e Arquitetura

- Resumo executivo da solucao (2-3 paragrafos).
- Stack de tecnologias detectadas (linguagens, frameworks, bibliotecas).
- Banco de dados utilizado.
- Padrao arquitetural (MVC, Clean Architecture, Microsservicos, Monolito).
- Diagrama textual simplificado da arquitetura.

### Secao 2 — Requisitos Funcionais (RFs)

Tabela completa consolidada:

| ID | Nome do Requisito | Descricao Detalhada | Modulo | Atores |
|---|---|---|---|---|
| RF001 | ... | ... | ... | ... |

### Secao 3 — Requisitos Nao Funcionais (RNFs)

Tabela completa consolidada:

| ID | Categoria | Descricao do RNF | Como Atendido |
|---|---|---|---|
| RNF001 | Seguranca | ... | ... |

### Secao 4 — Mapeamento de Endpoints / Interfaces

**Se Backend:**

| Metodo | Endpoint | Descricao | Autenticacao |
|---|---|---|---|
| GET | /api/viaturas | Listar todas as viaturas | JWT Obrigatorio |
| POST | /api/viaturas | Cadastrar nova viatura | JWT + Admin |

**Se Frontend:**

| Rota | Componente | Descricao | Tela | Requer Auth |
|---|---|---|---|---|
| /login | LoginPage | Tela de autenticacao | Login | Nao |
| /dashboard | DashboardPage | Painel principal com graficos | Dashboard | Sim |

### Secao 5 — Consideracoes de Manutencao e Proximos Passos

- Pontos de atencao tecnica para a equipe de desenvolvimento.
- Sugestoes de melhoria continua.
- Next steps recomendados (testes, deploy, documentacao de API com Swagger).
- Notas para supervisores e gestores sobre riscos e oportunidades.

## Regras de Formatacao

- Formato: **Markdown (.md)** — salvamento obrigatorio.
- Tom: **corporativo, profissional, elegante e objetivo**.
- Use tabelas alinhadas com pipes (`|`) para dados estruturados.
- Use blocos de destaque com `>` para citacoes importantes.
- Use divisores horizontais (`---`) entre secoes maiores.
- Nao use emojis.
- Linguagem formal, em portugues (ou ingles se o projeto exigir).
- O documento deve ser **auto-contido**: qualquer pessoa (dev, supervisor, gestor) deve entende-lo sem precisar de contexto externo.

## Aviso Final
Nao crie o documento se os dados da analise e dos requisitos ainda nao foram fornecidos. Esta skill e o **ultimo estagio do pipeline** e so deve ser ativada apos a analise completa.

Salve o arquivo na pasta destino informada pelo usuario, com o nome: `Documentacao_[NOME_DO_SISTEMA]_v1.0.md`.
