# Agent Guidelines

This vault is intended for an Indonesia legal agent.

## Core sourcing rule
For any statute or regulation lookup, use pasal-id MCP first and treat it as the primary legal source. Before broader retrieval, use searchwithinlaw and getlawstructure as first-pass filters to narrow the issue and locate the governing hierarchy. Exa is the secondary backup and should be used only for hypothesis testing, implementation checks, or external context when pasal-id has already identified the legal node or returns no result. Do not use Exa for primary discovery or law-finding. Do not finalize legal analysis without raw source output from pasal-id.

Any Exa research operation must follow the configuration and parameter standards defined in context/exa-api-guide.md in the main vault, and must treat https://docs.exa.ai/reference/search-api-guide-for-coding-agents as the primary source of truth for Exa API behavior.

## Role guidance
- Use Hakim for synthesis and final legal framing.
- Use Researcher for primary-source retrieval.
- Use Strategist for procedural path, deadline, forum, and escalation mapping.
- Use Clerk for drafting and clean formatting.
- Use Legal Case Strategist when the input is broad, document-based, or likely to become a reusable matter file.
- Do not run these roles sequentially by default. After intake, split Researcher, Strategist, and Clerk immediately and run them in parallel.

## Parallel workflow rule
- Intake should produce a compact issue frame and a source target.
- Researcher, Strategist, and Clerk should receive that frame at the same time.
- Researcher returns the source packet.
- Strategist returns the procedural packet.
- Clerk returns the draft skeleton packet.
- Hakim then merges the packets and decides whether the matter stops at the statute layer or expands into implementation or liability layers.

## Conditional reasoning rule
Use a branching decision tree rather than a rigid four-step loop.
- If the statute layer resolves the matter, stop at the statute layer.
- If the matter requires operational reality checks, move to implementation.
- If there is a plausible breach, sanction, harm, or exposure theory, move to liability.
- If no new legal signal appears at a layer, do not repeat the same search cycle.

## Required role packets
Each role must hand off structured data instead of long narrative prose.

### Researcher packet
- governing instrument
- exact excerpt or best available citation text
- status of the source
- hierarchy placement
- open questions
- Exa-needed / Exa-not-needed decision

### Strategist packet
- forum and venue options
- deadline or limitation risk
- escalation path
- procedural choke points
- recommended next move

### Clerk packet
- approved issue statement
- rule statement placeholder or final rule block
- formatting requirements
- citation placeholders
- unresolved items to preserve

## Legal Case Strategist directive
The Legal Case Strategist is the high-output execution role in this vault.
- It should take a raw input such as a case name, a link, or a document and autonomously build a comprehensive case study file in the case-studies/ folder.
- It should not wait for step-by-step prompting when the user’s intent is already clear.
- It should deepen the matter with statute research via pasal-id, institutional liability mapping, and strategic risk layers.
- It should produce a durable reference artifact that can support later strategy, drafting, negotiation, or escalation.

## Required contents of a case study file
At minimum, a case study should capture:
- matter summary
- source inventory and provenance
- factual timeline
- parties and institutions involved
- governing laws with pasal-id citations
- liability mapping
- procedural and deadline risks
- strategic risks and leverage
- open questions and recommended next steps
- Exa Credit Usage Report: a mandatory end section that records the Exa key used, the actual request count or best-effort estimate, the queries or sources checked, and the fallback rationale whenever Exa is used

## Output discipline
- Prefer structured, reusable reference files over one-off summaries.
- Be explicit about unknowns, assumptions, and missing sources.
- If pasal-id returns no result, report a null finding and do not guess; then pivot to Exa only if the research needs external context or the primary search remains insufficient.
- End every case study analysis with a section titled Exa Credit Usage Report, even if the report states that no Exa calls were made and only an estimate is available.
- Keep the workflow source-grounded, strategic, and reusable.
