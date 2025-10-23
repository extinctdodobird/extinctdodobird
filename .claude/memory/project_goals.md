# Project Goals

## Mission
Win or achieve top placement in **ARC Prize 2025** by building a system that demonstrates true abstract reasoning and generalization.

## Timeline
- **Start Date:** October 23, 2025
- **Submission Deadline:** November 3, 2025 (hard deadline)
- **Target Completion:** October 31, 2025 (safety buffer)
- **Daily Commitment:** 8+ hours/day

## Success Criteria

### Minimum Viable Goal
- **Top 10%** placement on Kaggle leaderboard
- **40%+ accuracy** on private evaluation set
- Working submission that completes within time/compute limits

### Stretch Goal
- **Top 3** placement
- **53%+ accuracy** (matching 2024 winners)
- Elegant, understandable solution

### Grand Prize (Aspirational)
- **85%+ accuracy** on private evaluation set
- **$2.50/task efficiency** or better
- **$600,000 prize**

## Core Philosophy

### Follow Chollet's Vision
- Build systems that **reason**, not memorize
- Use **discrete program synthesis**, not pure neural pattern matching
- Demonstrate **compositional generalization**
- Focus on **abstraction** over scale

### Approach
**Primary:** Discrete program search + Domain Specific Language (DSL)
**Secondary:** Small models for fallback (if fits compute budget)
**Forbidden:** External API calls, pure LLM approaches

## Team Structure
- **Human (extinctdodobird):** Project lead, strategist, context engineer
- **AI (Claude):** Coding assistant, execution partner, knowledge resource
- **Collaboration Model:** "Duo-preneur" - human leads, AI executes

## Resources Available
- **Compute:** Kaggle 4xL4 GPUs (96GB, 30hrs/week) + Google Colab Pro
- **Budget:** Minimal ($0-500 if needed for additional resources)
- **Skills:** Beginner Python/ML (human), expert coding (AI)
- **Time:** 8 days of focused work

## What We're Building
A **pure reasoning engine** that:
1. Analyzes ARC task examples to understand the transformation pattern
2. Searches through a space of compositional programs (DSL)
3. Tests candidate programs against training examples
4. Selects and applies the best program to test inputs
5. Outputs predictions in Kaggle's pass@2 format

## Why We'll Win
- **Focus on fundamentals:** DSL + search (proven 2020-2024)
- **Disciplined execution:** Structured workflow, clear milestones
- **Chollet-aligned approach:** Building what the benchmark actually tests
- **Efficient partnership:** Human strategy + AI implementation speed
