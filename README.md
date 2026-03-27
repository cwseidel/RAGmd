````markdown
# ragmd

A command-line tool for exploring and curating project directories built around Markdown documents.

## Overview

`ragmd` is designed for researchers and analysts who organize work in directory-based projects. Each project directory typically contains:

- Markdown (`.md`) or R Markdown (`.Rmd`) documents
- Analysis notes and results
- Scripts and intermediate outputs

Over time, these directories become difficult to navigate and synthesize. `ragmd` helps by:

- Indexing documents within a project directory
- Allowing natural language queries over your notes
- Acting as a "curation assistant" to improve documentation quality
- Encouraging structured, narrative-driven project organization

The goal is not just retrieval, but **understanding and improving your project documentation**.

---

## Key Features (Current / Planned)

### Core
- Parse `.md` and `.Rmd` files
- Build a searchable index using embeddings
- Query documents using natural language
- Retrieve relevant sections with context

### Curation Assistant (Planned)
- Detect missing or weak project documentation
- Suggest improvements (e.g., purpose, hypotheses, narrative flow)
- Encourage biologically meaningful questions
- Highlight gaps or inconsistencies across documents

### Project Awareness (Planned)
- Integrate with project-level YAML metadata
- Understand relationships between projects
- Surface connections across directories

---

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/ragmd.git
cd ragmd
````

Create an environment using Conda. I used an environment I installed for [paper-qa](https://github.com/Future-House/paper-qa) from Future House, and the added the following things to it.

```bash
pip install sentence-transformers faiss-cpu click rich openai
```


python -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Usage

From within a project directory:

Index a directory.

```bash
ragmd index
```

Get index stats files/chunks/embeddings.

```bash
ragmd stats
```

```bash
ragmd ask "What is the main question of this project?"
```

Example queries:

```bash
ragmd ask "Summarize this project"
ragmd ask "What datasets are being used?"
ragmd ask "What conclusions have been drawn?"
ragmd ask "Are there any missing pieces in this analysis?"
```

---

## How It Works

1. **Document Parsing**

   * Reads `.md` and `.Rmd` files in the directory

2. **Chunking**

   * Splits documents into manageable sections

3. **Embedding**

   * Converts text chunks into vector representations

4. **Indexing**

   * Stores embeddings in a local vector database (e.g., FAISS)

5. **Querying**

   * Matches user queries to relevant document sections
   * Uses an LLM to synthesize answers

---

## Philosophy

This tool is built around a few core ideas:

* A **project directory is a unit of thought**
* Documentation should tell a **coherent story**
* Analysis should be guided by **clear biological questions**
* AI should act as a **curious collaborator**, not just a search engine

---

## Example Project Structure

```text
project_X/
├── notes.md
├── analysis.Rmd
├── results.md
├── figures/
├── data/
└── project.yml   # (optional, planned integration)
```

---

## Development

Basic workflow:

```bash
git checkout -b feature/your-feature
# make changes
git add .
git commit -m "Describe your change"
git push
```

---

## Roadmap

* [ ] Support `.Rmd` parsing with code-awareness
* [ ] Persistent local index per project
* [ ] YAML project metadata integration
* [ ] Cross-project querying
* [ ] "Curation mode" (proactive suggestions)
* [ ] CLI improvements (flags, config, roles)
* [ ] Packaging for easy install (`pip install ragmd`)

---

## Contributing

This is an evolving tool. Contributions, ideas, and feedback are welcome.

---

## License

TBD

