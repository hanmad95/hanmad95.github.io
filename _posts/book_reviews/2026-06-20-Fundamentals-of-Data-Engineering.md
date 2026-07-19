---
layout: post
title: "📚 Book Review: Fundamentals of Data Engineering by Reis & Housley"
date: 2026-06-20
categories: [Data Engineering, Books]
tags: [data-architecture, dataops, learning]
rating: 4
max_rating: 5
excerpt: "A review of Fundamentals of Data Engineering by Joe Reis and Matt Housley—why this principle-first book belongs on every data engineer's reading list."
---

**⭐⭐⭐⭐☆ (4/5)**
**Read this if:** You want to understand the principles behind modern data platforms rather than learn a specific tool.
**Skip this if:** You're looking for a hands-on programming book filled with code examples and implementation tutorials.
> **Note:** The **4/5 rating is based entirely on my personal enjoyment and experience with the book.** It's not an objective measure of its quality, and your opinion may differ depending on your background and expectations.

![Book Cover](/assets/img/book_reviews/Fundamentals_of_Data_Engineering_Cover.png)

## ℹ️ About

The data engineering ecosystem moves incredibly fast. Every year brings a new framework, orchestration platform, or storage format that promises to revolutionize the industry. It's easy to get caught up in the latest trends and lose sight of the fundamentals.

That's what makes **Fundamentals of Data Engineering** by **Joe Reis** and **Matt Housley** so refreshing.

Rather than focusing on individual technologies, the authors explain the principles that remain relevant regardless of whether you're using Spark, Kafka, Airflow, dbt, or whatever comes next. Instead of teaching *which* tool to use, they teach *how to think* about designing data systems.

For me, that's what makes this book stand out.

## 💡 The Biggest Takeaway: Think in Lifecycles, Not Pipelines

The concept that resonated with me the most is the **Data Engineering Lifecycle**.

Many people think of data engineering as simply moving data from one system to another. The authors argue that it's much broader than that. They describe five interconnected stages:

1. **Generation** – Understanding where data originates, from transactional databases to IoT devices.
2. **Storage** – Selecting the right storage solution based on performance, scalability, and cost.
3. **Ingestion** – Moving data efficiently from systems that you often don't control.
4. **Transformation** – Cleaning, modeling, and enriching raw data into business-ready datasets.
5. **Serving** – Delivering data for analytics, machine learning, operational systems, and Reverse ETL.

What makes this framework particularly useful is that it encourages you to think about the entire system instead of optimizing only one component.

Throughout every stage, the authors introduce what they call the **undercurrents**: Security, Data Management, DataOps, Data Architecture, Orchestration, and Software Engineering.

These aren't optional topics or afterthoughts—they influence every architectural decision you make.

## ✅ What I Enjoyed

### It teaches principles instead of products

One of my favorite aspects of the book is that it avoids becoming a catalog of technologies.

Instead of saying *"use this framework,"* it explains concepts like:

- Idempotency
- ACID vs. BASE
- Schema-on-read vs. schema-on-write
- Data modeling trade-offs
- Distributed system fundamentals

Those ideas remain valuable even as tools evolve.

### It encourages architectural thinking

Rather than presenting a single "correct" architecture, the authors consistently discuss trade-offs.

That mindset is incredibly valuable because real-world engineering is rarely about finding perfect solutions—it's about making informed compromises.

### The undercurrents deserve more attention

Many engineers naturally gravitate toward exciting technologies while overlooking governance, security, documentation, cost optimization, or operational excellence.

This book argues that those "boring" topics are often what separate successful data platforms from expensive failures.

I completely agree.

## ❌ What Could Be Better

This isn't a perfect book, and it's worth knowing what you're getting before you buy it.

### It isn't a coding book

If you're expecting detailed tutorials on Spark, Kafka, Flink, or Airflow, you'll probably be disappointed.

There are very few implementation examples because that's simply not the book's goal.

### Some topics move quickly

Because the book covers the entire data engineering landscape—from storage hardware to cloud architecture and machine learning—it occasionally introduces complex topics without exploring them in great depth.

In several chapters, I found myself wanting another 20–30 pages of discussion.

## 👤 About the Authors

Joe Reis and Matt Housley are the co-founders of **Ternary Data** and bring decades of practical industry experience.

Their background shows throughout the book. The advice feels grounded in real production systems rather than academic theory, and they consistently explain *why* certain architectural choices matter instead of presenting them as universal best practices.

## ⭐ Final Verdict

If I could recommend just one book to someone beginning a career in data engineering, this would be near the top of the list.

It won't teach you every cloud service, framework, or programming technique.

Instead, it teaches something far more valuable: **how to think like a data engineer.**

Because the focus is on principles rather than technologies, I expect this book to remain relevant for many years. That's something few technical books can claim.

>**⭐⭐⭐⭐☆ (4/5)**

## 🔗  Where to Get the Book

- **Official O'Reilly page:** [Fundamentals of Data Engineering](https://oreil.ly/fundamentals-of-data)
- Also available from major booksellers, including Amazon and Barnes & Noble.
