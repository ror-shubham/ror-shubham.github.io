---
date: '2024-09-01T00:00:00+05:30'
title: 'AI Account Summary — 20K+ Daily AI Summaries'
summary: 'Built an AI engine generating 20,000+ account summaries daily with buying stage predictions, intent insights, and next-action recommendations.'
tags: ['Generative AI', 'Python', 'Django', 'OpenAI', 'React', 'TypeScript', 'LLM']
categories: ['AI Projects']
ShowToc: true
TocOpen: true
weight: 4
---

The AI Account Summary engine was one of the highest-impact projects I worked on at 6sense. It transformed raw data lakes of account activity into concise, actionable intelligence that sales reps could use instantly.

## The Problem

Sales reps at 6sense's enterprise customers were drowning in data. Each account had dozens of signals — web visits, content downloads, keyword research trends, technographic changes, and more. Reps needed to sift through all of this before every call or meeting.

We needed a system that could:
- Distill hundreds of data points into a single, readable summary
- Predict buying stages and recommend next actions
- Map personas within target accounts
- Scale to 20,000+ summaries per day without breaking the bank on LLM costs

## Architecture

### Data Pipeline
The system ingested multiple data streams:
- **Activity Recaps**: Recent web visits, content engagement, and ad interactions
- **Intent Signals**: Keyword-level research activity mapped to buying intent
- **Buying Stage Predictions**: ML-model outputs indicating where the account sits in the purchase journey
- **Technographic Data**: Known tech stack, recent changes, and competitive displacement signals

### Summary Generation
Each summary was structured into actionable sections:
1. **Executive Overview** — What happened with this account recently?
2. **Intent Insights** — What topics are they researching?
3. **Buying Stage** — Where are they in the journey?
4. **Persona Mapping** — Who are the key decision-makers engaging?
5. **Recommended Next Actions** — What should the rep do next?

### Performance Optimization

Generating 20K+ summaries daily with LLM calls is expensive. Two key optimizations made this feasible:

- **Response Caching**: Identical or near-identical data inputs produce cached summaries. We implemented a smart hashing mechanism that creates cache keys from the data fingerprint, so accounts with unchanged signals serve cached responses
- **Async Processing**: Summary generation runs asynchronously via task queues. Reps see a loading state briefly, then the summary renders — but the LLM isn't blocking any request threads

These optimizations reduced redundant LLM calls by ~60% and brought average latency down significantly.

## Frontend

The summary UI was built in React + TypeScript, designed for scannability:
- Collapsible sections for each summary component
- Visual indicators for intent signal strength
- Inline actions (schedule follow-up, add to cadence, share with team)
- Responsive design for both desktop dashboards and mobile views

## Impact

| Metric | Result |
|---|---|
| **Daily Volume** | 20,000+ summaries |
| **Pipeline Impact** | 11% increase in Stage 0 pipeline |
| **LLM Cost Reduction** | ~60% via caching |
| **Data Sources** | 5+ integrated signal types |

## Tech Stack

`Python` · `Django` · `OpenAI API` · `React` · `TypeScript` · `Celery` · `Redis` · `PostgreSQL`

---

*This project showed me that the real challenge in AI engineering isn't the model — it's the infrastructure around it. Caching, async processing, and data pipeline design determine whether an AI feature is a demo or a product.*
