---
name: analyze
description: Analyzes a folder structure and explains how the code works using the folder-analyzer agent
argument-hint: "<path/to/folder>"
---

## Mission
Use the folder-analyzer agent to examine a specified folder, understand its structure, and provide a comprehensive explanation of how it works.

## Steps

1. Validate that the folder path exists
2. Invoke the folder-analyzer agent
3. Have the agent analyze the folder structure
4. Present the findings in a clear, organized format

## Execution

Please use the folder-analyzer agent to analyze the folder: {{arg}}

The analysis should include:
- Complete folder structure
- Purpose and functionality
- Key files and their roles
- How the components work together
- Notable patterns or architecture decisions
- A concise summary

If no folder path is provided, analyze the current directory (.).