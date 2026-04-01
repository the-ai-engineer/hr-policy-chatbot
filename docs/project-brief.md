# Project Brief: HR Policy Chatbot

These are the rough notes from the client. Messy, incomplete, thinking out loud. This is how real projects start.

---

## The problem

Our HR team is drowning in repetitive questions. Employees keep asking the same things: how much time off do I have, what's the sick leave policy, how do I request parental leave, what's the dress code. HR staff are spending hours every day answering questions that are already documented in our policy documents.

We've got about 12-15 policy documents covering everything from annual leave to expenses to the disciplinary process. They're detailed, well-structured, and they have the answers. But nobody reads them. People just message HR instead.

We want an internal chatbot. Employee asks a question, the bot gives an accurate answer and tells them exactly where it came from -- which document and which section. So if someone asks "how many days off do I get?" the bot should say "25 days" and point them to the Leave Policy, Section 2.1.

## Who is it for

Internal employees at one company. This is an internal tool, not a public-facing product. It runs on the company's internal network. No public access. If you're on the internal network, you can use it.

Around 500 employees. Mostly office-based with some remote workers.

## What it should do

- Let HR upload policy documents (we use PDF and markdown)
- Employee types a question in a chat interface, gets an answer
- Answers must cite which policy document and section the answer came from
- Follow-up questions should work ("what about for part-time employees?")
- Conversation history so the bot has context

## What it should NOT do

- No authentication needed (internal network only, everyone has access)
- No editing or creating policies -- this is read-only
- No real-time syncing with policy changes (HR will re-upload when documents change)
- No multi-company support -- this is just for us
- No file types beyond PDF and markdown for now

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

```
Employee: "I need to take time off for a funeral"

Bot: "You are entitled to up to 5 days of paid compassionate leave
     following the death of an immediate family member (spouse,
     partner, parent, child, or sibling). Additional unpaid leave
     may be granted at your manager's discretion.
     [Source: Leave of Absence Policy, Section 4.2]"
```

```
Employee: "What happens if I'm sick for more than a week?"

Bot: "If you are absent for more than 7 calendar days, you must
     obtain a fit note from your GP and submit it to your line
     manager. You should continue to provide fit notes to cover
     the duration of your absence. A return-to-work meeting will
     be held on your first day back.
     [Source: Sickness Absence Policy, Section 5.1]"
```

## What success looks like

Upload our policy documents. Ask questions about time off, sick leave, benefits, expenses, dress code. Get accurate answers that cite the correct policy and section. Follow-up questions work. The whole thing runs on our internal infrastructure.

## Open questions

- What tech stack?
- How should we handle follow-up questions?
- How do we deal with questions that span multiple policies?
- How do we handle policy updates?
- Can employees ask about things not covered by policy? How should the bot respond?

## Sample documents

A set of sample HR policy documents are provided in the `sample-docs/` folder. These represent a realistic set of policies for a mid-size company. Use these for development and testing.
