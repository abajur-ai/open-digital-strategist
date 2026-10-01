[Leia em português](README.pt-BR.md)

# Open Digital Strategist

A multi-agent business strategy system for [Claude Code](https://docs.anthropic.com/en/docs/claude-code). Type `/strategy` followed by your business challenge and the system takes over the session, running structured strategic analysis and delivering professional outputs (DOCX, XLSX, PDF).

## What it is

A senior AI strategist backed by **5 structured knowledge bases** covering growth, offers, validation, customer discovery and the transition from early market to mainstream. It does not invent frameworks: it reads the knowledge bases and applies the right principle to your specific problem.

Everything runs locally inside Claude Code. There is no server, no account, no telemetry.

## Quick start

**Requirements**

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and working
- Python 3.x with `python-docx`, `openpyxl` and `fpdf2` (document generation only)

**Install**

```bash
git clone https://github.com/abajur-ai/open-digital-strategist.git
cd open-digital-strategist
pip install python-docx openpyxl fpdf2
claude
```

**Use**

```
/strategy I need to build an irresistible offer for my B2B product
```

The `/strategy` command is picked up automatically because `.claude/commands/strategy.md` lives in the project. Run Claude Code with this repository as the working directory.

**Global install**

To make `/strategy` available from any directory, copy the command into your global Claude Code folder and point the knowledge base paths at wherever this project lives:

```bash
cp .claude/commands/strategy.md ~/.claude/commands/strategy.md
# then edit the copy, replacing "knowledge-bases/" with the absolute path
# to the knowledge-bases/ directory of this project
```

On Windows the global folder is `%USERPROFILE%\.claude\commands\`.

## Knowledge bases

Each knowledge base holds three layers: the extracted frameworks, a RAG layer with principles, concepts and applied examples, and the system prompts for the specialist agents.

### Offers and monetization

Value Equation, Grand Slam Offer, money models (attraction, upsell, downsell, continuity), premium pricing, guarantee types and offer naming.

### Lean validation

Build-Measure-Learn, the five MVP types (Video, Concierge, Wizard of Oz, Smoke Test, Single Feature), the ten pivot types, innovation accounting, actionable versus vanity metrics, and the three growth engines.

### Customer discovery

The three rules for asking questions people cannot lie about, separating signal from noise, customer slicing down to who-where pairs, spotting earlyvangelists, detecting zombie leads, and conversation planning.

### Growth systems

Growth models as concentric layers, retention curves and habit loops, acquisition loops (Growth Multiplier, K-Factor, channel S-curves), the four fits of monetization, user psychology (ELMR, Psych!, core desires), experimentation and defensibility.

### Crossing to the mainstream

The revised technology adoption cycle and the gap between early adopters and the early majority, the D-Day beachhead strategy, the whole product 100% rule, the market development strategy checklist, creating the competition, positioning statements and the elevator test, distribution-oriented pricing, and staircase versus hockey stick forecasting.

> Knowledge base files are currently written in Brazilian Portuguese. The agent answers in whatever language you write in, so this does not affect usage.

## Capability catalog (66 tools)

### Atomic agents (28)

| # | Agent | Base | Function |
|---|--------|------|--------|
| 1 | `offer-builder` | Offers | Build a complete Grand Slam Offer |
| 2 | `money-model-architect` | Offers | Architect the monetization sequence |
| 3 | `pricing-consultant` | Offers | Premium pricing consulting |
| 4 | `downsell-agent` | Offers | Full downsell process (7 steps) |
| 5 | `guarantee-strategist` | Offers | Build guarantees (4 types) |
| 6 | `offer-naming` | Offers | Magnetic names with the MAGIC formula |
| 7 | `idea-validator` | Lean | Validate ideas against leap-of-faith assumptions |
| 8 | `mvp-designer` | Lean | Design the minimum MVP (5 types) |
| 9 | `pivot-advisor` | Lean | Decide pivot or persevere (10 types) |
| 10 | `innovation-accountant` | Lean | Set up innovation accounting |
| 11 | `growth-engine-selector` | Lean | Identify your growth engine |
| 12 | `interview-coach` | Discovery | Train question formulation |
| 13 | `conversation-analyzer` | Discovery | Separate signal from noise in notes |
| 14 | `customer-segmenter` | Discovery | Customer slicing to who-where pairs |
| 15 | `conversation-planner` | Discovery | Prepare conversation batches |
| 16 | `signal-detector` | Discovery | Detect earlyvangelists and zombie leads |
| 17 | `growth-strategist` | Growth | Assess the growth system holistically |
| 18 | `retention-specialist` | Growth | Diagnose retention and engagement |
| 19 | `acquisition-architect` | Growth | Optimize acquisition loops |
| 20 | `monetization-consultant` | Growth | Define the monetization model |
| 21 | `experiment-designer` | Growth | Build hypotheses and prioritize experiments |
| 22 | `user-psych-analyst` | Growth | User psychology (ELMR, Psych!) |
| 23 | `chasm-crossing-strategist` | Chasm | Holistic diagnosis plus D-Day plan |
| 24 | `target-customer-architect` | Chasm | Scenarios plus market development checklist |
| 25 | `whole-product-manager` | Chasm | Whole product (100% rule) plus partners |
| 26 | `positioning-strategist` | Chasm | Creating the competition, positioning statement, elevator test |
| 27 | `chasm-distribution-architect` | Chasm | High-tech channel plus distribution-oriented pricing |
| 28 | `postchasm-transition-advisor` | Chasm | Pioneers to settlers plus staircase |

### Composite agents (18), cross-knowledge-base

| # | Agent | Bases | Function |
|---|--------|-------|--------|
| 29 | `product-market-fit-assessor` | Lean + Discovery + Growth | Holistic PMF assessment |
| 30 | `go-to-market-architect` | Offers + Growth + Lean | Full GTM strategy |
| 31 | `customer-to-offer-pipeline` | Discovery + Offers | From discovery to offer |
| 32 | `full-stack-growth-auditor` | Growth + Offers + Lean | Complete growth audit |
| 33 | `experiment-to-insight-engine` | Growth + Lean + Discovery | End-to-end experimentation |
| 34 | `pricing-overhaul` | Offers + Growth | Pricing restructure |
| 35 | `churn-killer` | Growth + Offers | Multi-front anti-churn plan |
| 36 | `pivot-or-iterate-tribunal` | Lean + Discovery + Growth | Pivot tribunal with 3 perspectives |
| 37 | `offer-fatigue-refresher` | Offers + Growth | Refresh a fatigued offer |
| 38 | `beachhead-discoverer` | Chasm + Discovery + Lean | Discovery to slicing to checklist to BML loop |
| 39 | `whole-product-offer-architect` | Chasm + Offers | Whole product as the foundation for the offer |
| 40 | `chasm-experiment-designer` | Chasm + Growth + Lean | Experiments per psychographic phase |
| 41 | `psychographic-growth-strategist` | Chasm + Growth | Growth loops per psychographic phase |
| 42 | `pragmatist-offer-translator` | Chasm + Offers + Discovery | Translate a visionary offer for pragmatists |
| 43 | `stuck-in-the-chasm-diagnostic` | Chasm + Lean + Growth | Flat sales: chasm, churn or wrong segment |
| 44 | `bowling-pin-expansion-planner` | Chasm + Growth + Offers | Expansion sequence after the beachhead |
| 45 | `staircase-financial-planner` | Chasm + Lean + Growth | Staircase model plus innovation accounting |
| 46 | `psychographic-positioning-translator` | Chasm + Growth + Offers | Positioning per psychographic group |

### Utility tools (20)

| # | Tool | Function |
|---|------|--------|
| 47 | `value-equation-calculator` | Value Equation calculator (4 variables) |
| 48 | `growth-multiplier-calculator` | GM = 1/(1-V) with scenarios |
| 49 | `k-factor-calculator` | k = i x c with projection |
| 50 | `model-market-fit-checker` | 1Y ARPU x customers x capturable share |
| 51 | `question-grader` | Grade questions against the three rules |
| 52 | `meeting-scorer` | Classify a meeting as success or failure |
| 53 | `earlyvangelist-scorer` | Earlyvangelist score, 0 to 5 |
| 54 | `psych-mapper` | Map positive and negative psych per step |
| 55 | `channel-maturity-assessor` | Channel S-curve |
| 56 | `van-westendorp-analyzer` | Price sensitivity (4 questions) |
| 57 | `retention-curve-classifier` | Decline, slow decline, flat or smile |
| 58 | `five-whys-facilitator` | Five Whys analysis |
| 59 | `bad-data-detector` | Filter compliments, fluff and feature requests |
| 60 | `chasm-diagnostic-checker` | 10 yes/no questions on chasm position |
| 61 | `market-dev-strategy-rater` | Score a scenario against 9 factors |
| 62 | `position-statement-builder` | 6-slot template plus elevator test |
| 63 | `whole-product-gap-analyzer` | 4 circles, gap to 100%, cost to close |
| 64 | `target-scenario-generator` | Header plus day-in-the-life, before and after |
| 65 | `elevator-test-grader` | Grade a pitch on 5 criteria plus rewrite |
| 66 | `competitive-positioning-compass-plotter` | Plot competitors on a 2x2 matrix |

## Adaptive integration with MCPs and skills

The system is built to run on **many different Claude Code setups**. It does **not** assume which MCP servers or skills you have installed.

On startup it runs a tooling discovery step: it enumerates the MCP servers actually available in the session, enumerates additional skills, classifies what each one offers, and tells you what it found and how it plans to use it.

Principles:

- **The knowledge bases are the core.** The 5 bases and 66 analytical tools do not depend on external tooling. The system runs fully standalone.
- **MCPs and skills replace assumptions with real data.** Instead of guessing churn, query the analytics. Instead of imagining competitors, scrape their sites. Instead of estimating MRR, run the query.
- **No forced usage.** If no external tool adds value to the current recommendation, the system proceeds on the knowledge bases alone.
- **Read-only runs free, writes ask first.** Queries and searches execute without asking. Anything with blast radius (sending messages, creating tickets, deploying, touching production) requires explicit authorization.

If none of that exists on your machine, the system still delivers solid strategic recommendations, working from the premises you provide in the conversation.

## Output formats

Files are written to your Desktop:

| Format | Used for | Library |
|---------|-----------|------------|
| **DOCX** | Strategic analysis, recommendations, action plans | `python-docx` |
| **XLSX** | Calculations, financial models, quantitative comparisons | `openpyxl` |
| **PDF** | Executive summaries, one-pagers, presentations | `fpdf2` |

Markdown is **never** the final output unless you ask for it.

## Non-negotiable rules

1. **Always consults the knowledge bases** before answering: it never invents frameworks
2. **Never recommends competing on price**
3. **Always prioritizes retention over acquisition**
4. **Never accepts vanity metrics** as progress
5. **Never validates an idea without data**: it teaches the validation process instead
6. **Never crosses to the mainstream in multiple segments at once**: one beachhead, dominated
7. **Never uses hockey-stick forecasts for the crossing**: realistic staircase
8. **Never pitches technology to a pragmatist**: business case plus peer references
9. Answers in the language you write in
10. The knowledge base is the primary source of truth: MCPs are complementary

## Repository structure

```
open-digital-strategist/
├── .claude/
│   └── commands/
│       └── strategy.md          # the /strategy command (the brain)
├── knowledge-bases/
│   ├── hormozi-knowledge-base/
│   ├── lean-startup-knowledge-base/
│   ├── mom-test-knowledge-base/
│   ├── growth-systems-knowledge-base/
│   └── crossing-the-chasm-knowledge-base/
│       ├── 02-frameworks-extraidos/   # the frameworks themselves
│       ├── 03-knowledge-base-rag/     # principles, concepts, applied examples
│       └── 04-prompt-templates/       # specialist agent system prompts
├── CLAUDE.md
├── LICENSE
├── README.md
└── README.pt-BR.md
```

## Attribution

The frameworks referenced here were created by the authors and thinkers below. This project is an independent implementation: it encodes publicly documented methods into an agent workflow. It is not affiliated with, endorsed by, or sponsored by any of them, and it does not reproduce their books, courses or materials.

If a framework is useful to you, go to the source. The originals are far richer than any structured summary:

- **Alex Hormozi**, *$100M Offers* and *$100M Money Models* ([acquisition.com](https://www.acquisition.com))
- **Eric Ries**, *The Lean Startup* ([theleanstartup.com](http://theleanstartup.com))
- **Rob Fitzpatrick**, *The Mom Test* ([momtestbook.com](http://momtestbook.com))
- **Geoffrey A. Moore**, *Crossing the Chasm*
- **Brian Balfour**, on the four fits and growth loops ([brianbalfour.com](https://brianbalfour.com/four-fits-growth-framework))
- **Andrew Chen**, on growth loops and network effects ([andrewchen.com](https://andrewchen.com))
- **Casey Winters** ([caseyaccidental.com](https://caseyaccidental.com)) and **Kevin Kwok** ([kwokchain.com](https://kwokchain.com))

Ideas, methods and systems are not subject to copyright protection. The specific expression of them is, and it belongs to the authors above. This repository ships methods and the tooling built around them.

## License

MIT. Free to use, copy, modify and distribute, commercially or not. See [LICENSE](LICENSE).

## Contributing

Issues and pull requests are welcome: new agents, new tools, translations of the knowledge bases, fixes. Contributions that paste in copyrighted text from books or paid courses will not be merged.
