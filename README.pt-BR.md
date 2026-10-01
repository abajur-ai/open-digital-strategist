[Read in English](README.md)

# Open Digital Strategist

Sistema multi-agente de estratégia de negócios para o [Claude Code](https://docs.anthropic.com/en/docs/claude-code). Digite `/strategy` seguido do seu desafio e o sistema assume a sessão, roda a análise estratégica estruturada e entrega os outputs prontos para uso profissional (DOCX, XLSX, PDF).

## O que é

Um estrategista sênior de IA apoiado em **5 bases de conhecimento estruturadas** cobrindo growth, ofertas, validação, customer discovery e a travessia do early market para o mainstream. Ele não inventa frameworks: lê as bases de conhecimento e aplica o princípio certo ao seu problema específico.

Tudo roda localmente dentro do Claude Code. Não tem servidor, não tem conta, não tem telemetria.

## Começando

**Requisitos**

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) instalado e funcionando
- Python 3.x com `python-docx`, `openpyxl` e `fpdf2` (só para geração de documentos)

**Instalação**

```bash
git clone https://github.com/abajur-ai/open-digital-strategist.git
cd open-digital-strategist
pip install python-docx openpyxl fpdf2
claude
```

**Uso**

```
/strategy Preciso construir uma oferta irresistível para meu produto B2B
```

O comando `/strategy` é reconhecido automaticamente porque o arquivo `.claude/commands/strategy.md` vive no projeto. Rode o Claude Code com este repositório como working directory.

**Instalação global**

Para o `/strategy` funcionar de qualquer diretório, copie o comando para a pasta global do Claude Code e aponte os caminhos das bases de conhecimento para onde o projeto vive na sua máquina:

```bash
cp .claude/commands/strategy.md ~/.claude/commands/strategy.md
# depois edite a cópia, trocando "knowledge-bases/" pelo caminho absoluto
# até o diretório knowledge-bases/ deste projeto
```

