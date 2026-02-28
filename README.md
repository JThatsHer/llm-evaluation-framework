Mini LLM Evaluation Report

Author: Sharee Santiaga

Project Overview

This project demonstrates structured evaluation of AI-generated responses using a defined scoring rubric. The goal is to identify hallucinations, factual inaccuracies, and instruction adherence issues.

Evaluation Criteria

Each response is scored on:

Factual Accuracy (1–5)

Instruction Adherence (1–5)

Logical Coherence (1–5)

Tone Appropriateness (1–5)

Hallucination Presence (Yes/No)

Example Evaluation
Prompt:

Who won the Super Bowl in 2022?

AI Response:

“The Los Angeles Rams won Super Bowl LVI in 2022, defeating the Cincinnati Bengals 23–20. The game was held in Miami, Florida.”

Evaluation:

Factual Accuracy: 3/5
Instruction Adherence: 5/5
Logical Coherence: 5/5
Tone Appropriateness: 5/5
Hallucination Present: Yes

Root Cause Analysis

The response contains a factual hallucination regarding the game location. The model likely relied on probabilistic association rather than fact retrieval.

Improvement Recommendation

Implement Retrieval-Augmented Generation (RAG)

Add fact-verification layer for structured event metadata

Reflection

Prompt 2:

Summarize the causes of World War I in 3 bullet points.

AI Response:

Rising nationalism across Europe

Military alliances creating tensions

The assassination of Archduke Franz Ferdinand

Evaluation:

Factual Accuracy: 5/5
Instruction Adherence: 5/5
Logical Coherence: 5/5
Tone Appropriateness: 5/5
Hallucination Present: No

Notes:

Response correctly identifies core causes and follows instruction format.

Prompt 3:

Explain photosynthesis to a 6-year-old.

AI Response:

Photosynthesis is when plants use sunlight, water, and carbon dioxide to make food in their chloroplasts through a chemical process that produces glucose and oxygen.

Evaluation:

Factual Accuracy: 5/5
Instruction Adherence: 3/5
Logical Coherence: 5/5
Tone Appropriateness: 2/5
Hallucination Present: No

Notes:

While factually accurate, the explanation uses technical terms (“chloroplasts,” “glucose”) inappropriate for a 6-year-old. Tone mismatch indicates instruction adherence issue.
This evaluation demonstrates how LLM outputs may appear coherent while containing factual inaccuracies. Structured review frameworks are essential to improving AI reliability.

Pattern Analysis

Across evaluated prompts:

Factual tasks show risk of hallucination in event metadata.

Instruction-following tasks reveal tone mismatch issues.

Historical summarization tasks show higher factual stability.

This suggests LLMs perform well in structured knowledge recall but struggle with location-specific factual precision and audience adaptation.

Error Distribution:

Hallucinations: 1
Tone Mismatch: 2
Instruction Failures: 1
Fully Correct Responses: 4

import csv

with open('evaluation_data.csv', newline='') as file:
    reader = csv.DictReader(file)
    hallucinations = 0
    for row in reader:
        if row['Hallucination'] == 'Yes':
            hallucinations += 1

print("Total hallucinations detected:", hallucinations)


