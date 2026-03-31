# HR Policy Chatbot

An internal chatbot that answers employee questions about company policies. Built step by step using spec-driven development with AI coding agents.

This is the course project for [The Agentic Engineer](https://skool.com/aiengineer). Each lesson in the course adds a piece to this project, from rough notes to deployed application.

## The Problem

A company's HR team is drowning in repetitive questions. Employees keep asking the same things: how much time off do I have, what's the sick leave policy, how do I request parental leave. HR staff are spending hours every day answering questions that are already in the policy documents.

This chatbot searches HR policy documents and gives accurate answers with citations back to the source.

## How It Works

1. HR uploads policy documents (PDF, Markdown)
2. Documents are chunked, embedded, and stored in a vector database
3. Employee asks a question through the chat interface
4. The system retrieves relevant document chunks and generates an answer with citations

## Tech Stack

- **Backend:** Python, FastAPI, uv
- **Database:** PostgreSQL with pgvector
- **AI:** Claude API for generation, embeddings for retrieval
- **Frontend:** Next.js
- **Deployment:** Docker Compose

## Course Progression

This project is built across the course modules:

| Module | What happens |
|--------|-------------|
| Module 2: Spec-Driven Development | Requirements, design, and task breakdown |
| Module 3: Implementation and Quality | Build, add hooks, review, and ship |
| Module 4: The Full Build | Watch the complete end-to-end recording |

## Getting Started

The starting point is the project brief in `docs/project-brief.md`. This is the raw client problem before any planning.

```bash
git clone https://github.com/the-ai-engineer/hr-policy-chatbot.git
cd hr-policy-chatbot
```

Follow along with the course lessons to turn these rough notes into a working application.
