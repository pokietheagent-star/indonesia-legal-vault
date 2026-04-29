---
title: PLAYBOOK
source: repository
folder: /
---

# PLAYBOOK

This file is the operating playbook for Indonesian legal research in this vault.

## Non-negotiables

- Use Pasal.id first for any statute or regulation lookup.
- Use Exa second, only after the governing rule is identified in Pasal.id or when external context is needed to explain implementation, enforcement, or institutional practice.
- Never finalize analysis from Exa alone when the question turns on black-letter law.
- Separate the statutory duty from the observed practice.
- Treat lower-level instruments as subordinate to their parent authority and check delegation carefully.

## 1) Strategic Workflow: Pasal-id + Exa for Institutional Failure Analysis

Use this sequence whenever the issue is not just "what does the law say?" but "why does the institution still fail in practice?"

### Step 1: Identify the statutory duty in Pasal.id

Start with the governing rule in Pasal.id and extract:

- the legal subject or duty holder;
- the exact obligation, prohibition, authority, or standard;
- the triggering condition;
- deadlines, procedure, sanctions, or exceptions;
- the regulation status of the source;
- any transitional clause or implementing mandate.

Write the duty as a clean rule statement before doing anything else.

### Step 2: Translate the duty into an implementation question

Ask:

- Who is supposed to implement this duty?
- What institution, regulator, company, or local government is responsible?
- What evidence would show compliance in the real world?
- What would failure look like operationally?

### Step 3: Use Exa to find the law in the wild

Use Exa for external evidence that shows how the rule is actually implemented or ignored, such as:

- regulator guidance and FAQs;
- agency websites and public notices;
- enforcement statistics or complaints portals;
- procurement, licensing, HR, or privacy policies;
- court reporting and public investigations;
- news coverage of delay, capture, under-enforcement, or workarounds.

### Step 4: Compare duty vs. practice

Map the gap in a simple structure:

- legal duty;
- stated institutional process;
- observed behavior;
- mismatch;
- institutional failure point;
- consequence for rights, compliance, or enforcement.

### Step 5: Name the failure precisely

Prefer exact labels like:

- under-implementation;
- capture;
- procedural bottleneck;
- delegated authority mismatch;
- enforcement drift;
- documentation gap;
- selective compliance;
- weak sanctions;
- ambiguous supervision.

Do not blur black-letter law with institutional practice. Keep the two layers separate, then connect them.

## 2) Hierarchy Search Protocol

Use a top-down search path and do not start from the lowest instrument unless the user explicitly asks for a local rule first.

### Search order

1. UU / PP
2. Permen / Perban
3. Perda

### Core logic

- Start with the parent authority first.
- Identify whether the lower instrument is an implementing rule, delegated rule, or local adaptation.
- Check whether the lower rule stays inside the scope of the parent delegation.
- Check whether the lower rule creates new obligations, sanctions, exclusions, or procedures that the parent did not authorize.
- Check whether the lower rule conflicts with higher law, exceeds authority, or quietly narrows rights.

### Delegation breach checklist

Flag a possible breach when a lower instrument:

- creates substantive rules without a clear delegation basis;
- expands or narrows rights beyond the parent rule;
- adds sanctions or burdens that the parent did not authorize;
- changes who may act, decide, or enforce;
- imposes conditions that look policy-based rather than delegated;
- conflicts with the text, purpose, or hierarchy of the parent rule;
- uses vague technical language to mask a substantive change.

### Output format for hierarchy checks

Always report:

- Parent rule:
- Lower rule:
- Delegation basis:
- Scope match or mismatch:
- Breach risk:
- Practical effect:

If no delegation breach exists, say so clearly and explain why.

## 3) Pro Prompt Templates

These templates are built for source-grounded legal work. Replace bracketed placeholders before use.

### A. Labor: severance, acquisition rights, terminations

Use this prompt when the matter involves severance, transfer of undertaking, acquisition rights, dismissal, or termination procedure.

Prompt:
You are working in Indonesia legal mode.

Task: analyze the labor issue using Pasal.id first, then use Exa only for implementation and enforcement context.

Facts:
[INSERT FACTS]

Question:
[INSERT SPECIFIC QUESTION]

Required method:
1. Identify the governing statutory duty in Pasal.id.
2. Track the hierarchy from UU/PP down to any Permen or Perda if relevant.
3. Identify whether the issue is severance, acquisition rights, termination, or a mixed employment transition issue.
4. State the worker-right / employer-duty / procedural-duty / remedy structure.
5. Use Exa only to find real-world implementation gaps, disputes, regulator practice, or public guidance.
6. Flag any delegation breach, inconsistent implementing rule, or procedural gap.

Output required:
- rule statement
- hierarchy map
- practical risk
- implementation gap
- recommended next research step

### B. Anti-corruption: regulatory capture, oversight failure

Use this prompt when the issue is about anti-corruption, oversight collapse, agency capture, or weak supervision.

Prompt:
You are working in Indonesia legal mode.

Task: analyze the anti-corruption problem as an institutional failure analysis, not just a black-letter review.

Facts:
[INSERT FACTS]

Question:
[INSERT SPECIFIC QUESTION]

Required method:
1. Find the statutory duty, supervisory duty, or prohibition in Pasal.id first.
2. Identify the institution that is legally supposed to supervise, approve, audit, disclose, or sanction.
3. Map the delegated authority chain and check whether any lower rule dilutes supervision or widens discretion without authorization.
4. Use Exa to find the law in the wild: procurement patterns, public reporting, watchdog coverage, enforcement delays, audit findings, or signs of capture.
5. Distinguish between a legal gap, a supervision gap, and a political or institutional failure.

Output required:
- governing rule
- responsible institution
- delegation chain
- capture / oversight failure theory
- real-world evidence
- legal significance

### C. Privacy: SaaS compliance, data controller liability, 2022 law window

Use this prompt when the issue is privacy compliance, SaaS vendor obligations, controller liability, processor liability, or transition analysis around the 2022 law window.

Prompt:
You are working in Indonesia legal mode.

Task: analyze privacy compliance under Indonesia law with Pasal.id as the primary source and Exa as the secondary source for implementation reality.

Facts:
[INSERT FACTS]

Question:
[INSERT SPECIFIC QUESTION]

Required method:
1. Identify the governing privacy duty in Pasal.id.
2. Check whether the relevant rule is a pre-2022 framework, the 2022 law window, or a transitional / implementing issue.
3. Separate controller obligations, processor obligations, vendor obligations, and liability exposure.
4. If SaaS is involved, identify the data flow, role allocation, and contractual compliance gap.
5. Use Exa to find public privacy notices, vendor terms, enforcement signals, or market practice that show the law in the wild.
6. Highlight any mismatch between promised compliance and actual operational controls.

Output required:
- statute and status
- role mapping
- transition or 2022 window note
- SaaS compliance gap
- liability exposure
- evidence from the wild

## 4) Working notes for the vault

- Pasal.id resolves what the law is.
- Exa resolves how the law behaves in the wild.
- The playbook should always preserve that separation.
- When a matter becomes a reusable file, keep the analysis source-grounded, procedural, and auditable.
- If Exa is used in a matter file, record the queries or sources checked and the fallback rationale in the end section of that file.
