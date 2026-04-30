# Hakim PRD

## Document status
- Product: Hakim
- Version: v1 PRD
- Distribution pivot: WhatsApp-first
- Backend posture: channel-agnostic
- Primary persona: legal associates
- Core workflow: fast research and deep case analysis
- Core legal sources: Pasal.id and Exa
- Source hierarchy: Pasal.id is primary legal authority; Exa provides supporting context
- Phase 1 inference: Groq only
- Phase 1 backend: Supabase + pgvector

## 1. Product summary

Hakim is an AI legal research product for Indonesian legal associates and legal departments. It helps teams process large, time-consuming cases faster by turning legal questions, case histories, and comparison tasks into grounded, source-verified answers.

Hakim is optimized for professional legal research, not general consumer Q&A. The product supports two working modes:

- Fast Research: single-pass triage for quick signal extraction and immediate answer shaping
- Deep Report: multi-pass synthesis for broader analysis, contradiction resolution, and deeper legal reasoning

Hakim is distributed through WhatsApp first, but the backend is designed to remain channel-agnostic so the same product logic can later power other interfaces such as web, Telegram, or internal tools.

## 2. Core operating standards

These are the operating standards for the Hakim build:

### 2.1 Source hierarchy
- Use Pasal.id as the primary legal authority.
- Use Exa as supporting context, corroboration, and breadth expansion.
- When Pasal.id and Exa differ, Pasal.id governs legal grounding unless a higher-authority source is explicitly identified and verified.
- Legal conclusions should never rely on Exa alone when a statutory or regulatory answer is available from Pasal.id.

### 2.2 Citation provenance layer
- Every answer must be backed by an evidence bundle.
- The evidence bundle should preserve:
  - source name
  - source type
  - cited excerpt or span
  - jurisdiction / authority level
  - retrieval timestamp
  - query or retrieval intent
  - confidence or relevance note
- The generated answer must be traceable back to the bundle.
- A post-generation verifier must inspect the answer against the evidence bundle before the response is finalized.
- The verifier should check:
  - citations exist for each material claim
  - quoted or paraphrased legal text matches source meaning
  - source hierarchy was respected
  - unsupported claims are flagged or removed
  - the final response remains consistent with retrieved evidence

### 2.3 Research mode logic
- Fast Research is a single-pass triage mode.
- Fast Research should:
  - identify the legal issue
  - retrieve the most relevant authority quickly
  - extract the minimum grounded answer needed for triage
  - stop once the answer is sufficiently supported
- Deep Report is a multi-pass synthesis mode.
- Deep Report should:
  - broaden the source set
  - compare authorities, exceptions, and related doctrine
  - reconcile contradictions
  - produce a structured legal memo with stronger reasoning depth
  - run the verifier after synthesis before final output
- The system should route to Fast Research when speed and early signal matter most, and to Deep Report when completeness, nuance, or risk is higher.

## 3. Product scope

The initial build should support:
- legal question intake
- issue classification
- source retrieval from Pasal.id and Exa
- evidence bundle generation
- verifier pass before final output
- fast triage and deeper research workflows
- case context retention in Supabase + pgvector

## 4. Technical architecture

- Channel delivery: WhatsApp first
- Backend posture: channel-agnostic
- Inference for Phase 1: Groq only
- Database and memory layer: Supabase + pgvector
- Retrieval sources: Pasal.id primary, Exa supporting
- Response pipeline:
  1. intake
  2. source retrieval
  3. evidence bundle assembly
  4. research mode execution
  5. post-generation verification
  6. final answer delivery

## 5. Research workflow

### Fast Research
Fast Research is optimized for:
- quick legal triage
- one-shot issue answering
- first-pass statute lookup
- rapid user feedback

Fast Research behavior:
- run a single retrieval pass
- prefer the highest-authority source that answers the issue
- keep the answer concise
- surface uncertainty early if the issue is under-supported

### Deep Report
Deep Report is optimized for:
- complex matters
- conflicting authority
- comparative issue analysis
- deeper factual or doctrinal review

Deep Report behavior:
- run multiple retrieval passes
- expand across complementary authorities
- synthesize findings into a structured report
- verify the final answer against the evidence bundle

## 6. Evidence bundle requirements

Each research session should produce an evidence bundle that can be reused for auditability and future follow-up.
The bundle should include:
- retrieved source records
- highlighted relevant spans
- source ranking rationale
- source hierarchy notes
- verification status
- unresolved questions, if any

## 7. Operating principles

- Be grounded before being expansive.
- Prefer primary authority over secondary context.
- Verify before finalizing.
- Use the fastest mode that safely solves the user\u2019s problem.
- Escalate from Fast Research to Deep Report when needed.
- Preserve traceability so every answer can be audited.

## 8. Initial delivery goals

- Fast, grounded triage for common legal questions
- Reliable legal citations with provenance
- Better handling of nuanced or conflicting authority
- Reusable evidence bundles for internal audit and follow-up
- A clean path from intake to verified answer

---
*Core operating standards for the Hakim build.*
*Last Updated: April 30, 2026*