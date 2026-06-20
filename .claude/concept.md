# Owl — Concept Doc

## 1. Motivation

A tool to fixate insights in a retrievable format with as little friction as possible, making them retrievable and interpretable at any time, and ensuring that they are never lost.

## 2. Core Philosophy

1. Organisation is the enemy
2. Capture is all that matters
3. AI handles retrieval

## 3. Core Features

1. **Append-only capture:** the intended usage is to only ever add insights, not refactoring existing ones
2. **Amend capability:** added insights can be amended if needed with commands similar in spirit to `git commit --amend`. This is not intended for regular usage but for edge cases (no distinction between most recent insight and previous insights like `git commit --amend`)
3. **Insight structure:** date and body
4. **Buckets:** every insight must be in exactly one bucket, any number of buckets can be created, buckets can be deleted (deletes all insights within them)
5. **Storage:** insights are embedded into vector representations to enable RAG-based retrieval
6. **Retrieval:** handles synthesis, analysis, querying, staleness and freshness, etc. Entirely separate project working on the data in the storage system as the main input

## 4. Peripheral Features

1. **Command-line interface:** the primary user interface is a command-line based 
2. **Git-backed storage:** insights are stored in a backend Git repository, enabling robust version control

## 5. Future Features

These are features that might be added after evaluating the viability of the core principles in an MVP:

1. Advanced bucket operations:
  - Merging
  - Selective merging (only merge part of the insights into another bucket)
  - Organisation (tagging, grouping, etc.)

## 6. Differentiator

Owl differs from traditional note-taking apps like Notion, Obsidian or Roam in that notes (insights) are append-only and not intended to be repeatedly edited or curated over time. All organisation, synthesis, and retrieval is delegated to an LLM-based retrieval layer.

## 7. Related Solution Case Studies

Closer look at solutions with similar ideas as Owl.

### [Mem](https://get.mem.ai/)

The core philosophy is similar or identical to Owl: capture with minimal friction, AI handles all organisation and retrieval. The main difference is that Mem supports multiple content types (meeting transcripts, web clips, voice notes, messages) whereas Owl has a single content type: the insight.

Owl can be seen as a stripped-down version of Mem that removes all non-essential concepts and integrations and concnetrates only on the core philosopy with a focus on capturing "insights".

### [Notational Velocity](https://notational.net/)

The core philosophy is similar to Owl: eliminate organisation (no folders), frictionless capture (create and search are the same action), and a focus on efficient retrieval. note model. The main limitation is that retrieval is purely keyword-based (not using RAG or LLMs) since Notational Velocity originates from the pre-LLM era (first published in 2009, latest version from 2011).

Notational Velocity can be seen as an early attempt at implementing (parts of) the core ideas of Owl and Mem from the pre-LLM era.

## 8. Idea Evolution

TODO: document evolution of idea with information from the [Owl](https://github.com/users/weibeld/projects/18) GitHub Project.
