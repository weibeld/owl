# Owl — Concept Doc (WIP)

> Note: this document is WIP and may not reflect the current state of the implementation at all times. The working implementation is the authoritative source.

> TODO: extend concept doc to final concept doc structure (see blueprint-workflow repository or elsewhere for a discussion of the settled structure and content of a conept doc).

## 1. Problem Statement

> TODO: write a full problem statement. The field is personal knowledge management (PKM) and the following are the key problems to address:
>
> - **Organisation overhead:** the ongoing maintenance cost of keeping a structured system coherent — links go stale, categories drift, hierarchies need restructuring, formats need enforcing across all items
> - **Capture friction:** the decision cost at the moment of capture — where does this item go, what tags, what category, how does it relate to existing content. This causes deferral ("I'll add it properly later") which in practice means loss

## 2. Proposed Solution

The root cause of the above problems is the dependency of retrieval on the organisation of information at capture time. With the advent of LLMs this dependency is no longer necessary: LLMs are built precisely for extracting meaning and structure from unorganised textual data.

Therefore, Owl is built around two core principles:

1. **No organisation at capture time:** content is captured without categorisation, tagging, linking, or other curation. Capture is a friction-free operation.
2. **Meaning derivation at retrieval time:** all meaning, structure, and context is derived at retrieval time by an LLM-based retrieval component. Retrieval is the real workhorse.

These two principles have a direct implication for the kind of content Owl accepts: there are no constraints on the content, format, or structure of what is stored, the only requirement is that it is text. Any blob of text — a personal note, a research finding, a copy-pasted snippet, a half-finished thought — is equally valid input. Owl's value generalises uniformly across all of these without modification.

## 3. Related Solutions

A closer look at solutions that use similar ideas as Owl.

### [Mem](https://get.mem.ai/)

The core philosophy is similar or even identical to Owl: no organisation, intelligent retrieval. Meaning and intelligence is fully derived in the retrieval stage. The main difference is that Mem provides a larger set of peripheral features than Owl, such as multiple content types (meeting transcripts, web clips, voice notes, messages), note collections, tags, and a graphical user interface.

Mem can be seen as an expanded version of Owl that adds generally useful but non-essential features and integrations to the core philosophy shared with Owl.

> Note: the above description applies to Mem 2.0 which was [released in 2025](https://www.producthunt.com/products/mem-2-0). Earlier versions of Mem exist since 2020 but are not fully LLM-based.

### [Notational Velocity](https://notational.net/)

The core philosophy is similar to Owl: no organisation, intelligent retrieval. The main limitation is that retrieval is done in a conventional keyword-based manner since Notational Velocity originates from the pre-LLM era (first published in 2009, latest version from 2011).

Notational Velocity can be seen as an early attempt at implementing the core ideas of Owl and Mem that has been held back by the limited retrieval technologies that existed at the time when the tool was developed (pre-LLM era).

GitHub: [scrod/nv](https://github.com/scrod/nv) ([wiki](https://github.com/scrod/nv/wiki))

### [jrnl](https://jrnl.sh/)

CLI-based journaling tool with local plain-text file storage. Shares Owl's peripheral preferences (CLI interface, local files, potential Git tracking) but not its core philosophy (no organisation, intelligent retrieval). Instead, jrnl uses traditional organisation (tags, templates, chronological structure) and conventional date-based and keyword-based retrieval. It doesn't put emphasis on the derivation of meaning and intelligence in the retrieval stage.

GitHub: [jrnl-org/jrnl](https://github.com/jrnl-org/jrnl)

### [GitJournal](https://gitjournal.io/)

Mobile frontend for a GitHub repository with markdown notes (also works with GitLab or other providers). Allows viewing and editing notes and save edits directly back to the Git repository. Not related to Owl's core philosophy (no organisation, intelligent retrieval), but shares the focus on native Git integration for storage and version control with Owl.

GitHub: [GitJournal/GitJournal](https://github.com/GitJournal/GitJournal)
