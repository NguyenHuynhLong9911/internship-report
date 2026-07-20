---
title: "Translated Blog"
date: 2026-06-08
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

# Translated AWS Blog

This section presents a translated and summarized AWS technical article selected during the internship. The article explores how to build scalable Python applications by integrating SQLAlchemy 2.x with Amazon Aurora DSQL.

## [Building Python Applications with SQLAlchemy and Amazon Aurora DSQL](3.1-Blog1/)

Amazon Aurora DSQL is a distributed, serverless, PostgreSQL-compatible database that automatically scales with application traffic and authenticates through AWS IAM. When it is used with SQLAlchemy, developers retain a familiar Python ORM workflow while adapting several database design and connection patterns for a distributed environment.

The article focuses on three essential adaptations:

- Using UUIDs as primary keys for scalable distributed inserts.
- Defining application-level relationships with `relationship()`, `primaryjoin`, and `foreign()` instead of foreign key constraints.
- Configuring the SQLAlchemy engine in AUTOCOMMIT mode to avoid unsupported SAVEPOINT operations.

It also covers the Aurora DSQL Python Connector, IAM authentication, CRUD operations, eager loading, connection lifecycle management, and retry logic with exponential backoff and jitter for optimistic-concurrency conflicts.

[Read the translated article →](3.1-Blog1/)
