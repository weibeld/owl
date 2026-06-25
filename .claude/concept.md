# Owl — Concept Doc

## 1. Motivation

A tool to record insights in a retrievable format with as little friction as possible, making them retrievable and interpretable at any time, and ensuring that they are never lost.

## 2. Core Ideas

1. No organisation and curation: no folder structure or cross links, append-only
2. Minimal friction for capture: single input channel
3. Intelligent retrieval: LLM-based, deriving structure and meaning

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

## 7. Related Solutions Case Studies

Closer look at solutions that use similar ideas as Owl.

### [Mem](https://get.mem.ai/)

The core philosophy is similar or even identical to Owl: minimal friction capture, no organisation, LLM-based retrieval. Meaning and intelligence is fully derived in the retrieval stage. The main difference is that Mem provides a larger set of peripheral features than Owl, such as multiple content types (meeting transcripts, web clips, voice notes, messages), note collections, tags, and a graphical user interface.

Mem can be seen as an expanded version of Owl that adds generally useful but non-essential features and integrations to the core philosophy shared with Owl.

> Note: the above description applies to Mem 2.0 which was [released in 2025](https://www.producthunt.com/products/mem-2-0). Earlier versions of Mem exist since 2020 but are not fully LLM-based.

### [Notational Velocity](https://notational.net/)

The core philosophy is similar to Owl: reduce organisation (no explicit categorisation), minimal friction capture (single input field for both capture and search), and a focus on retrieval efficiency (incremental search). The main limitation is that retrieval is done in a conventional keyword-based manner since Notational Velocity originates from the pre-LLM era (first published in 2009, latest version from 2011).

Notational Velocity can be seen as an early attempt at implementing the core ideas of Owl and Mem that has been held back by the limited retrieval technologies that existed at the time when the tool was developed (pre-LLM era).

GitHub: [scrod/nv](https://github.com/scrod/nv) ([wiki](https://github.com/scrod/nv/wiki))

### [jrnl](https://jrnl.sh/)

CLI-based journaling tool with local plain-text file storage. Shares Owl's peripheral preferences (CLI interface, local files, potential Git tracking) but not its core philosophy (capture first, no organisation, intelligent retrieval). Instead, jrnl uses traditional organisation (tags, templates, chronological structure) and conventional date-based and keyword-based retrieval. It doesn't put emphasis on the derivation of meaning and intelligence in the retrieval stage.

GitHub: [jrnl-org/jrnl](https://github.com/jrnl-org/jrnl)

### [GitJournal](https://gitjournal.io/)

Mobile frontend for a GitHub repository with markdown notes (also works with GitLab or other providers). Allows viewing and editing notes and save edits directly back to the Git repository. Not related to Owl's core philosophy (minimal friction capture, no organisation, intelligent retrieval), but shares the focus on native Git integration for storage and version control with Owl.

GitHub: [GitJournal/GitJournal](https://github.com/GitJournal/GitJournal)
