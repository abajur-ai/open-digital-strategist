# Open Digital Strategist: project instructions

This repository holds **Open Digital Strategist**, a multi-agent business strategy system for Claude Code.

## How to use

The `/strategy` command is available automatically when Claude Code runs with this repository as the working directory.

```
/strategy [describe your business challenge here]
```

## Knowledge bases

The knowledge bases live in `knowledge-bases/` at the repository root. When reading any of them, use the path relative to the project root.

Each base has three layers:

- `02-frameworks-extraidos/`: the frameworks themselves
- `03-knowledge-base-rag/`: principles, concepts and applied examples
- `04-prompt-templates/`: system prompts for the specialist agents

The knowledge base files are written in Brazilian Portuguese. Answer in the language the user writes in.

## Python dependencies

For document generation (DOCX, XLSX, PDF):

```bash
pip install python-docx openpyxl fpdf2
```

## Rules

- Outputs are saved to `~/Desktop/` in business formats (DOCX, XLSX, PDF)
- The knowledge bases are the primary source of truth. MCP servers available on the user's machine are complementary
- NEVER commit credentials, API keys or sensitive data to this repository
- NEVER paste copyrighted text from books or paid courses into the knowledge bases. This project ships methods and frameworks, not reproductions
