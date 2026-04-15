# Virtual Squad Copilot - Guia de Agents e Workflows

Este repositório pessoal organiza uma squad virtual para apoiar atuacao de Principal Engineer em temas de alta complexidade: arquitetura, resiliencia, performance, qualidade de codigo, observabilidade, seguranca e qualidade de testes.

## Estrutura

```text
~/.copilot/
├── agents/
│   ├── po-spec.agent.md
│   ├── squad-lead.agent.md
│   ├── go-performance.agent.md
│   ├── go-reviewer.agent.md
│   ├── observability-expert.agent.md
│   ├── reliability-engineer.agent.md
│   ├── go-qa.agent.md
│   ├── go-architect.agent.md
│   ├── security-reviewer.agent.md
│   ├── tech-writer.agent.md
│   └── incident-analyzer.agent.md
└── skills/
    └── go-coverage/
        └── SKILL.md
```

## Objetivo da Squad

- Transformar ideias vagas em especificacoes tecnicas acionaveis
- Quebrar problemas grandes em backlog sequencial e delegavel
- Apoiar revisoes profundas de arquitetura, performance, resiliencia e qualidade
- Fornecer analise tecnica padronizada para escalar atuacao entre multiplos times

## Catalogo de Agents

### 1) PO - Technical Spec
Arquivo: `agents/po-spec.agent.md`

Quando usar:
- Ideia vaga ainda sem escopo tecnico
- Necessidade de user stories, criterios de aceite e requisitos NFR
- Necessidade de transformar demanda executiva em especificacao implementavel

Entrega principal:
- Contexto, escopo, requisitos funcionais e nao funcionais
- Contratos de interface/dados
- DoR, DoD e questoes em aberto

---

### 2) Squad Lead
Arquivo: `agents/squad-lead.agent.md`

Quando usar:
- Precisa converter spec em backlog tecnico sequenciado
- Precisa orquestrar especialistas para um tema complexo
- Precisa montar plano de execucao com dependencias e risco

Entrega principal:
- Backlog por fases
- Caminho critico
- Tarefas paralelizaveis
- Riscos, premissas e fora de escopo

---

### 3) Go Performance Engineer
Arquivo: `agents/go-performance.agent.md`

Quando usar:
- Latencia alta, throughput baixo ou custo elevado de CPU/memoria
- Duvida sobre algoritmo, concorrencia e alocacoes
- Necessidade de tunning focado em Go runtime

Entrega principal:
- Findings por severidade
- Analise de complexidade, alocacao e concorrencia
- Recomendacoes com estrategia de validacao (benchmark/profile)

---

### 4) Go Code Reviewer
Arquivo: `agents/go-reviewer.agent.md`

Quando usar:
- Revisao de PRs e modulos Go
- Aumento de manutenabilidade e padronizacao
- Verificacao de boas praticas idiomaticas em Go

Entrega principal:
- Must Fix / Should Fix / Consider
- Sugestoes de refactor e melhoria de design
- Revisao de tratamento de erros, interfaces e coesao

---

### 5) Observability Expert
Arquivo: `agents/observability-expert.agent.md`

Quando usar:
- Falta visibilidade operacional
- Dificuldade de diagnostico em incidentes
- Necessidade de padronizar logs/metricas/traces

Entrega principal:
- Avaliacao de qualidade de logs estruturados
- Avaliacao de metricas Prometheus (naming, labels, cardinalidade)
- Recomendacao de SLIs/SLOs e gaps de instrumentacao

---

### 6) Reliability Engineer
Arquivo: `agents/reliability-engineer.agent.md`

Quando usar:
- Fluxos com risco de cascata, timeout e indisponibilidade
- Necessidade de hardening de resiliencia
- Revisao de retry, circuit breaker, bulkhead e degradacao graciosa

Entrega principal:
- Matriz de falha por dependencia
- Riscos criticos de propagacao de falha
- Recomendacoes de resiliencia por prioridade

---

### 7) Go QA Specialist
Arquivo: `agents/go-qa.agent.md`

Quando usar:
- Cobertura baixa ou pouco confiavel
- Necessidade de testes de qualidade (unit, integration, fuzz, bench)
- Planejamento de cobertura por risco de negocio

Entrega principal:
- Mapa de lacunas de teste
- Plano de testes por prioridade
- Skeletons de testes table-driven e estrategias de race/fuzz

---

### 8) Go Solutions Architect
Arquivo: `agents/go-architect.agent.md`

Quando usar:
- Decisoes arquiteturais com trade-offs relevantes
- Analise de fronteiras de servico e consistencia de dados
- Definicao de padroes (saga, outbox, CQRS, etc.)

Entrega principal:
- Revisao arquitetural
- Recomendacoes de evolucao
- Estrutura de ADR com opcoes e consequencias

---

### 9) Security Reviewer
Arquivo: `agents/security-reviewer.agent.md`

Quando usar:
- Revisao de risco OWASP em servicos Go
- Validacao de authn/authz, injecao, segredo e criptografia
- Revisao de dependencias e supply chain

Entrega principal:
- Vulnerabilidades por severidade
- Vetor de ataque e impacto
- Correcao recomendada e prioridade

---

### 10) Technical Writer
Arquivo: `agents/tech-writer.agent.md`

Quando usar:
- Necessidade de runbook, postmortem, README tecnico e ADRs
- Documentacao para operacao e onboarding

