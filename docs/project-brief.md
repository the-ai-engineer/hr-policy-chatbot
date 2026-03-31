# Project Brief: HR Policy Chatbot

These are the rough notes for what we're building. Messy, incomplete, thinking out loud. This is how real projects start.

---

## The problem

A company's HR team is drowning in repetitive questions. Employees keep asking the same things: how much time off do I have, what's the sick leave policy, how do I request parental leave, what's the dress code. HR staff are spending hours every day answering questions that are already documented in policy documents.

They want an internal chatbot. Employees ask a question, the bot searches the HR policy documents, and gives an accurate answer with a citation back to the source.

## Who is it for

Internal employees at one company. This is an internal tool, not a public-facing product. It runs on the company's internal network at something like hr-support.mycompany.com. No public access. If you're on the internal network, you can use it.

## What it should do

- Upload HR policy documents (PDF and markdown)
- Process them: chunk into pieces, generate embeddings, store in a vector database
- Chat interface: employee types a question, gets an answer
- Answers cite which policy document and section the answer came from
- Conversation history so follow-up questions work

## What it should NOT do

- No authentication (internal network only)
- No fine-tuning or custom model training
- No multi-company support
- No real-time document syncing (HR uploads manually when policies change)
- No file types beyond PDF and markdown for v1
- No editing or creating policies - read only

## Example interactions

```
Employee: "How many days of annual leave do I get?"

Bot: "Full-time employees receive 25 days of annual leave per year,
     plus 8 public holidays. Part-time employees receive a pro-rata
     allocation based on their contracted hours.
     [Source: Leave Policy, Section 2.1]"

Employee: "What about if I've only been here 3 months?"

Bot: "During your first year of employment, annual leave is accrued
     at a rate of 2.08 days per month. After your probation period
     (typically 3 months), you may take accrued leave with manager
     approval.
     [Source: Leave Policy, Section 2.3]"
```

## Open questions

- What tech stack?
- What embedding model?
- How to chunk documents?
- How many chunks to retrieve per query?
- How to handle follow-up questions?
- How to handle policy updates?
