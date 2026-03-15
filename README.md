# 🔒 Deep Trust Model 0.0.1 — Collecting · Splitting · Embedding · Retrieving

> **Deep Trust Model** is a lightweight **trust-oriented RAG and document intelligence workflow** for **structured files, screenshots, annotations, and semantic retrieval**.  
> It supports **manual ROI collection, structure-aware text splitting, recursive chunk refinement, embedding, pooling, and similarity-based querying** for downstream **LLM retrieval, repository search, and knowledge pipelines**.

---

## 🌟 Project Overview

Deep Trust Model is designed for **high-trust retrieval workflows** where raw information must be collected, cleaned, structured, embedded, and searched in a transparent way.
It emphasizes a modular pipeline so each step can be inspected, improved, and reused independently.

A key part of this workflow is the **OmniParser BBox Clicker**, a lightweight bounding-box annotation tool for manually defining image regions of interest before downstream processing.

### 💡 In one sentence

```text
Raw files or images → ROI collection + structure-aware splitting → recursive chunking → embedding + pooling → semantic querying → trusted retrieval for LLM workflows
```

---

## 🚀 Key Features

| Category | What Deep Trust Model does | Why it matters |
|---|---|---|
| 🖱️ **ROI Collection with Clicker** | Uses a lightweight click-and-drag bounding-box tool to capture regions of interest from images | Makes manual data collection fast, transparent, and reproducible |
| 🧱 **Structure-Aware Splitting** | Preserves document hierarchy such as `#`, `##`, and `###` headers before chunking | Keeps semantic meaning stronger than flat text splitting |
| ✂️ **Recursive Chunk Refinement** | Further divides large text into retrieval-friendly chunks | Helps stay within embedding limits and improves retrieval precision |
| 🧠 **Embedding Pipeline** | Converts each chunk into vector representations | Enables semantic search beyond exact keyword matching |
| 🌀 **Pooling Layer** | Aggregates or stabilizes embedding outputs for downstream similarity comparison | Improves consistency when comparing chunks and queries |
| 🔎 **Querying Module** | Embeds user queries and retrieves the most relevant chunks | Forms the retrieval core for RAG and repository search |
| 🧩 **Modular PyPI-Style Tools** | Each step can be packaged as an independent tool or CLI module | Makes the workflow easier to test, publish, and extend |

---

## 🧠 Core Idea

Instead of sending raw documents directly into an LLM, Deep Trust Model breaks the problem into explicit stages:
**collect → structure → split → embed → pool → query**.

This makes the workflow easier to debug, easier to explain, and more trustworthy for scientific, technical, or repository-scale knowledge systems.

### 🔄 Conceptual pipeline

```mermaid
flowchart LR
    A[📂 Raw files / screenshots / documents] --> B[🖱️ OmniParser BBox Clicker]
    B --> C[🧱 MarkdownHeaderTextSplitter]
    C --> D[✂️ RecursiveCharacterTextSplitter]
    D --> E[🧠 Embedding]
    E --> F[🌀 Pooling]
    F --> G[🔎 Querying]
    G --> H[✅ Trusted retrieval chunks for LLM use]
```

---

## 🧪 System Components

### 1. 🖱️ OmniParser BBox Clicker

The Clicker module is designed for fast manual annotation of image regions.
It is especially useful when screenshots, interface panels, or image-based inputs need human-defined bounding boxes before later parsing or model workflows.

#### What it does

- interactive **click-and-drag** bounding box selection
- immediate visual overlay feedback
- exports coordinates such as **(x1, y1, x2, y2)**
- lightweight alternative to heavier annotation platforms
- useful for dataset preparation and preprocessing workflows

#### Why it matters

Manual ROI selection is often the first trust step in a data pipeline: it lets the user explicitly decide **what information should enter the system**.

---

### 2. 🧱 MarkdownHeaderTextSplitter