Entrega principal:
- Documentacao tecnica objetiva e acionavel
- Estruturas padronizadas para operacao e comunicacao

---

### 11) Incident Analyzer
Arquivo: `agents/incident-analyzer.agent.md`

Quando usar:
- Analise de incidente de producao
- RCA e 5 Whys
- Definicao de acoes corretivas/preventivas

Entrega principal:
- Timeline estruturada
- Causa imediata, fatores contribuintes e causa raiz
- Action items com owner, prazo e prioridade

## Skill Disponivel

### go-coverage
Arquivo: `skills/go-coverage/SKILL.md`

Quando usar:
- Executar cobertura em Go
- Gerar relatorios e identificar funcoes sem cobertura
- Rodar race detector, fuzz e benchmark com criterios de qualidade

Entrega principal:
- Procedimento operacional para medir coverage
- Comandos padrao para analise de gaps
- Thresholds recomendados por tipo de pacote

## Workflows Recomendados

### Workflow A - Da ideia ao backlog tecnico

Objetivo: transformar uma demanda vaga em plano executavel.

Passos:
1. PO - Technical Spec: formalizar requisitos, escopo e criterios de aceite.
2. Go Solutions Architect: validar trade-offs e riscos de arquitetura.
3. Squad Lead: decompor em fases, tarefas e dependencias.
4. Technical Writer: consolidar artefato final (spec + backlog + ADRs).

Saida esperada:
- Spec tecnica consistente
- Backlog sequenciado
- Decisoes arquiteturais rastreaveis

---

### Workflow B - Hardening de resiliencia de servico critico

Objetivo: reduzir risco de indisponibilidade e falhas em cascata.

Passos:
1. Reliability Engineer: mapear riscos em timeout/retry/circuit breaker/bulkhead.
2. Observability Expert: fechar gaps de sinais para detectar degradacao cedo.
3. Go Performance Engineer: validar impacto de protecoes em latencia e throughput.
4. Squad Lead: priorizar backlog de hardening por risco e esforco.

Saida esperada:
- Matriz de riscos por dependencia
- Plano de mitigacao priorizado
- Telemetria minima para operacao segura

---

### Workflow C - Performance tuning orientado a evidencias

Objetivo: melhorar latencia e custo sem regressao funcional.

Passos:
1. Go Performance Engineer: identificar hotspots e hipoteses de ganho.
2. Go QA Specialist: preparar testes de regressao e benchmarks de controle.
3. Go Code Reviewer: revisar implementacao otimizada (qualidade e clareza).
4. Observability Expert: garantir metricas para validar resultado em producao.

Saida esperada:
- Melhorias com comprovacao (bench/profile)
- Risco de regressao reduzido
- Guardrails observaveis em runtime

---

### Workflow D - Revisao completa pre-merge para tema critico

Objetivo: elevar confiabilidade de mudancas de alto impacto.

Passos:
1. Go Code Reviewer: revisar estilo, design, erros e manutenabilidade.
2. Security Reviewer: revisar vulnerabilidades e configuracoes inseguras.
3. Reliability Engineer: revisar modos de falha e estrategias de recuperacao.
4. Go QA Specialist + go-coverage: validar cobertura e qualidade dos testes.
5. Squad Lead: consolidar decisao go/no-go com criterios objetivos.

Saida esperada:
- Parecer tecnico multiangulo
- Lista de bloqueios e nao bloqueios
- Recomendacao final de merge

---

### Workflow E - Pos-incidente ate acao preventiva

Objetivo: converter incidente em melhoria sistemica.

Passos:
1. Incident Analyzer: construir timeline, 5 Whys e causa raiz.
2. Reliability Engineer: projetar controles de prevencao e degradacao.
3. Observability Expert: corrigir lacunas de deteccao e alerta.
4. Squad Lead: transformar em backlog com dono e prazo.
5. Technical Writer: publicar postmortem e atualizar runbook.

Saida esperada:
- RCA sem culpabilizacao
- Acoes preventivas executaveis
- Aprendizado institucionalizado

## Modo de Uso Sugerido no Dia a Dia

- Use o Squad Lead como ponto de entrada para temas complexos multi-disciplinares.
- Use agentes especialistas para aprofundamento tecnico dirigido.
- Ao final de cada fluxo, consolide resultado em backlog objetivo (owner, prazo, criterio de aceite).

Exemplos de prompts:
- "Squad Lead: transformar esta spec em backlog por fases com caminho critico e riscos"
- "Go Performance Engineer: revise este handler para reduzir alocacoes e latencia p99"
- "Reliability Engineer: audite retries e timeouts neste fluxo de pagamento"
- "Observability Expert: proponha metricas Prometheus e SLIs para este endpoint"
- "Go QA Specialist: monte plano de testes para cobrir branches de erro"

## Boas Praticas de Governanca

- Definir um template unico de severidade para todos os pareceres (Critical/High/Medium/Low).
- Exigir sempre recomendacao validavel (benchmark, metrica, teste, evidencias).
- Rastrear decisoes arquiteturais via ADR para evitar retrabalho e incoerencia entre times.
- Padronizar backlog com dependencia explicita e criterio de pronto (DoR/DoD).

## Evolucao Recomendada

- Criar agentes complementares por dominio (ex.: dados, plataforma, custo cloud).
- Incluir prompts padrao para cenarios recorrentes de review.
- Integrar os resultados de analise em rituais dos times (planning, design review, postmortem review).
