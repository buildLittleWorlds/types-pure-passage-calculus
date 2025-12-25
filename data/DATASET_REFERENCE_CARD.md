# Dataset Reference Card: The Pure Passage Calculus

## Quick Reference

All datasets load from the central repository:
```python
BASE_URL = "https://raw.githubusercontent.com/buildLittleWorlds/densworld-datasets/main/data/"
df = pd.read_csv(BASE_URL + "dataset_name.csv")
```

---

## Datasets

### passage_calculus_expressions.csv
**Rows:** 150 | **Primary Key:** expression_id

Mund's catalog of fundamental passage expressions.

| Column | Type | Description |
|--------|------|-------------|
| expression_id | string | Unique identifier (PCE-001, etc.) |
| expression_name | string | Mund's name for this passage |
| lambda_notation | string | Formal notation (e.g., "λx.x") |
| mund_notation | string | Densworld notation (e.g., "passage(x).x") |
| expression_type | string | identity, combinator, numeral, boolean, pair, list, arithmetic, other |
| bound_variables | string | Semicolon-separated list |
| free_variables | string | Semicolon-separated or "none" |
| complexity_depth | int | Nesting depth |
| year_documented | int | 3-digit Densworld year |
| documented_by | string | Scholar name |
| source_manuscript | string | Manuscript reference |
| notes | string | Additional context |

**Key expressions:** Identity (PCE-001), Omega (PCE-022), Y Combinator (PCE-023), Church numerals (PCE-005 to PCE-010)

---

### passage_reductions.csv
**Rows:** 200 | **Primary Key:** reduction_id + step_number

Step-by-step reduction traces showing how passages simplify.

| Column | Type | Description |
|--------|------|-------------|
| reduction_id | string | Unique identifier (PR-001, etc.) |
| initial_expression | string | Starting expression |
| step_number | int | Step in sequence |
| rule_applied | string | alpha, beta, eta, none |
| expression_after | string | Expression after step |
| redex_location | string | Where reduction occurred |
| is_normal_form | bool | True if final step |
| terminates | bool | True if sequence ends |
| total_steps | int | Total steps (on final step) |
| year_traced | int | 3-digit year |
| traced_by | string | Scholar name |
| notes | string | Context |

**Key traces:** Identity application (PR-001), Omega non-termination (PR-009), Church arithmetic (PR-013)

---

### church_encodings.csv
**Rows:** 50 | **Primary Key:** encoding_id

Church numeral and boolean representations.

| Column | Type | Description |
|--------|------|-------------|
| encoding_id | string | Unique identifier (CE-001, etc.) |
| encoded_value | string | What this represents (0, 1, TRUE, SUCC, etc.) |
| encoding_type | string | numeral, boolean, arithmetic, pair, list, other |
| lambda_notation | string | Formal notation |
| mund_notation | string | Densworld notation |
| verification_expression | string | Expression demonstrating correctness |
| year_discovered | int | 3-digit year |
| discovered_by | string | Scholar name |
| notes | string | Context |

**Key encodings:** Zero (CE-001), TRUE/FALSE (CE-012/CE-013), SUCC (CE-021), Pairs (CE-031-033), Lists (CE-034-042)

---

### great_collapse_records.csv
**Rows:** 75 | **Primary Key:** record_id

Archive malfunction logs from Year 720's Great Categorical Collapse.

| Column | Type | Description |
|--------|------|-------------|
| record_id | string | Unique identifier (GCR-001, etc.) |
| timestamp | string | Date/time (720-03-14 through 720-03-17) |
| incident_type | string | reclassification, circular_citation, index_loop, hierarchy_inversion |
| affected_document | string | Document ID or description |
| original_classification | string | Before collapse |
| collapse_classification | string | During collapse |
| restored_classification | string | After recovery or "irrecoverable" |
| archive_section | string | Where incident occurred |
| witness | string | Archivist who documented |
| severity | string | minor, moderate, severe, catastrophic |
| notes | string | Context |

