> Mirror of [iceanimations/checkoutin](https://github.com/iceanimations/checkoutin), published by the
> studio under EPL 2.0. Kept here for reference; the original repository is the canonical one.

# checkoutin

The publish and check-in half of a shot and asset pipeline, built on TACTIC.

An artist pulls a task, gets a starter file in their own sandbox, works, and publishes a version back
into the context. `checkoutin` is the tool that keeps that loop honest: it knows what a task is, what
the latest version in the context is, who is assigned to it, and what a valid publish looks like.

## The modules

| File | Job |
|---|---|
| `src/backend/_backend.py` | The TACTIC-facing backend: task queries, context resolution, version lookup |
| `src/publish.py` | The publish flow, from validation through to the version record |
| `src/mainBrowser.py` | The context browser artists navigate to find their work |
| `src/myTasks.py` | The My Tasks interface: assigned work, starter-file creation |
| `src/checkinput.py` | Check-in, with the input validation that keeps bad publishes out |
| `src/link_rig_shaded.py` | Rig and shading variant linking |
| `src/published_report.py` | Reporting over what has been published |
| `src/_seqshot.py` | Sequence and shot naming and resolution |
| `scenarios` | A Gherkin spec for the starter-file behaviour, written before the code |

`scenarios` is worth reading if you only read one file. It states the rule the tool exists to enforce:
a task file should be empty when the context has no versions, and the latest version otherwise.

## Dependencies

Not standalone. It imports `tactic_client_lib` (Southpaw's TACTIC client), plus `auth`, `app.util`,
`customui`, `cui` and `imaya` from the studio pipeline, and the UI is PyQt4.

## Authorship

360 commits between 2014 and 2021, and this one was genuinely built by a team:

| Author | Commits |
|---|---|
| Talha Ahmed | 154 |
| Qurban Ali | 143 |
| Hussain Parsaiyan | 53 |
| unattributed | 10 |

I led the work and wrote the largest share. Qurban Ali and Hussain Parsaiyan wrote most of the rest.
The commit log is the record, and this mirror does not claim otherwise.

LICENSE
=======

Copyright 2021. Talha Ahmed. All rights reserved.

This work is licensed under the terms of Eclipse Public License - v 2.0.
For a copy see https://www.eclipse.org/org/documents/epl-2.0/EPL-2.0.txt
