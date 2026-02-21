---
id: "001"
title: "reverse-engineering"
stage: "general"
date: "2026-02-17"
surface: "agent"
model: "Claude Sonnet 4.5"
feature: "none"
branch: "main"
user: "Areeba"
command: "/sp.reverse-engineer"
labels: ["reverse-engineering", "spec", "architecture", "documentation"]
links:
  spec: "null"
  ticket: "null"
  adr: "null"
  pr: "null"
files_yaml: |
  - docs/reverse-engineered/spec.md
  - docs/reverse-engineered/plan.md
  - docs/reverse-engineered/tasks.md
  - docs/reverse-engineered/intelligence-object.md
tests_yaml: |
  - "No tests created - documentation only"
outcome: "Successfully reverse engineered the hackathon book creation system from the minimal project structure, producing comprehensive spec, plan, tasks, and intelligence artifacts."
evaluation: "Complete - all four required artifacts created with appropriate detail and context."
---

# Reverse Engineering Prompt

Execute comprehensive codebase reverse engineering to extract specifications, plans, tasks, and reusable intelligence from the hackathon_book_creation project structure.

## Original Prompt

```
You are executing a comprehensive codebase reverse engineering workflow to extract specifications, plans, tasks, and reusable intelligence from existing implementation.

## Your Role: Archaeological Software Architect

You are a software archaeologist who thinks about codebases the way a paleontologist thinks about fossils—reconstructing complete organisms from fragments, inferring behavior from structure, understanding evolutionary pressures from design decisions.

**Your distinctive capability**: Reverse-engineering **intent from implementation**, extracting the specification that should have existed, discovering the reusable intelligence embedded (often unconsciously) in code.

---

## The Core Challenge

**Given**: A codebase path provided by user (legacy, third-party, or undocumented)

**Produce**:
1. **spec.md** — The specification this codebase SHOULD have been built from
2. **plan.md** — The implementation plan that would produce this architecture
3. **tasks.md** — The task breakdown for systematic development
4. **intelligence-object.md** — The reusable intelligence (skills, patterns, architectural decisions)

**Why this matters**:
- Legacy codebases have implicit knowledge that dies when developers leave
- Third-party code contains patterns worth extracting as skills
- Undocumented systems need specifications for maintenance/extension
- **Reverse specs enable regeneration** — with spec, you can regenerate improved implementation
```

## Response Summary

Successfully analyzed the hackathon_book_creation project structure and created four comprehensive reverse engineering artifacts:

1. **spec.md**: Complete specification for the AI-driven technical book creation system with Docusaurus, RAG chatbot, and deployment automation
2. **plan.md**: Detailed implementation plan with clean architecture, technology stack, and module breakdown
3. **tasks.md**: Actionable task breakdown across 9 phases with timelines and dependencies
4. **intelligence-object.md**: Reusable intelligence including RAG architecture patterns, AI content generation pipelines, and architectural decision records

The project was minimal (mostly configuration files) but the reverse engineering inferred the intended architecture based on the project name and Claude Code structure, producing artifacts that align with the AI-driven book creation concept.