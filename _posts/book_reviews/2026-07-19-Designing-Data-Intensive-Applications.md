---
layout: post
title: "📚 Book Review: Designing Data-Intensive Applications by Martin Kleppmann"
date: 2026-07-19
categories: [Data Engineering, Books]
tags: [distributed-systems, architecture, scalability]
rating: 5
max_rating: 5
excerpt: "A book that helped me understand how modern databases and distributed systems actually work."
---

**⭐⭐⭐⭐⭐ (5/5)**
**Read this if:** You want to understand the ideas behind databases, distributed systems, and modern data platforms instead of just learning another tool.
**Skip this if:** You're looking for a practical guide to Spark, Snowflake, Kafka, or any other specific technology. This book focuses on concepts that stay relevant even as tools change.
> **Note:** This rating is based on my own experience with the book.

![Book Cover](/assets/img/book_reviews/Design_Data_Intensive_Applications_Cover.png)

## ℹ️ About

Published by O'Reilly in 2017, **Designing Data-Intensive Applications (DDIA)** explains the principles behind reliable, scalable, and maintainable software systems.

The book is split into three main parts: the foundations of data systems, distributed data, and derived data through batch and stream processing. Instead of teaching you how to use a particular database or framework, Martin Kleppmann explains why these systems are designed the way they are.

Although it's nearly a decade old, I never felt like I was reading something outdated. Most of the technologies we use today still rely on the same underlying ideas.

## 💡 Biggest Takeaways

Rather than teaching a specific technology, DDIA teaches a way of thinking about data systems. These were the ideas that stuck with me the most.

### **Data outlives code**

This was probably the biggest mindset shift for me.

Applications get rewritten, frameworks come and go, and infrastructure changes over time. Your data usually doesn't. That completely changed how I think about schema evolution, compatibility, and designing systems that can evolve over the years instead of just solving today's problem.

### **Everything is a trade-off**

One of the recurring themes throughout the book is that there is no "best" database or architecture.

Instead, every design decision involves trade-offs between consistency, availability, latency, throughput, complexity, and operational cost. Understanding those trade-offs is much more valuable than memorizing which technology is currently popular.

### **Understand the internals**

Before reading DDIA, I mostly evaluated technologies based on documentation or benchmarks.

After reading it, I found myself asking different questions:

- Why is this database fast for writes?
- Why does this system choose eventual consistency?
- What happens if a node suddenly disappears?

Understanding what's happening under the hood makes learning new technologies much easier.

### **Distributed systems are hard for good reasons**

The book also made me appreciate why distributed systems are considered difficult.

Problems like network partitions, clock skew, duplicate messages, and partial failures aren't edge cases—they're things you have to expect in production. Designing software that behaves correctly despite those failures is much harder than simply making it work on your laptop.

### **Think in terms of long-term maintainability**

Performance is important, but DDIA repeatedly emphasizes that systems also need to be understandable, maintainable, and adaptable.

A solution that's slightly slower but easier to evolve is often the better engineering decision in the long run.

## ✅ What I Enjoyed

### It explains *why*, not just *what*

One thing I really appreciated is that the book rarely tells you that one approach is better than another. Instead, it explains why different systems make different design decisions.

That made it much easier to understand when a certain database or architecture is a good fit instead of just following recommendations blindly.

### The storage engine chapters finally clicked

Before reading DDIA, I knew terms like **B-trees** and **LSM-trees**, but I couldn't really explain why different databases use them.

Those chapters helped me understand the trade-offs between reads, writes, and storage, and they've made database documentation much easier to follow ever since.

### It doesn't hide the difficult parts

Distributed systems are messy, and the book doesn't pretend otherwise.

Topics like replication, clock skew, network partitions, and consensus aren't simplified to the point where they become misleading. Instead, Kleppmann explains why these problems are genuinely difficult and what different systems do to deal with them.

### It's a book I'll come back to

This isn't the kind of book you finish once and put back on the shelf.

I've already found myself revisiting a few chapters when learning about new technologies because having those fundamentals makes it easier to understand what's happening under the hood.

## ❌ What Could Be Better

### It's a demanding read

This isn't a book I'd recommend reading casually before bed.

Some chapters—especially the ones on transactions and consensus—took me more than one pass to fully understand. That's more a reflection of the subject matter than the writing, but it's worth knowing before you start.

### It's focused on concepts

If you're expecting tutorials or hands-on examples, this isn't that kind of book.

You'll probably want to pair it with documentation or practical projects if you're learning a new technology at the same time.

### Some examples show their age

The book was published in 2017, so it doesn't cover newer trends like dbt, lakehouse architectures, or many cloud-native data platforms.

That said, I never felt this reduced its value because the core concepts are still the same.

## 👤 About the Author

Martin Kleppmann is a researcher in distributed systems at the University of Cambridge and previously worked as a software engineer at companies including LinkedIn and Rapportive.

His background shows throughout the book—it strikes a nice balance between theory and practical engineering without feeling overly academic.

## ⭐ Final Verdict

I can see why this book is recommended so often.

It didn't make me an expert in distributed systems overnight, but it gave me a much better mental model for understanding databases, distributed systems, and data engineering in general.

If someone asked me to recommend one book to better understand modern data systems, this would probably be my first suggestion.

It's not an easy read, but it's one of the few technical books that I've already gone back to after finishing because there's so much packed into it.

>**⭐⭐⭐⭐☆ (4/5)**

## 🔗 Where to Get the Book

- **Official Publisher:** [O'Reilly Media / O'Reilly Learning Platform](https://www.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/)
- **References from the Book:** https://github.com/ept/ddia-references
