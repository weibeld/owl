- What terminology to use for the "notes" (formerly "insights"): note, item, entry, blob, etc.?
- Document omission of buckets or other structurisation of notes (e.g. as an ADR, or actually add the basic idea as an Owl note?). Below is the content of the corresponding commit message body from the owl-data repository:
    ```
    Remove support for buckets

    All notes are saved as flat files adjacent to each other, no more
    categorisation into buckets, etc.

    The reason for this is that having buckets organised by topic adds
    capture friction, i.e. the necessity to decide for each new note in
    which bucket it belongs. Furthermore, many notes could reasonably belong
    to multiple buckets, further complicating the matter.

    Having notes separated by buckets also impedes retrieval, i.e.
    connections between notes in different buckets can't be made (which
    feeds back to capture friction, i.e. making an optimal decision at
    capture time which bucket to assign a note to).

    Buckets have also been abolished in the Owl project itself and instead
    all notes of an Owl instance are tracked in the same repository (it
    would still be possible to operate multiple Owl instances backed by
    different repositories, if hard separation is absolutely needed).

    A consequence of this is that all notes must be either public or
    private (since it is tracked in the same Git repository which must be
    either public or private on GitHub). The choice will probably be on a
    private GitHub repository since there might be notes containing private
    information.

    This also makes sense on a conceptual level as Owl data is not really
    meant for public consumption, but may be used as a source for creating
    content for public consumption (such as Nightingale [1] stories).

    [1] https://github.com/weibeld/nightingale
    ```
