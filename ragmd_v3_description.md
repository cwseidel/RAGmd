# ragmd_v3 is an improvement of ragmd

Currently I use ragmd to ask questions about my markdown documents. However I want to make it more aware of the general context
by assigning it a role. For instance, I'd like it to be more proactive about making sure my documents meet a certain criteria,
such as stating their purpose, or making sure I'm asking biological questions. I want it to be a curious curation helper,
and have it help me to make sure there is some kind of narrative in my markdown documents.

To accomplish this two files were created:

 - role.md
 - rubric.yaml

These documents go into the .ragmd directory. Functions were added to ragmd to incorporate functionality.

Run a curation sweep

```bash
ragmd curate --recursive
```

Write sidecar reports:

```bash
ragmd curate --recursive --write-suggestions
```

Writes a curation sister document for each document with the name *.curation.md with a curation report.

```bash
ls *.curation.md
```

Write a sister document and an aggregated report:

```bash
ragmd curate --recursive --write-suggestions --aggregate-report .ragmd/curation_report.md
```

Write just the combined report:

```bash
ragmd curate --recursive --aggregate-report .ragmd/curation_report.md
```

Prepend actionable TODOs into each doc:

```bash
ragmd curate --recursive --apply
```

Keep normal Q&A behavior, but now with the persona:

```bash
ragmd ask "What are the open biological questions in this project?"
```

## Why this works well for “narrative curation”

 - Role-aware answers: every ask now uses your persona/voice.
 - Objective structure: the rubric enforces purpose, question, methods, results, narrative, provenance, next steps.
 - Actionable output: sidecar reports or inline TODOs keep momentum.
 - Offline fallback: even without an API key you get a useful checklist.


