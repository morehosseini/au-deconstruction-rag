# Building a Domain-Specific Retrieval-Augmented Generation System for Australian Building Deconstruction

[![DOI](https://img.shields.io/badge/DOI-pending-lightgrey)]()
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
![GitHub last commit](https://img.shields.io/github/last-commit/morehosseini/au-deconstruction-rag)

## Overview

This repository contains the data and code supporting the paper *"Building a Domain-Specific Retrieval-Augmented Generation System for Australian Building Deconstruction"*. The system implements a Retrieval-Augmented Generation (RAG) pipeline tailored to the Australian building deconstruction domain, enabling evidence-grounded question answering over a curated corpus of policy, regulatory, and industry reports.

The pipeline ingests 95 JSONL chunk files (364 extracted chunks) derived from Australian deconstruction and waste management documents, builds a ChromaDB vector index using OpenAI embeddings, and exposes an interactive Gradio chat interface with citation-level provenance for every answer generated.

**Authors:**
- Dr. M. Reza Hosseini — Faculty of Architecture, Building and Planning, The University of Melbourne
- K.A.D.M. Natasha

**Status:** Manuscript in preparation. DOI pending.

---

## Repository Structure

```
au-deconstruction-rag/
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt             # Python dependencies
├── notebooks/
│   └── au_deconstruction_rag_colab.ipynb   # End-to-end Colab notebook
├── data/
│   └── kept_chunks/
│       └── Chunks/              # 95 × .kept.jsonl chunk files (364 chunks)
├── docs/
│   └── Revision_2-RAG_Paper_Final.docx     # Latest manuscript draft
└── figures/
    └── [screenshots]            # System screenshots
```

---

## Getting Started

### Prerequisites

- Python ≥ 3.9
- An OpenAI API key ([get one here](https://platform.openai.com/api-keys))
- Google Colab (recommended) or a local Python environment

### Installation

```bash
git clone https://github.com/morehosseini/au-deconstruction-rag.git
cd au-deconstruction-rag
pip install -r requirements.txt
```

### Running in Google Colab (Recommended)

1. Clone or upload this repository to your Google Drive.
2. Open `notebooks/au_deconstruction_rag_colab.ipynb` in [Google Colab](https://colab.research.google.com/).
3. Add a Colab secret named `OPENAI_API_KEY`:
   - Left sidebar → **Secrets** → **Add new secret**
   - Name: `OPENAI_API_KEY` | Value: your key
4. Update `REPO_ROOT` in Cell 2 to point to your Drive folder.
5. Run all cells in order.
6. Ask questions via the Gradio chat interface that launches at the end.

### Local Usage

```bash
jupyter notebook notebooks/au_deconstruction_rag_colab.ipynb
```

Set `OPENAI_API_KEY` as an environment variable before running locally.

---

## Technologies

| Component | Technology |
|---|---|
| Vector database | [ChromaDB](https://www.trychroma.com/) ≥ 0.5.5 |
| Embeddings & LLM | [OpenAI API](https://platform.openai.com/) (`text-embedding-3-small`, `gpt-4.1-mini`) |
| Chat interface | [Gradio](https://www.gradio.app/) ≥ 4.44 |
| Data processing | [pandas](https://pandas.pydata.org/) ≥ 2.0 |
| Notebook environment | Google Colab / Jupyter |

---

## Dataset

The `data/kept_chunks/Chunks/` directory contains **95 JSONL files** with **364 curated text chunks** extracted from Australian building deconstruction, construction and demolition waste, and circular economy policy documents. Each chunk record includes:

| Field | Description |
|---|---|
| `chunk_id` | Unique identifier for the chunk |
| `source_file` | Original document name |
| `page_num` | Page number in the source document |
| `chunk_index` | Sequential index within the source |
| `relevance` | Relevance label assigned during curation |
| `text` | Extracted text content |

---

## Citation

If you use this code or dataset in your research, please cite:

```bibtex
@article{hosseini2026rag,
  author  = {Hosseini, M. Reza and Natasha, K.A.D.M.},
  title   = {Building a Domain-Specific Retrieval-Augmented Generation System
             for Australian Building Deconstruction},
  journal = {(in preparation)},
  year    = {2026},
  doi     = {pending},
  url     = {https://github.com/morehosseini/au-deconstruction-rag}
}
```

---

## Licence

This project is licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** Licence — see the [LICENSE](LICENSE) file for details. You are free to share and adapt the material for any purpose, provided appropriate credit is given.

---

## Contributing

Contributions and issue reports are welcome. Please open a [GitHub Issue](https://github.com/morehosseini/au-deconstruction-rag/issues) to discuss proposed changes before submitting a pull request.

## Contact

**Dr. M. Reza Hosseini**
Senior Lecturer in Construction Technology
Faculty of Architecture, Building and Planning, The University of Melbourne
📧 mreza.hosseini@unimelb.edu.au

For questions about this repository, open a [GitHub Issue](https://github.com/morehosseini/au-deconstruction-rag/issues).

---

*This repository was prepared in accordance with open-science and FAIR-data principles.*
