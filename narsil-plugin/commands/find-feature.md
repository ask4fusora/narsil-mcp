---
description: Find where a specific feature or concept is implemented in the codebase
---

# Find Feature Implementation

Help locate where a specific feature or concept is implemented in the codebase.

## Workflow

1. **Parse input**: Extract feature description from $ARGUMENTS

2. **AI-assisted search**: Use `find_implementation` with the feature description for AI-guided feature location

3. **Semantic search**: Use `hybrid_search` with the feature description to find semantically relevant code

4. **Symbol search**: Use `workspace_symbol_search` with key terms from the feature to find related symbols

5. **For promising candidates**:
   - Use `find_symbol_usages` to see how widely each candidate is used
   - Use `get_symbol_definition` to read the actual implementation

6. **Trace connections** (if call-graph enabled):
   - Use `get_callers` and `get_callees` to understand how the feature integrates

7. **Present findings**:
   - Primary implementation location(s)
   - Key functions/classes involved
   - How the feature is invoked/used
   - Related files and modules

## Arguments

Feature to find: $ARGUMENTS

Example usage:
- `/narsil:find-feature user authentication`
- `/narsil:find-feature payment processing`
- `/narsil:find-feature error handling`
