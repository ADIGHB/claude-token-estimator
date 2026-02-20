---
name: claude-token-estimator
description: Estimate token usage, context load, and cost before executing a task. Includes model recommendation, confidence scoring, optional sensitivity analysis, optional break-even comparison, and CSV export.
---

# Claude Token Estimator

A structured cost forecasting and model optimization skill for Claude.

# CORE WORKFLOW

Follow these steps strictly.

## 1. Input Token Estimation

- 1,000 words ≈ 1,300–1,500 tokens
- Plain text ≈ 4 characters per token
- 100 KB ≈ 25,000 tokens
- Code density ≈ 1.5× text
- Markdown adds 10–20% overhead

If iterative refinement expected:
Multiply input tokens by 1.3–2.0.

If multi-document:
Sum inputs.

## 2. Output Token Estimation

Short: 500–1,000 tokens  
Structured: 1,000–3,000 tokens  
Long-form: 3,000–10,000+ tokens  
Heavy reasoning: Add 20–50%

## 3. Tool Overhead

Simple: +500  
Multi-step: +2,000–5,000  
Complex agentic: +5,000–15,000  

## 4. Context Window Safety

Total Context = Input + Output + Tool Overhead

If usage exceeds 60% of context window, prefer larger model.

Reason: Remaining 40% provides margin for system prompts, reasoning, and output buffering.

## 5. Cost Calculation

Estimated Cost =
(Input Tokens × Input Price per Token) +
(Output Tokens × Output Price per Token)

## 6. Confidence Bands

Very Low (<40%)  
Low (40–60%)  
Medium (60–80%)  
High (80–100%)  

Never assign 100%.

## 7. Sensitivity Analysis (Permission Required)

Vary output, iterations, and tool overhead.

## 8. Break-Even (Permission Required)

Compare cost per 1M tokens and scale thresholds.

## 9. Model Recommendation

Select lowest-cost safe model.

## 10. CSV Export (Permission Required)

Output clean CSV per spreadsheet-format.md.

# GUARDRAILS

- Never fabricate pricing
- Never auto-switch models
- Never auto-run optional analyses
