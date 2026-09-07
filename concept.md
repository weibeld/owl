# Owl — Concept Doc

## 1. Problem Statement

Personal knowledge management — the externalisation of knowledge and thoughts as text for future retrieval — is commonly practiced through note-taking. Traditional note-taking systems require some form of organisation at capture time (categorisation, tagging, linking, hierarchical structure) in order to make notes retrievable later. Without retrieval, the entire point of personal knowledge management is lost, so organisation is not optional — it is a prerequisite for the system to be useful.

Organisation, however, is labour-intensive and attention-absorbing. More insidiously, it tends to induce a phenomenon we call **curation creep**: the gradual emergence of an urge to treat one's notes as a personal encyclopedia — something that should be complete, comprehensive, consistent, and free of gaps. This leads in the worst case to the creation of notes for the sole purpose of filling a perceived gap, i.e. content that is not driven by genuine knowledge or experience but by the internal logic of the note system itself. At that point, the organisation of notes has become a task of its own, one that competes with and can entirely displace the actual work that note-taking was meant to facilitate.

## 2. Proposed Solution

### Redefining Capture and Retrieval

The root cause of curation creep is the dependency of retrieval on the organisation of information at capture time. Until recently, this dependency was unavoidable: the available retrieval technology relied on explicit structure (tags, folders, links, keywords, etc.) to meaningfully retrieve relevant content.

With the advent of LLMs this changes. LLMs are precisely built for extracting meaning and structure from unorganised textual data. That means, by using LLMs for retrieval, the requirement for organisation at capture time becomes obsolete. This in turn eliminates the main culprit for curation creep.

Therefore, Owl is centred around the following philosophy:

1. **No organisation:** notes are captured without categorisation, tagging, linking, or other curation. Capture becomes a friction-less one-off operation
2. **Intelligent retrieval:** all meaning, structure, and context is derived at retrieval time by an LLM-based retrieval component. Retrieval is the real workhorse instead of capture and organisation.

In other words, the meaning-deriving logic is moved from the capture stage to the retrieval stage.

### Focus on Insights

The removal of organisation has some consequences on how we look at the recorded knowledge at a conceptual level. The recorded knowledge items do now NOT need to be embedded into a predefined and ever-evolving organisation structure at capture time. As mentioned, the knowledge's organisation is derived in real time at retrieval time.

Instead, captured knowledge items can now take on a fleeting nature and can be created in a "shoot-and-forget" manner. The most important point is that the core knowledge a user wants to record is captured. Any connections, gaps, duplications, etc. in the context of other recorded knowledge is fully derived by the retrieval stage.

This shifts the nature of recorded knowledge items away from notes (which typically have a specific topic and are embedded in a knowledge graph with other existing notes — exactly what enables curation creep) towards the notion of **insights**.

An insight is a piece of knowledge that a user deems worth recording in a specific context, at a specific moment in time. Insights do NOT need to be objectively grounded and harmonised with other recorded knowledge items, as notes usually would, but can be highly subjective, time and context-dependent.

Therefore, Owl revolves around the concept of **insights** as the elementary knowledge items that are captured.

This conceptual shift is another step away from curation creep towards a more efficient knowledge management that captures only what matters with minimal overhead while still enabling effective and efficient retrieval.

## 3. Features

1. **Append-only focus:** insights are intended to be captured and left as-is. Editing is possible for edge cases but is not the intended usage (akin to Git commit amendment).
2. **Unstructured input:** insights are unstructured blobs of text with no imposed formatting or structure
3. **CLI-based:** both capture and retrieval are CLI-based. Capture may additionally employ an editor such as Vim for editing, and retrieval may use an LLM agent chat interface.
4. **Git-based:** the input data (which is the source of truth) is automatically tracked by Git allowing for robust and fully controllable version control and backup.
5. tbd

## 4. Related Solutions

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
