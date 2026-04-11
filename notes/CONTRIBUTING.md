# Contributing notes

Notes in this folder are rendered by [mipviz](https://mipviz.mghannam.com)
under the **About → Notes** tab on any MIPLIB instance viewer page. They
are curated, community-edited markdown documents — **not** authoritative
statements by the mipviz maintainers. Every claim in a note must be
traceable to a linked reference at the bottom of the file.

## Layout

```
notes/
  <instance>.md              — per-instance note, shown only on that instance
  <instance>/images/...      — images referenced from <instance>.md
  groups/<group>.md          — group note, shown on every instance whose
                               MIPLIB "group" field equals <group>
  groups/<group>/images/...  — images referenced from groups/<group>.md
```

When both a per-instance note and a group note exist, the per-instance
note renders first, followed by the group note under a `Group: <group>`
label.

Relative image paths in markdown (e.g. `![](images/structure.png)`)
resolve against the note's own directory — no need to write absolute
URLs.

## What to include

A good note can cover any or all of:

- **Description** — what the instance models, the real-world problem
  behind it, and how it got into MIPLIB
- **Structure** — algebraic or combinatorial shape of the constraint
  matrix, symmetry, decomposability
- **Why it is hard (or easy)** — what makes the LP relaxation weak,
  what blows up branch-and-bound, or why presolve crushes it
- **Techniques that help** — reformulations, cutting planes,
  heuristics, symmetry handling, decomposition; cite the paper for
  each
- **Trivia** — historical notes, record-holders, surprising facts

**Keep it short.** One screen of prose + a reference list is enough for
most instances. Link out for the rest.

## Required: linked references

Every note **must** end with a `## References` section listing each
source cited in the text. Each reference should include a DOI, arXiv
link, or permanent URL. This is how we avoid making authoritative
claims: if it isn't in a cited paper, don't write it.

You can seed a triage draft with linked candidate papers by running:

```bash
python3 scripts/find_group_references.py <group> --limit 20 > /tmp/draft.md
```

from the mipviz repo. The output uses the same shape as this template.

## Example skeleton

```markdown
# <group or instance name>

One-paragraph description of the problem class, with a citation to
the origin paper[^1].

## Why they are hard

- bullet
- bullet

## Techniques that help

- **Reformulation X.** Short explanation, citing the paper[^2].
- **Heuristic Y.** etc.

## References

[^1]: Author, A., & Author, B. (YEAR). *Paper title.* Venue.
      [DOI](https://doi.org/10.xxxx/yyyy)
[^2]: Author, C. (YEAR). *Other paper.*
      [arXiv](https://arxiv.org/abs/xxxx.xxxxx)
```

## Submitting

1. Fork [mmghannam/mipviz-instances](https://github.com/mmghannam/mipviz-instances)
2. Add or edit your `notes/<name>.md` (or use the **Edit on GitHub**
   link from the mipviz instance page — it opens the right file
   directly).
3. Open a PR. Small, focused PRs land faster than large rewrites.

Notes go live on mipviz.mghannam.com within a minute of merging.
