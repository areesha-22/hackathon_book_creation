<!-- SYNC IMPACT REPORT
Version change: N/A -> 1.0.0
Modified principles: N/A (new constitution)
Added sections: All sections
Removed sections: None
Templates requiring updates: N/A
Follow-up TODOs: None
-->
# Technical Book RAG Constitution

## Core Principles

### I. Spec-First Development
All development follows the Spec-Kit Plus methodology before any code implementation begins. Every feature must have a complete specification document that outlines requirements, interfaces, and acceptance criteria before implementation starts.

### II. Accuracy and Documentation Alignment
All technical content and implementation details must align with official documentation from referenced technologies (Docusaurus, OpenAI Agents SDK, FastAPI, Neon Postgres, Qdrant Cloud). No unverified technical claims or assumptions are permitted in the codebase or documentation.

### III. Clean Modular Architecture
The system must follow clean architecture principles with clear separation of concerns. The frontend (Docusaurus), backend (FastAPI), vector database (Qdrant Cloud), and metadata storage (Neon Postgres) must be designed as independent, loosely coupled modules with well-defined interfaces.

### IV. Retrieval-Grounded Responses (No Hallucination)
The RAG chatbot must only respond based on retrieved information from the technical book content. The system must implement confidence-based response filtering to prevent hallucinations and clearly indicate when information is not available in the source material.

### V. Stack Compliance
The project must strictly adhere to the required technology stack: Docusaurus for documentation, FastAPI for backend services, Qdrant Cloud for vector embeddings, Neon Serverless Postgres for metadata, and OpenAI Agents SDK for the chatbot functionality. No substitutions or alternatives are allowed without explicit approval.

### VI. Stateless API Design
All backend services must follow stateless design principles. No server-side session storage or persistent connections. The API must be horizontally scalable and resilient to individual instance failures.

## Constraints and Requirements

- No hardcoded secrets: All credentials and configuration must be managed through environment variables
- Reproducible deployment: The entire stack must be deployable to GitHub Pages with clear deployment procedures
- Full-book and selected-text querying: The RAG system must support both comprehensive book-wide queries and specific text selection queries
- Top-k semantic retrieval: Implement semantic search with configurable k-value for result ranking
- Performance standards: API responses must be under 2 seconds for 95% of requests
- Security: Proper authentication and authorization for all backend endpoints

## Development Workflow

- All changes must follow the red-green-refactor cycle with comprehensive testing
- Pull requests require specification alignment verification before merging
- Code reviews must validate adherence to architectural principles
- Automated tests must pass before deployment
- Documentation must be updated alongside code changes
- Version control follows semantic versioning with clear changelog maintenance

## Governance

This constitution governs all development activities for the technical book RAG project. All team members must comply with these principles. Amendments require explicit approval and must be documented with clear justification. Code reviews and CI/CD pipelines will enforce compliance with these principles.

**Version**: 1.0.0 | **Ratified**: 2026-02-18 | **Last Amended**: 2026-02-18
