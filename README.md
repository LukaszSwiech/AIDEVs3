# AIDEVs3

JavaScript solutions to select tasks from the **AIDEVs3** course. Not every
lesson required a scripted solution, so only the tasks that did are included
here.

> **Code was written by hand, with heavy AI assistance in [Cursor](https://cursor.com)
> using Claude 3.5 Sonnet** as a pair programmer for exploring approaches,
> drafting code, and debugging.

## Techniques used

- **Agent loops** — iterative calls against external lookup APIs until a
  termination condition is met (S03E04)
- **Audio transcription** — Whisper (S02E01, S02E04, S02E05)
- **Vision / multimodal** — image reasoning and OCR via GPT-4o (S02E02,
  S02E04, S02E05)
- **Image generation** — DALL-E 3 (S02E03)
- **RAG / vector search** — OpenAI embeddings indexed in Qdrant (S03E02)
- **Text-to-SQL** — LLM-generated SQL executed against a live database (S03E03)
- **Structured (JSON-mode) output** — classification and extraction (S02E04,
  S03E04)
- **Keyword tagging & semantic enrichment** across fact/report corpora (S03E01)
- **Prompt engineering** — few-shot and strict-output prompts, including
  prompt-injection-resistant instructions (S01E01, S01E02)
- **Web scraping** — HTML-to-markdown extraction via a reader proxy (S02E05)

## Stack

- **Runtime**: Node.js
- **AI API**: OpenAI, called directly (raw `fetch` in earlier tasks, the
  official `openai` SDK from S02E01 onward)
- **Models**: GPT-4o / GPT-4o-mini, Whisper, DALL-E 3, text-embedding-3-large
- **Vector DB**: Qdrant

## Structure

```
S01E01/   robot login — LLM answers a trivia challenge to authenticate
S01E02/   robot verification dialogue, resisting a prompt-injection check
S01E03/   JSON data repair + LLM-answered questions, resubmitted
S01E05/   PII censorship of a text file via LLM
S02E01/   Whisper transcription of recordings + QA over the transcripts
S02E02/   vision-based map fragment identification
S02E03/   DALL-E 3 image generation from a text description
S02E04/   multimodal document classification (audio + image + text)
S02E05/   multi-stage pipeline: scraping, transcription, QA over sections
S03E01/   keyword tagging & semantic enrichment across fact/report files
S03E02/   embeddings + Qdrant vector search (RAG)
S03E03/   text-to-SQL query generation against a live database
S03E04/   multi-step agent loop searching people/places lookup APIs
```

## Running a task

Each folder is a standalone script with its own `package.json` and `.env`.
From inside a task folder:

```bash
npm install
node <entry-file>.js
```
