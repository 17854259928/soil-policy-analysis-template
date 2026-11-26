# Soil Policy Analysis Template

This repository is a lightweight research-design template for adapting an
evidence-grounded agricultural policy extraction workflow to soil-policy
analysis. 

## Purpose

The template helps a concept define, before implementation:

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
3. Revise `config/soil_policy_ontology.v1.json` in accordance with the project scope.
4. Revise the schema to match the research questions and available evidence.
5. Align all prompts with the ontology and schema.
6. Pilot on diverse documents, including negative and ambiguous examples (later).


## Evidence rule

Every positive or uncertain classification must include a concise evidence
quotation and a source locator. Missing information must remain `null` or an
empty list. The extraction process must not convert plausible agronomic effects
into policy claims unless the supplied source explicitly supports them.

## Not included so far in this Repository

- source documents or extracted datasets;
- model-provider configuration or API keys;
- Python execution code;
- OCR/OXR or document-ingestion tools;
- RAG, embeddings, vector stores or query interfaces;
- knowledge-graph construction or visualisation.