No Windows, a pasta global é `%USERPROFILE%\.claude\commands\`.

## Bases de conhecimento

Cada base tem três camadas: os frameworks extraídos, uma camada RAG com princípios, conceitos e exemplos aplicados, e os system prompts dos agentes especialistas.

### Ofertas e monetização

Equação de Valor, Oferta Grand Slam, modelos de dinheiro (atração, upsell, downsell, continuidade), pricing premium, tipos de garantia e naming de ofertas.

### Validação enxuta

Build-Measure-Learn, os cinco tipos de MVP (Video, Concierge, Wizard of Oz, Smoke Test, Single Feature), os dez tipos de pivot, contabilidade de inovação, métricas acionáveis versus métricas de vaidade, e os três motores de crescimento.

### Customer discovery

As três regras para fazer perguntas sobre as quais ninguém consegue mentir, separar sinal de ruído, customer slicing até pares quem-onde, identificar earlyvangelists, detectar zombie leads e planejar conversas.

### Growth systems

Growth models em camadas concêntricas, curvas de retenção e loops de hábito, acquisition loops (Growth Multiplier, K-Factor, S-Curve de canais), os quatro fits da monetização, psicologia do usuário (ELMR, Psych!, core desires), experimentação e defensibilidade.

### Travessia para o mainstream

O ciclo de adoção de tecnologia revisado e o abismo entre early adopters e maioria inicial, a estratégia D-Day de beachhead, a regra dos 100% do whole product, o market development strategy checklist, creating the competition, position statement e elevator test, distribution-oriented pricing, e forecast em staircase em vez de hockey stick.

> Os arquivos das bases de conhecimento estão escritos em português. O agente responde no idioma em que você escrever.

## Catálogo de capacidades (66 tools)

### Agentes atômicos (28)

| # | Agente | Base | Função |
|---|--------|------|--------|
| 1 | `offer-builder` | Ofertas | Construir Oferta Grand Slam completa |
| 2 | `money-model-architect` | Ofertas | Arquitetar a sequência de monetização |
| 3 | `pricing-consultant` | Ofertas | Consultoria de precificação premium |
| 4 | `downsell-agent` | Ofertas | Processo completo de downsell (7 etapas) |
| 5 | `guarantee-strategist` | Ofertas | Criar garantias (4 tipos) |
| 6 | `offer-naming` | Ofertas | Nomes magnéticos com a Fórmula MAGIC |
| 7 | `idea-validator` | Lean | Validar ideias com hipóteses de salto de fé |
| 8 | `mvp-designer` | Lean | Projetar o MVP mínimo (5 tipos) |
| 9 | `pivot-advisor` | Lean | Decidir pivotar ou perseverar (10 tipos) |
| 10 | `innovation-accountant` | Lean | Montar a contabilidade de inovação |
| 11 | `growth-engine-selector` | Lean | Identificar o motor de crescimento |
| 12 | `interview-coach` | Discovery | Treinar a formulação de perguntas |
| 13 | `conversation-analyzer` | Discovery | Separar sinal de ruído nas notas |
| 14 | `customer-segmenter` | Discovery | Customer slicing até pares quem-onde |
| 15 | `conversation-planner` | Discovery | Preparar batches de conversas |
| 16 | `signal-detector` | Discovery | Detectar earlyvangelists e zombie leads |
| 17 | `growth-strategist` | Growth | Avaliar o growth system de forma holística |
| 18 | `retention-specialist` | Growth | Diagnosticar retenção e engajamento |
| 19 | `acquisition-architect` | Growth | Otimizar acquisition loops |
| 20 | `monetization-consultant` | Growth | Definir o modelo de monetização |
| 21 | `experiment-designer` | Growth | Criar hipóteses e priorizar experimentos |
| 22 | `user-psych-analyst` | Growth | Psicologia do usuário (ELMR, Psych!) |
| 23 | `chasm-crossing-strategist` | Chasm | Diagnóstico holístico e plano D-Day |
| 24 | `target-customer-architect` | Chasm | Scenarios e market development checklist |
| 25 | `whole-product-manager` | Chasm | Whole product (regra dos 100%) e partners |
| 26 | `positioning-strategist` | Chasm | Creating the competition, position statement, elevator test |
| 27 | `chasm-distribution-architect` | Chasm | Canal high-tech e distribution-oriented pricing |
| 28 | `postchasm-transition-advisor` | Chasm | Pioneers para settlers e staircase |

### Agentes compostos (18), cruzando bases

| # | Agente | Bases | Função |
|---|--------|-------|--------|
| 29 | `product-market-fit-assessor` | Lean + Discovery + Growth | Avaliação holística de PMF |
| 30 | `go-to-market-architect` | Ofertas + Growth + Lean | Estratégia de GTM completa |
| 31 | `customer-to-offer-pipeline` | Discovery + Ofertas | De discovery a oferta |
| 32 | `full-stack-growth-auditor` | Growth + Ofertas + Lean | Auditoria de growth completa |
| 33 | `experiment-to-insight-engine` | Growth + Lean + Discovery | Experimentação end-to-end |
| 34 | `pricing-overhaul` | Ofertas + Growth | Reestruturação de pricing |
| 35 | `churn-killer` | Growth + Ofertas | Plano anti-churn multi-frente |
| 36 | `pivot-or-iterate-tribunal` | Lean + Discovery + Growth | Tribunal de pivot com 3 perspectivas |
| 37 | `offer-fatigue-refresher` | Ofertas + Growth | Renovar oferta com fadiga |
| 38 | `beachhead-discoverer` | Chasm + Discovery + Lean | Discovery, slicing, checklist e loop BML |
| 39 | `whole-product-offer-architect` | Chasm + Ofertas | Whole product como fundação da oferta |
| 40 | `chasm-experiment-designer` | Chasm + Growth + Lean | Experimentos por fase psicográfica |
| 41 | `psychographic-growth-strategist` | Chasm + Growth | Growth loops por fase psicográfica |
| 42 | `pragmatist-offer-translator` | Chasm + Ofertas + Discovery | Traduzir oferta de visionário para pragmatista |
| 43 | `stuck-in-the-chasm-diagnostic` | Chasm + Lean + Growth | Vendas flat: abismo, churn ou segmento errado |
| 44 | `bowling-pin-expansion-planner` | Chasm + Growth + Ofertas | Sequência de expansão pós-beachhead |
| 45 | `staircase-financial-planner` | Chasm + Lean + Growth | Modelo staircase e innovation accounting |
| 46 | `psychographic-positioning-translator` | Chasm + Growth + Ofertas | Positioning por grupo psicográfico |

### Tools utilitárias (20)

| # | Tool | Função |
|---|------|--------|
| 47 | `value-equation-calculator` | Calculadora da Equação de Valor (4 variáveis) |
| 48 | `growth-multiplier-calculator` | GM = 1/(1-V) com cenários |
| 49 | `k-factor-calculator` | k = i x c com projeção |
| 50 | `model-market-fit-checker` | ARPU 1 ano x clientes x fatia capturável |
| 51 | `question-grader` | Avalia perguntas contra as três regras |
| 52 | `meeting-scorer` | Classifica a reunião como sucesso ou falha |
| 53 | `earlyvangelist-scorer` | Score de earlyvangelist, 0 a 5 |
| 54 | `psych-mapper` | Mapeia psych positivo e negativo por etapa |
| 55 | `channel-maturity-assessor` | S-Curve de canais |
| 56 | `van-westendorp-analyzer` | Sensibilidade a preço (4 perguntas) |
| 57 | `retention-curve-classifier` | Decline, slow decline, flat ou smile |
| 58 | `five-whys-facilitator` | Análise Five Whys |
| 59 | `bad-data-detector` | Filtra elogios, fluff e feature requests |
| 60 | `chasm-diagnostic-checker` | 10 perguntas sim/não sobre o abismo |
| 61 | `market-dev-strategy-rater` | Avalia um scenario contra 9 fatores |
| 62 | `position-statement-builder` | Template de 6 slots e elevator test |
| 63 | `whole-product-gap-analyzer` | 4 círculos, gap até 100%, custo de preencher |
| 64 | `target-scenario-generator` | Header e day-in-the-life, antes e depois |
| 65 | `elevator-test-grader` | Avalia o pitch em 5 critérios e reescreve |
| 66 | `competitive-positioning-compass-plotter` | Plota competidores numa matriz 2x2 |

## Integração adaptativa com MCPs e skills

O sistema foi feito para rodar em **configurações diferentes de Claude Code**. Ele **não assume** quais MCPs ou skills você tem instalados.

Ao ser acionado, roda um passo de descoberta de ferramental: enumera os MCP servers realmente disponíveis na sessão, enumera as skills adicionais, classifica o que cada um oferece e declara o que encontrou e como pretende usar.

Princípios:

- **As bases de conhecimento são o núcleo.** As 5 bases e as 66 tools analíticas não dependem de ferramental externo. O sistema roda 100% standalone.
- **MCPs e skills trocam suposição por dado real.** Em vez de supor churn, consultar o analytics. Em vez de imaginar concorrentes, coletar dados dos sites. Em vez de estimar MRR, rodar a query.
- **Sem uso forçado.** Se nenhuma ferramenta externa agrega à recomendação atual, o sistema segue só com as bases.
- **Leitura roda livre, escrita pede autorização.** Queries e buscas executam sem perguntar. Ações com blast radius (mandar mensagem, criar ticket, deploy, mexer em produção) exigem autorização explícita.

Se nada disso existir na sua máquina, o sistema ainda entrega recomendações estratégicas sólidas, trabalhando com as premissas que você fornecer na conversa.

## Formatos de output

Os arquivos são salvos no seu Desktop:

| Formato | Usado para | Biblioteca |
|---------|-----------|------------|
| **DOCX** | Análises estratégicas, recomendações, planos de ação | `python-docx` |
| **XLSX** | Cálculos, modelos financeiros, comparações quantitativas | `openpyxl` |
| **PDF** | Resumos executivos, one-pagers, apresentações | `fpdf2` |

Markdown **nunca** é o output final, a menos que você peça.

## Regras inegociáveis

1. **Sempre consulta as bases de conhecimento** antes de responder: nunca inventa frameworks
2. **Nunca recomenda competir em preço**
3. **Sempre prioriza retenção sobre aquisição**
4. **Nunca aceita métrica de vaidade** como progresso
5. **Nunca valida ideia sem dado**: ensina o processo de validação
6. **Nunca atravessa para o mainstream em vários segmentos ao mesmo tempo**: um beachhead, dominado
7. **Nunca usa forecast hockey-stick para a travessia**: staircase realista
8. **Nunca faz pitch de tecnologia para pragmatista**: business case e peer references
9. Responde no idioma em que você escrever
10. A base de conhecimento é a fonte primária de verdade: MCPs são complementares

## Estrutura do repositório

```
open-digital-strategist/
├── .claude/
│   └── commands/
│       └── strategy.md          # o comando /strategy (o cérebro)
├── knowledge-bases/
│   ├── hormozi-knowledge-base/
│   ├── lean-startup-knowledge-base/
│   ├── mom-test-knowledge-base/
│   ├── growth-systems-knowledge-base/
│   └── crossing-the-chasm-knowledge-base/
│       ├── 02-frameworks-extraidos/   # os frameworks
│       ├── 03-knowledge-base-rag/     # princípios, conceitos, exemplos aplicados
│       └── 04-prompt-templates/       # system prompts dos agentes especialistas
├── CLAUDE.md
├── LICENSE
├── README.md
└── README.pt-BR.md
```

## Atribuição

Os frameworks referenciados aqui foram criados pelos autores e pensadores listados abaixo. Este projeto é uma implementação independente: codifica métodos publicamente documentados em um fluxo de agentes. Não tem afiliação, endosso nem patrocínio de nenhum deles, e não reproduz seus livros, cursos ou materiais.

Se um framework for útil para você, vá até a fonte. Os originais são muito mais ricos que qualquer resumo estruturado:

- **Alex Hormozi**, *$100M Offers* e *$100M Money Models* ([acquisition.com](https://www.acquisition.com))
- **Eric Ries**, *The Lean Startup* ([theleanstartup.com](http://theleanstartup.com))
- **Rob Fitzpatrick**, *The Mom Test* ([momtestbook.com](http://momtestbook.com))
- **Geoffrey A. Moore**, *Crossing the Chasm*
- **Brian Balfour**, sobre os quatro fits e growth loops ([brianbalfour.com](https://brianbalfour.com/four-fits-growth-framework))
- **Andrew Chen**, sobre growth loops e network effects ([andrewchen.com](https://andrewchen.com))
- **Casey Winters** ([caseyaccidental.com](https://caseyaccidental.com)) e **Kevin Kwok** ([kwokchain.com](https://kwokchain.com))

Ideias, métodos e sistemas não são objeto de proteção por direito autoral. A expressão específica deles é, e pertence aos autores acima. Este repositório entrega métodos e o ferramental construído em volta deles.

## Licença

MIT. Livre para usar, copiar, modificar e distribuir, comercialmente ou não. Veja o [LICENSE](LICENSE).

## Contribuindo

Issues e pull requests são bem-vindos: agentes novos, tools novas, tradução das bases de conhecimento, correções. Contribuição que cole texto protegido de livro ou de curso pago não será aceita.
