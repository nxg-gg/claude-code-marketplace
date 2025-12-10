---
name: explain-api
description: Deep dive into any API endpoint - traces from controller to database
argument-hint: "<endpoint> e.g., GET /sessions/matches"
---

## Mission

Perform a complete deep dive analysis of the specified API endpoint, tracing it through all layers of the codebase.

## Usage

```
/explain-api GET /sessions/matches
/explain-api POST /auth/login
/explain-api PATCH /players/:id
```

## Execution

Use the api-deep-dive agent to analyze this endpoint:

{{arg}}

The agent will:
1. Find the controller handling this endpoint
2. Read the method and decorators
3. Examine the DTOs (request/response)
4. Trace to the Interactor (application layer)
5. Follow to the Query/Command Handler
6. Check the Repository interface and implementation
7. Show the database schema and domain entity
8. Identify guards, interceptors, caching
9. Draw the complete request flow

Be thorough - read actual files and show real code snippets!