---
date: '2025-04-15T00:00:00+05:30'
draft: false
title: '6sense: From Hackathons to AI Pipelines'
summary: 'A 4.5-year journey scaling frontend architectures, merging acquisitions, building big data pipelines, and shipping Generative AI infrastructure.'
subtitle: 'A 4.5-year journey scaling frontend architectures and building Generative AI infrastructure.'
tags: ['React', 'TypeScript', 'GraphQL', 'Django', 'PySpark', 'Generative AI', 'System Design']
categories: ['Experience']
ShowToc: true
TocOpen: true
weight: 2
---

My 4.5-year tenure at 6sense was a period of massive technical evolution. I joined shortly after the Covid lockdowns and went from building single-page applications in "hackathon mode" to architecting AI systems that process millions of signals daily. 

Here is a deep dive into the systems I built, the architectural decisions my team made, and the challenges we navigated along the way.

### 1. The Foundation: Sales Dashboards (2020 - 2025)
My first major project was building the "Sales Dashboards" app from scratch. This was the starting point for the sales team to get insights and recommendations for their accounts. 

* **The Build:** I was the sole frontend developer responsible for the initial architecture, boilerplate code, CI/CD pipelines, and the foundational reusable component library. 
* **The Stack:** We went with `JavaScript` + `React` + `GraphQL` + `Apollo` on the frontend, backed by `Django`.
* **The Grind:** We spent 3 months in pure hackathon mode, pushing patches until the very last minute before our November 2020 launch. I maintained this frontend for its entire lifecycle until it was officially decommissioned in March 2025 (RIP 🪦).

### 2. The Slintel Merger: Architecting the New Sales Intelligence 
When 6sense acquired Slintel, we faced a massive integration challenge. We needed to merge legacy 6sense Sales Intelligence with Slintel's technology. 

Initially, we considered the easy route—just embedding one app's frontend as an iframe within the other. Instead, as part of a 3-member architect team, we decided to execute a total UI overhaul and introduce a completely new design language. 

* **The Migration:** We migrated from JavaScript to `TypeScript`, utilized the Craco framework, and created new boilerplates to connect with the backend. 
* **The Execution:** It took 5 months, 15 engineers, and a lot of late nights, but the unified Sales Intelligence app was a massive success, eventually contributing over $20M+ in revenue.

### 3. Scaling Big Data & The Outlook Rendering Nightmare
As the platform grew, my responsibilities expanded into the backend, specifically focusing on data pipelines and automated alerting through **SI Alerts**. 

We sent over 90,000 custom intent alerts daily, notifying users of critical signals for their accounts. This project presented two entirely different types of engineering challenges:
1. **The Frontend (Email Clients):** Writing the frontend for this was peculiar because these alerts don't load in browsers; they load in native email clients. Microsoft Outlook uses the MS Word engine to render HTML. Building responsive templates using "ancient" table-based CSS to satisfy Outlook was an absolute trial by fire.
2. **The Backend (PySpark):** The backend was my introduction to big data. We used `Python`, `PySpark`, and `Jinja2` to generate the templates. 

Later, as part of the 6-member SI Tech Pod, I took on ownership of keeping these massive pipelines running—handling PagerDuty, optimizing slow queries, managing `Hive` and `Hadoop` clusters, and successfully optimizing a critical DAG that reduced our daily run time by over 45 minutes. 

### 4. The LLM Era: AI Email Writer & Account Summaries
In my final years at 6sense, my focus shifted entirely to Generative AI product engineering. I was tasked with building systems that didn't just display data, but acted on it.

* **AI Account Summary:** I built an engine that generated 20,000+ summaries daily, taking raw activity recaps, buying stage predictions, and intent insights, and turning them into actionable persona mappings. To make this performant, I implemented heavy response caching and async processing, which drastically reduced redundant LLM calls and latency. 
* **AI Email Writer:** This was the culmination of our intent data. I built an LLM system that processed 1,500+ emails daily, weaving together CRM history, technographics, and behavioral signals. Because of the risks associated with AI-generated outbound emails, I engineered multi-layer guardrails and feedback loops to ensure output safety, alongside a credit-based usage system with org-level quotas. The impact was undeniable: a 42% reply rate and a 29% increase in booked meetings.