# AU Deconstruction RAG (ChromaDB + OpenAI + Gradio)

This repository contains:
- A dataset of `95` `.kept.jsonl` files with `364` total extracted chunks.
- A Google Colab notebook that builds a ChromaDB RAG index from scratch each run.
- A simple Gradio chat UI that answers questions with citations (`chunk_id`).

## Repository structure

- `data/kept_chunks/Chunks/`: source JSONL chunk files
- `notebooks/au_deconstruction_rag_colab.ipynb`: end-to-end Colab notebook
- `chroma_db/`: local persistent Chroma directory (rebuilt from scratch by notebook)
- `requirements.txt`: optional local environment dependencies

## Run in Google Colab

1. Upload this repository to GitHub.
2. Open `notebooks/au_deconstruction_rag_colab.ipynb` in Colab.
3. Add secret `OPENAI_API_KEY` in Colab secrets.
4. Run all cells in order.
5. Ask questions in the Gradio app.

## Notes

- The notebook deletes and rebuilds `chroma_db` on each run to ensure reproducibility.
- Answers include citations with `chunk_id` and source file metadata.
