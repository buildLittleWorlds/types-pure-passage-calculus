# The Pure Passage Calculus

**A Types & Computation Course**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/buildLittleWorlds/types-pure-passage-calculus/blob/main/notebooks/tutorial_01_what_is_a_passage.ipynb)

*Teaching lambda calculus through the intellectual history of Densworld's Classification Integrity Committee*

---

## A Letter from the Classification Integrity Committee

*Capital Archives, Year 722*

To the Scholars of the Archive:

Two years ago, this institution witnessed what we now call the Great Categorical Collapse. For three days in the spring of Year 720, the Archive's classification systems failed catastrophically. Documents reclassified themselves. Citations became circular. Indexes referenced their own entries. The hierarchies that had organized human knowledge for generations inverted, flattened, and dissolved.

We recovered. The damage was contained. But the question remained: *How did this happen, and how do we prevent it from happening again?*

The Classification Integrity Committee was formed to answer this question. After two years of investigation, one of our members—Senior Logician Kelleth Mund—has proposed a radical theory.

Mund argues that the collapse occurred because our classification system allowed *objects* to reference themselves. A document could cite itself. An index could contain itself. A category could be a member of itself. These self-referential structures created loops that the archive could not resolve.

His solution is equally radical: **eliminate objects entirely**. In Mund's framework, there are no documents, no indexes, no categories. There are only *passages*—transformations that take inputs and produce outputs. What we call a "document" is simply a passage that hasn't been applied yet. What we call a "category" is a passage that sorts other passages.

This course presents Mund's Pure Passage Calculus—the formal system that may prevent future collapses. Whether you find his ideas compelling or dangerous, you must understand them. The future of the Archive depends on it.

*—The Classification Integrity Committee*

---

## The Great Categorical Collapse

In Year 720, on the 14th day of the third month, Archivist Torrel Goss noticed something strange in Section A-7. Manuscript MS-0501, an expedition report, had begun citing its own appendix. Not as a later addition—the citation appeared to have always been there, creating an impossible temporal loop.

Over the next three days, the anomalies spread:

- **Circular Citations**: Documents citing themselves, citing documents that cited them
- **Reclassifications**: Manuscripts changing their own genre while being read
- **Index Loops**: Alphabetical indexes that referenced their own entries
- **Hierarchy Inversions**: Parent categories becoming children of their children

By the morning of the 17th, the chaos had subsided as mysteriously as it began. Eleven documents were irrecoverably lost—their meaning dissolved into self-reference. The Archive recovered, but its scholars were shaken.

What had caused the collapse? Some blamed Dens influence—the strange region to the south whose proximity had always troubled the Capital. Others saw it as a failure of archival practice. But Kelleth Mund saw something deeper: a flaw in the very notion of categorical structure.

---

## Kelleth Mund (720-798)

Kelleth Mund was a young logician when the Great Collapse occurred. He had joined the Archive only months before, drawn by its promise of ordered knowledge. The collapse shattered that promise—and set Mund on a seventy-year quest to rebuild it on firmer foundations.

**Key Works:**
- *On the Reduction of Structure* (Year 722) — First proposal of the Pure Passage Calculus
- *Against Objects* (Year 725) — Philosophical argument for eliminating objects
- *The Passage Calculus* (Year 731) — Complete formal treatise
- *On Church Numerals* (Year 738) — Numbers as pure passages
- *On Self-Reference* (Year 752) — Fixed points and the Y combinator
- *Paradoxes of Self-Application* (Year 758) — Non-termination and its meaning
- *Passages and Their Limits* (Year 775) — Mature philosophical reflection

**Career:**
- Year 720: Joined the Archive as junior logician
- Year 720: Witnessed the Great Categorical Collapse
- Year 720: Appointed to the Classification Integrity Committee
- Year 735: Promoted to Senior Logician
- Year 762: Became Director of the Classification Integrity Committee
- Year 792: Retired after 72 years of service
- Year 798: Died peacefully in the Capital

**Legacy:**
Mund's Pure Passage Calculus remains controversial. His student Jorell Vance proposed an alternative—the Combinatorial Reduction—that eliminates even the variable names Mund used. His nephew Brennis Mund later added *types* to the calculus, creating boundaries that prevent certain passages from combining. The debate between pure passages and typed passages continues to this day.

---

## Course Overview

This course teaches the fundamentals of computation through Mund's Pure Passage Calculus—what modern computer scientists call the *lambda calculus*.

### Densworld Terminology

| Technical Term | Densworld Term | Mund's Definition |
|----------------|----------------|-------------------|
| Lambda expression | Passage | A transformation awaiting application |
| Variable | Name | A placeholder for any passage |
| Abstraction | Passage construction | Creating a new passage |
| Application | Passage application | Applying one passage to another |
| Beta reduction | Simplification | Substituting arguments for names |
| Normal form | Resolved passage | A passage that cannot simplify further |
| Non-termination | Dissolution | A passage that simplifies forever |
| Fixed point | Self-referential passage | A passage that equals its own output |

### Tutorials

| # | Title | Technical Concepts | Datasets |
|---|-------|-------------------|----------|
| 01 | What Is a Passage? | Lambda expressions, abstraction | expressions, collapse_records |
| 02 | Names and Binding | Variables, free/bound, alpha equivalence | expressions, correspondence |
| 03 | Application and Substitution | Beta reduction, substitution | expressions, reductions |
| 04 | Simplification Rules | Normal forms, reduction strategies | reductions |
| 05 | Everything Is a Passage | Church encodings | church_encodings |
| 06 | Self-Reference and Dissolution | Fixed points, Y combinator, non-termination | fixed_point_observations, collapse_records |
| 07 | Build a Passage Evaluator | Parser, evaluator, REPL | All datasets |

### Prerequisites

- Basic Python programming
- Comfort with functions and recursion
- No prior knowledge of lambda calculus required

---

## Technical Content

By the end of this course, you will understand:

1. **Lambda expressions** — The universal language of computation
2. **Variable binding** — How names are bound and substituted
3. **Beta reduction** — The fundamental rule of computation
4. **Church encodings** — Numbers, booleans, and data as pure functions
5. **Fixed points** — Self-reference and recursive computation
6. **Non-termination** — When computation never ends
7. **Implementation** — Building an interpreter from scratch

---

## Series: Types & Computation

This course is part of the **Types & Computation** series, which traces the intellectual history of type theory through Densworld scholars:

| Course | Scholar | Technical Content |
|--------|---------|-------------------|
| **01: The Pure Passage Calculus** | Kelleth Mund | Lambda calculus |
| 02: Combinatorial Reduction | Jorell Vance | Combinatory logic |
| 03: Typed Passages | Brennis Mund | Simply typed lambda calculus |
| 04: Continuous Domains | Arren Mott | Domain theory |
| 05: Dependent Classifications | Sereth Linn | Dependent types |
| 06: Resource Typing | Quellen Vast | Linear types |
| 07: Equivalence via Passage | Dora Keth | Homotopy Type Theory |

---

## Getting Started

Each tutorial is a Jupyter notebook designed to run in Google Colab. Click the badge at the top of any notebook to open it in Colab.

The notebooks load data from the central Densworld datasets repository. All you need is a browser—no local installation required.

---

*Part of the [Densworld Courses](https://github.com/buildLittleWorlds) project*
