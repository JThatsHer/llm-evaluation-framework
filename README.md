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

This evaluation demonstrates how LLM outputs may appear coherent while containing factual inaccuracies. Structured review frameworks are essential to improving AI reliability.