**Key incidents:** First circular citation (GCR-001), Taxonomy collapse (GCR-017), Total inversion (GCR-024)

---

### fixed_point_observations.csv
**Rows:** 40 | **Primary Key:** observation_id

Self-referential passages and their behaviors.

| Column | Type | Description |
|--------|------|-------------|
| observation_id | string | Unique identifier (FPO-001, etc.) |
| expression_name | string | Name of self-referential passage |
| lambda_notation | string | Formal notation |
| behavior | string | terminates, cycles, diverges |
| reduction_length | int | Steps before termination (-1 for divergence) |
| pattern_detected | string | Cycle description if applicable |
| dens_proximity | string | stable_region, boundary, dens_adjacent |
| year_observed | int | 3-digit year |
| observer | string | Scholar name |
| risk_assessment | string | low, moderate, high, catastrophic |
| notes | string | Context, Dens parallels |

**Key observations:** Omega (FPO-001), Y Combinator (FPO-003), Collapse patterns (FPO-026-028)

---

### mund_correspondence.csv
**Rows:** 60 | **Primary Key:** letter_id

Letters between Mund, Vance, and colleagues spanning 78 years.

| Column | Type | Description |
|--------|------|-------------|
| letter_id | string | Unique identifier (MC-001, etc.) |
| date | string | 3-digit year format (725-03-12) |
| sender | string | Writer |
| recipient | string | Receiver |
| primary_topic | string | Main subject |
| related_manuscript | string | Manuscript referenced |
| tone | string | collegial, argumentative, reflective, urgent |
| key_passage | string | Notable quote |
| significance | string | routine, notable, breakthrough, foundational |
| notes | string | Context |

**Key correspondence:** Theory proposal (MC-007), Church numerals (MC-025), Y combinator (MC-040), Death announcement (MC-060)

---

## Timeline

| Year | Event |
|------|-------|
| 720 | Great Categorical Collapse; Mund joins Archive |
| 722 | Pure Passage Calculus proposed |
| 725 | Jorell Vance begins correspondence |
| 731 | *The Passage Calculus* treatise completed |
| 738 | Church numerals discovered |
| 745 | Vance proposes SKI combinators |
| 752 | Fixed points and Y combinator discovered |
| 755 | Omega non-termination observed |
| 762 | Mund becomes Director |
| 780 | Brennis Mund appointed to Committee |
| 792 | Kelleth Mund retires |
| 798 | Kelleth Mund dies |

---

## Common Queries

### Find all identity-type expressions
```python
expressions = pd.read_csv(BASE_URL + "passage_calculus_expressions.csv")
identities = expressions[expressions['expression_type'] == 'identity']
```

### Trace a specific reduction
```python
reductions = pd.read_csv(BASE_URL + "passage_reductions.csv")
trace = reductions[reductions['reduction_id'] == 'PR-013'].sort_values('step_number')
```

### Find divergent fixed points
```python
fixed_points = pd.read_csv(BASE_URL + "fixed_point_observations.csv")
divergent = fixed_points[fixed_points['behavior'] == 'diverges']
```

### Collapse incidents by severity
```python
collapse = pd.read_csv(BASE_URL + "great_collapse_records.csv")
collapse.groupby('severity').size()
```

### Breakthrough correspondence
```python
letters = pd.read_csv(BASE_URL + "mund_correspondence.csv")
breakthroughs = letters[letters['significance'] == 'breakthrough']
```

---

## Key Scholars

| Scholar | Years | Role |
|---------|-------|------|
| Kelleth Mund | 720-798 | Founder of Pure Passage tradition |
| Jorell Vance | 745-812 | Proposed combinatory alternative |
| Brennis Mund | 780-862 | Added types to passages |
| Torrel Goss | — | Classification Integrity Committee founder |
| Menna Krey | — | Committee member, early skeptic |
| Marden Krey | — | Consistency critic |
