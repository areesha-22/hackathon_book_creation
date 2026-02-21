---
id: 1
title: Create Project Constitution
stage: constitution
date_iso: 2026-02-18
surface: agent
model: claude-sonnet-4-6
feature: none
branch: main
user: user
command: /sp.constitution
labels:
  - constitution
  - governance
  - setup
links:
  spec: null
  ticket: null
  adr: null
  pr: null
files_yaml:
  - .specify/memory/constitution.md
tests_yaml: []
prompt_text: |

  Project:
  AI-driven technical book built with Docusaurus (via Claude Code + Spec-Kit Plus) and deployed to GitHub Pages, with an embedded RAG chatbot using OpenAI Agents SDK, FastAPI, Neon Postgres, and Qdrant Cloud.

  Core Principles:
  - Spec-first development (Spec-Kit Plus before coding)
  - Accuracy aligned with official documentation
  - Modular clean architecture
  - Retrieval-grounded responses (no hallucination)
  - Reproducible deployment

  Key Standards:
  - Book written in structured Markdown (Docusaurus)
  - Backend: FastAPI (typed, RESTful)
  - Vector DB: Qdrant Cloud (embeddings stored here)
  - Metadata: Neon Serverless Postgres
  - Agent framework: OpenAI Agents / ChatKit SDK
  - RAG must support:
    - Full-book queries
    - Selected-text queries
    - Top-k semantic retrieval
    - Confidence-based response filtering

  Constraints:
  - No hardcoded secrets (use env variables)
  - No unverified technical claims
  - Stateless API design
  - Must deploy book to GitHub Pages
  - Must use required stack (no substitutions)

  Success Criter
response_text: |
  Created a project constitution based on the specifications for the AI-driven technical book project. The constitution includes core principles for spec-first development, accuracy alignment, clean modular architecture, retrieval-grounded responses, stack compliance, and stateless API design. It also defines constraints, requirements, development workflow, and governance procedures.
outcome: |
  Successfully created the project constitution file at .specify/memory/constitution.md with all specified principles and requirements.
evaluation: |
  The constitution file has been created with all required principles and follows the proper format. All placeholders have been replaced with specific content related to the technical book RAG project.
---

# Prompt History Record

## Summary
Created a project constitution for the AI-driven technical book with RAG capabilities based on the user's specifications.

## Details
- Updated the constitution template with project-specific principles
- Included all required constraints and standards from the user input
- Defined development workflow and governance procedures
- Ensured compliance with stack requirements and architectural principles