This module preserves Markdown hierarchy before chunking.
Instead of flattening a document into raw text, it respects structural boundaries such as headings and subheadings.

#### Why this matters

Documents often carry meaning in their structure.
A chunk under `## Methods` should not be treated the same as a chunk under `## Results`.
Structure-aware splitting helps maintain that context.

---

### 3. ✂️ RecursiveCharacterTextSplitter

After structural splitting, larger text blocks can still be too long for efficient embedding.
This step breaks them into smaller retrieval-ready chunks while preserving as much local coherence as possible.

#### Why this matters

- reduces chunk size to fit embedding constraints
- improves retrieval granularity
- prevents oversized sections from dominating semantic search

---

### 4. 🧠 Embedding

Each chunk is transformed into a vector representation using an embedding model.
This is the stage that allows the system to compare meaning rather than only exact words.

#### Why this matters

Embedding makes it possible to retrieve semantically related chunks even when the wording is different from the query.

---

### 5. 🌀 Pooling

Pooling converts token-level or intermediate embedding information into a stable representation suitable for chunk-level comparison.
Depending on the embedding design, this may involve selecting or aggregating token information.

#### Why this matters

Pooling helps produce a consistent vector output for ranking and retrieval.
It is an important bridge between raw embedding output and usable semantic search.

---

### 6. 🔎 Querying

The Querying module takes a user sentence or prompt, embeds it with the same embedding space, and compares it against stored chunk vectors.
The highest-scoring chunks can then be passed into an LLM.

#### What it does

- embeds the user query
- compares query vectors to chunk vectors
- ranks chunks by similarity
- returns the most relevant text for downstream LLM use

---

## 🧰 What Deep Trust Model Produces

Depending on the workflow stage, the project is designed to generate:

| Output Type | Description |
|---|---|
| 🖱️ ROI coordinates | Bounding-box annotations from images or screenshots |
| 🧱 Structured text blocks | Header-aware document sections |
| ✂️ Refined chunks | Smaller retrieval-optimized text segments |
| 🧠 Embedding vectors | Semantic numerical representations of chunks |
| 🌀 Pooled representations | Stable chunk-level vectors for comparison |
| 🔎 Retrieval results | Ranked chunks most relevant to a query |
| 🤖 LLM-ready context | Trusted context blocks for RAG prompting |

---

## 🎯 Best-Fit Use Cases

Deep Trust Model is especially useful when you want to:

- build a **transparent RAG pipeline** step by step
- search **repositories, notes, or scientific documents** semantically
- preprocess **screenshots or image regions** before extraction
- keep **chunking and retrieval explainable** rather than opaque
- create **modular PyPI tools** for each stage of the workflow

---

## ✨ Project Highlights

| Highlight | Summary |
|---|---|
| 🔒 Trust-oriented design | Breaks retrieval into explicit, inspectable stages |
| 🖱️ Manual collection support | Includes lightweight ROI annotation through the Clicker module |
| 🧱 Structure-preserving preprocessing | Respects Markdown hierarchy before recursive chunking |
| 🧠 Semantic retrieval pipeline | Embedding, pooling, and querying support meaning-based search |
| 🧩 Modular architecture | Each stage can be developed, packaged, and tested independently |
| 🤖 RAG-ready output | Produces clean context chunks for downstream LLM prompting |

---

## 🗂️ Suggested README Expansion Later

This refined version keeps the current project direction while matching the polished documentation vibe.
Helpful next sections to add later would be:

- installation and environment setup
- CLI usage for each module
- example input and output files
- supported embedding models
- chunk size and pooling configuration options
- benchmark examples for retrieval quality
- repository search demo or screenshot examples

---

## 🧾 Short Summary

**Deep Trust Model is a modular trust-oriented RAG workflow that combines ROI collection, structure-aware splitting, recursive chunking, embedding, pooling, and semantic querying to produce reliable LLM-ready retrieval context.**
