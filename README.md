# Soil Policy Analysis Template

This repository is a lightweight research-design template for adapting an
evidence-grounded agricultural policy extraction workflow to soil-policy
analysis. It intentionally contains **no executable LLM pipeline, document
parser, RAG system, knowledge graph, data, or API credentials**.

## Purpose

The template helps a research team define, before implementation:

1. what counts as a soil policy;
2. which soil objectives, threats and instruments should be coded;
3. which fields should be extracted from policy documents;
4. how every coded claim should be linked to local documentary evidence; and
5. how human reviewers should treat missing, ambiguous and conflicting claims.

## Repository structure

```text
config/
  soil_policy_ontology.v1.json       Controlled policy vocabulary
prompts/
  soil_policy_analyst_system.txt     Analyst role and general safeguards
  soil_policy_extraction.txt         Main structured-extraction instructions
  soil_policy_page_reading.txt       Page/table transcription instructions
  soil_policy_review.txt             Human/LLM quality-review checklist
schema/
  soil_policy_record.schema.json     Target record structure
docs/
  adaptation_checklist.md            Decisions required before implementation
  coding_guidelines.md               Inclusion, exclusion and evidence rules
```

## Recommended adaptation sequence

1. Define the jurisdiction, policy system and time period.
2. Decide whether the corpus covers soil-specific policies only or also
   agricultural policies with explicit soil mechanisms.
3. Revise `config/soil_policy_ontology.v1.json` with domain experts.
4. Revise the schema to match the research questions and available evidence.
5. Align all prompts with the ontology and schema.
6. Create a manually coded gold-standard sample before automating extraction.
7. Pilot on diverse documents, including negative and ambiguous examples.

## Key differences from a GHG-policy workflow

- A general environmental or climate statement is not automatically a soil
  policy.
- A soil-management practice must not be treated as an observed soil outcome.
- Policy targets, implementation outputs and measured outcomes must remain
  separate.
- Soil indicators require explicit units, depth, sampling basis, spatial scope
  and measurement method where available.
- Carbon sequestration is one soil-policy dimension, not a synonym for soil
  health.
- Expected co-benefits for GHG mitigation, water, biodiversity or production
  must be distinguished from reported effects.

## Evidence rule

Every positive or uncertain classification must include a concise evidence
quotation and a source locator. Missing information must remain `null` or an
empty list. The extraction process must not convert plausible agronomic effects
into policy claims unless the supplied source explicitly supports them.

## Not included

- source documents or extracted datasets;
- model-provider configuration or API keys;
- Python execution code;
- OCR/OXR or document-ingestion tools;
- RAG, embeddings, vector stores or query interfaces;
- knowledge-graph construction or visualisation.

## Provenance

This template was derived conceptually from the research design of the
`ghgStorylinesRAG` project. Reuse should acknowledge that project and any other
software or conceptual sources adopted during later implementation.
