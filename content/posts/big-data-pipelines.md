---
date: '2023-10-01T00:00:00+05:30'
title: 'Big Data Engineering: Optimizing PySpark Pipelines at 6sense'
summary: 'Owned critical big data infrastructure handling millions of signals daily. Optimized a core PySpark DAG saving 45 mins/day and retired legacy systems to save $130K annually.'
tags: ['PySpark', 'Hadoop', 'Hive', 'Data Engineering', 'Backend', 'Python']
categories: ['Experience']
ShowToc: true
TocOpen: true
weight: 6
---

As 6sense grew, the volume of intent data, web activities, and technographic signals we processed exploded. The system that built and delivered these insights—specifically the daily SI Alerts pipeline—became my introduction to big data engineering.

## The Challenge

Every day, we generated over 90,000 custom alert emails for customers based on millions of underlying data points. This pipeline was critical; many users literally started their work week by reading these insights. 

When I joined the 6-member SI Tech Pod, our data infrastructure was groaning under the scale:
- Long-running pipelines frequently missed SLAs
- Slow, inefficient queries in Hive
- Legacy databases driving high operational costs
- Complex PySpark DAGs that were difficult to debug

## Pipeline Optimization

One of my major wins was diving into a critical data pipeline DAG that had become a bottleneck for our daily runs. 

1. **Query Analysis**: Identified inefficient joins and missing partitions in our Hive queries
2. **PySpark Tuning**: Optimized the Spark execution plan by managing data skew and tuning shuffle partitions
3. **Caching**: Strategically persisted intermediate DataFrames that were reused across multiple downstream jobs

**The Impact**: These optimizations reduced the daily run time of our core pipeline by **over 45 minutes**, ensuring we consistently hit our delivery SLAs.

## Decommissioning Legacy Infrastructure

Technical debt is an invisible cost until it isn't. As we migrated features to the newer, unified Sales Intelligence platform, we were left with the legacy "Sales Dashboard" application and its underlying database.

I led the effort to safely decommission this infrastructure. This wasn't just pulling a plug; it required:
- Migrating any remaining active workloads
- Ensuring downstream consumers were repointed
- Safely backing up archived data

**The Impact**: Retiring this legacy database resulted in **over $130,000 in annualized infrastructure savings**.

## Tech Stack

`PySpark` · `Hadoop` · `Hive` · `Python` · `Airflow (DAGs)` · `AWS`

---

*Moving from frontend engineering to big data pipelines was a trial by fire, but it gave me a deep appreciation for optimization. When your datasets are measured in terabytes, even a small inefficiency cascades into massive performance hits.*
