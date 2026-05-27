# Project Brief: HR Policy Chatbot

## Overview

Build a small internal Q&A application that helps employees answer HR policy questions.

Employees should be able to open a web page, ask a question in plain English, and receive a concise answer grounded in company policy documents. The answer must show which document or documents were used. If the documents do not contain the answer, the system should say so instead of guessing.

This is the sample project for the Agentic Engineer course. The point is not to build a complex production RAG platform. The point is to practice an end-to-end agentic software workflow: understanding a brief, writing a spec, breaking work into tasks, implementing with an AI coding agent, testing, reviewing, and deploying.

## Scenario

The HR team at a mid-sized company answers the same questions every week:

- How much annual leave do I get?
- What should I do if I am sick for more than a few days?
- Can I work remotely from another location?
- How do expenses get approved?
- What parental leave am I eligible for?

The answers already exist in policy documents, but employees do not always know where to look. HR wants a simple tool that answers common questions accurately and points employees back to the source policy.

## Target Users

The primary users are internal employees who want quick answers to policy questions.

The secondary users are HR staff who want to reduce repeated questions while keeping answers consistent with the written policies.

## Product Goal

Create a full-stack chatbot-style Q&A system with:

- a Python backend
- a Next.js frontend
- simple markdown document loading
- an LLM call that answers from the loaded documents
- clear source attribution in every supported answer

The application should feel like a useful internal tool, not a throwaway demo.

## Core Behaviour

When an employee asks a question, the system should:

1. Load the approved HR policy documents.
2. Send the employee question and relevant policy content to the model.
3. Answer using only the provided policy content.
4. Include the source policy document names used.
5. Say it does not know when the answer is not in the documents.
6. Refuse off-topic questions politely.

## Document Scope

Use simple markdown policy files checked into the repository during the build.

The first version should use a small set of HR policies, such as:

- annual leave
- sickness absence
- parental leave
- remote working
- expenses and travel

The first version should load the documents directly from disk. Do not add embeddings, vector databases, chunking pipelines, rerankers, document upload, or a complex RAG architecture.

## User Experience

The frontend should provide:

- a clean internal support-style page
- a chat or question input
- a few example prompts
- an answer area
- visible source attribution
- useful empty, loading, error, unsupported-question, and off-topic states

The UI should be clear and professional. It should help employees ask policy questions quickly without needing to understand how the AI works.

## Backend Expectations

The backend should:

- expose an API endpoint for asking a question
- load markdown policy documents from the repository
- keep the model API key server-side
- validate request input
- return a structured response containing the answer and sources
- handle unsupported and off-topic questions predictably
- include focused tests for document loading and answer API behaviour

## Frontend Expectations

The frontend should:

- call the backend API
- show loading and error states
- render answers and sources clearly
- make common example questions easy to try
- avoid exposing secrets in browser code
- include focused tests or browser verification for the main user flow

## Non-Goals

Do not build these in the course project unless they are introduced later as an explicit extension:

- vector search
- embeddings
- document upload
- admin dashboards
- authentication
- employee-specific policy entitlements
- conversation memory beyond the current question
- analytics dashboards
- Slack or Teams integrations
- production-grade evaluation pipelines
- multi-company or multi-tenant support

## Example Interactions

```text
Employee: How many days of annual leave do I get?

Assistant: Full-time employees receive 25 days of annual leave per year, plus public holidays. Part-time employees receive a pro-rata allowance based on contracted hours.

Sources: annual-leave-policy.md
```

```text
Employee: What happens if I am off sick for more than a week?

Assistant: If sickness absence lasts more than seven calendar days, you need to provide a fit note and keep your manager updated. A return-to-work conversation may be required when you come back.

Sources: sickness-absence-policy.md
```

```text
Employee: Can you help me pick a holiday destination?

Assistant: I can only answer questions about the HR policy documents available to me. Please ask a question about company policy.

Sources: none
```

## Suggested Technical Shape

The course will decide and implement the exact structure, but the intended direction is:

- Python backend, likely FastAPI
- Next.js frontend with TypeScript
- markdown policy documents in the repository
- direct document loading from disk
- one server-side LLM integration
- tests for the backend logic
- browser verification for the main frontend flow
- deployment with environment variables and live smoke checks

## Success Criteria

By the end of the course, the project should have:

- a working local full-stack application
- a Python backend that loads markdown HR policy documents
- a Next.js frontend for asking questions
- answers grounded in the provided policies
- source policy names shown with supported answers
- clear behaviour for unsupported and off-topic questions
- tests or checks that prove the core path works
- a documented deployment path
- a deployed version that has been smoke-tested

## Teaching Boundary

This project contains an AI feature, but it is not an advanced AI architecture course.

Keep the AI flow intentionally simple so the course can focus on professional software delivery with agents: context, specs, tasks, implementation, tests, review, git, pull requests, deployment, and iteration.
