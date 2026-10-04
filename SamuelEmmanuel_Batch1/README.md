# AI Engineering Training --- Lab Assignments

A record of my practical work, design decisions, and learning progress
throughout the AI Engineering training.

## Day 4 — Prompt-Based Text Classifier

**Goal:** Build and evaluate a prompt-based classifier that routes customer support messages into one of four categories: `billing`, `technical`, `account_access`, or `other`.

**Work completed:**
- Set up a Google Colab notebook and loaded a Qwen instruction model using Hugging Face Transformers.
- Created a fixed, hand-labelled set of 10 test messages.
- Compared prompt versions: a basic instruction (v1), role and label definitions with JSON output rules (v2), few-shot examples (v3), and an optional reason-then-label version (v4).
- Evaluated classification accuracy, output parseability, and consistency across repeated sampled runs.
- Recorded prompt comparisons in a playbook and reflected on the strongest improvement and hardest test case.

**Success target:** At least 9/10 correct classifications and 10/10 parseable outputs for the best prompt, with the consistency check recorded.

**Notebook:** [Open Day 4 in Google Colab](https://github.com/Clintjeez/Tech4Youth-AI-Training/tree/main/SamuelEmmanuel_Batch1/Day4_Assignment)

------------------------------------------------------------------------

## Day 5 --- Design an AI System on Paper

**Goal:** Design the architecture for a customer support assistant that categorizes incoming tickets, drafts replies, and escalates uncertain or sensitive cases to a human agent.

**System design:**
- **Interface:** Web-based support dashboard connected to the support inbox.
- **Orchestration:** Backend code cleans ticket text, assembles prompts, validates model output, applies business rules, retries failures, and routes tickets.
- **Models:** `text-embedding-3-small` for semantic retrieval and `GPT-4.1 mini` for classification and reply drafting.
- **Data:** PostgreSQL with pgvector for ticket records and similarity search.
- **Operations:** Logging, confidence checks, monitoring, and a human-review queue.

**Workflow:** Receive a ticket, remove unnecessary formatting and personal identifiers, retrieve three similar resolved tickets, generate a category, confidence score, and suggested reply in JSON, validate the result, then queue an eligible high-confidence draft or route the ticket for human review.

**Key design decisions and safeguards:**
- Target at least 90% correct categorization on a test set.
- Use a confidence threshold of 0.8 alongside business rules before a draft can proceed through the approved sending workflow.
- Retry malformed output or transient API failures, then send unresolved cases to human review.
- Store ticket-processing data for 90 days, subject to the support team's retention requirements; restrict access to authorized agents and administrators.

**Diagram:** [Open the Day 5 worksheet & Excalidraw design](https://github.com/Clintjeez/Tech4Youth-AI-Training/tree/main/SamuelEmmanuel_Batch1/Day5_Assignment)

------------------------------------------------------------------------


## Ongoing Updates

