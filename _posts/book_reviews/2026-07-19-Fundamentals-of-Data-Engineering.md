---
layout: post
title: "Book Review: Fundamentals of Data Engineering by Reis & Housley"
date: 2026-07-19
categories: [Data Engineering, Books]
tags: [data-architecture, dataops, learning]
rating: 4
max_raging: 5
---

> **About**
>In the fast-moving world of data, it is easy to get lost in the "tool-of-the-week" hype. **Fundamentals of Data Engineering** by Joe Reis and Matt Housley is a breath of fresh air that ignores the noise and focuses on the **immutable principles** of the field. As a Data Engineer, finding a resource that connects the dots of the end-to-end data lifecycle is rare, and this book does exactly that.

![Book Cover](/assets/img/book_reviews/Fundamentals_of_Data_Engineering_Cover.png)

## The Central Framework: The Data Engineering Lifecycle

The book's greatest strength is its definition of the **data engineering lifecycle**. It moves beyond the simple "plumbing" of moving data from A to B and identifies five key stages:

1. **Generation:** Understanding source systems like IoT swarms and transactional databases.
2. **Storage:** Choosing between object storage, data warehouses, and lakehouses based on data "temperature".
3. **Ingestion:** Handling the bottleneck of gathering data from systems outside your control.
4. **Transformation:** Converting raw ingredients into business value through modeling and cleaning.
5. **Serving:** Delivering data for analytics, ML, and **Reverse ETL**.

Interwoven throughout these stages are the **"undercurrents"**—Security, Data Management, DataOps, Data Architecture, Orchestration, and Software Engineering—which the authors argue must be top-of-mind at every step.

## What I Like as a Data Engineer

* **A Focus on "How to Think":** The book doesn't just give you a manual; it teaches you how to evaluate trade-offs. For instance, the distinction between **Type A (Abstraction)** and **Type B (Build)** engineers helps clarify career paths and organizational needs.
* **Tool-Agnostic Wisdom:** By focusing on concepts like **idempotency**, **ACID vs. BASE**, and **schema-on-read vs. write**, the authors provide knowledge that won't become obsolete when the next hot framework arrives.
* **The Power of Undercurrents:** Often, engineers ignore "boring" topics like data governance or FinOps. This book successfully demonstrates that these are actually "enterprisey" superpowers that help control costs and ensure data trust.

## What Is Not Ideal

* **Lack of Deep-Dive Code:** If you are looking for a step-by-step tutorial on how to write a specific PySpark job or configure a Kafka cluster, this isn't that book. It stays at a high architectural level, which is its purpose, but may leave some "hands-on" learners wanting more concrete implementation details.
* **Breadth Over Depth:** Because it covers the *entire* landscape—from magnetic disk physics to the future of "Live Data Stacks"—it can sometimes feel like it's scratching the surface of complex topics like ML engineering or cloud networking.

## About the Authors

**Joe Reis** and **Matt Housley** are the co-founders of **Ternary Data**. Joe is a business-minded data nerd with two decades of experience, and Matt holds a PhD in mathematics. They often refer to themselves as "recovering data scientists" who transitioned into engineering after realizing that most data science projects fail without a solid foundation. You can also catch them discussing industry trends on their show, ***The Monday Morning Data Chat***.

## Final Verdict

This is an **instant classic** and a must-read for anyone serious about a career in data. Whether you are a "recovering data scientist" or a software engineer pivoting into data, this book provides the blueprint you need to build robust, scalable systems.

## Where to Get the Book

* **Official O'Reilly Page:** [Fundamentals of Data Engineering](https://oreil.ly/fundamentals-of-data)
* Available at major retailers like Amazon and Barnes & Noble.
