# Part 4 Writeup Boundaries: Pre-P3 vs Post-P3

## Classification Key

- **Pre-P3**: Content fully writable before P3 deliverable. No pre-p3/post-p3 split.
- **Hybrid**: Has both pre-P3 and post-P3 content. Split into `pre-p3/content.tex` and `post-p3/content.tex`.
- **Post-P3**: Entirely dependent on P3 deliverable or post-P3 runs. No pre-p3/post-p3 split.

---

## Summary Table

| Section | Subsection | Type | Pre-P3 Content | Post-P3 Content |
|---------|-----------|------|----------------|-----------------|
| 1. Introduction | — | Hybrid | Overview paragraph (A/B design, ablation structure) | Add C/D specifics, combined run outcome |
| 2. Reward Design | Opening | Pre-P3 | Design philosophy, complementarity | — |
| 2a | Reward A: Format Compliance | Pre-P3 | Definition, rationale, literature, alternatives | — |
| 2b | Reward B: Numeric Proximity | Pre-P3 | Definition, rationale, literature, complementarity | — |
| 2c | Reward C | Post-P3 | — | Full design (definition, rationale, literature) |
| 2d | Reward D | Post-P3 | — | Full design (definition, rationale, literature) |
| 3. Methodology | Opening | Pre-P3 | Ablation framing paragraph | — |
| 3a | Evaluation Metrics | Hybrid | All metric definitions, taxonomy reference | Update taxonomy if P3 adds categories |
| 3b | Experimental Setup | Pre-P3 | Checkpoint, RL config, infrastructure | — |
| 3c | Comparison Structure | Hybrid | Ablation table, comparison tiers, significance criteria | Fill C/D reward names in table |
| 4. Results | Opening | Pre-P3 | Orienting sentence | — |
| 4a | Summary | Hybrid | T1 + T2 tables (4 runs), commentary | Add C/D/Combined rows, update bold |
| 4b | Error Analysis | Hybrid | Taxonomy table, error distribution (4 runs), F1 + F2, commentary | Add C/D rows, regenerate figures |
| 4c | Training Dynamics | Hybrid | F3 + F4 + F5 (4 runs), commentary | Add C/D curves, update combined component analysis |
| 5. Discussion | Opening | Pre-P3 | Framing sentence | — |
| 5a | Per-Reward Impact | Hybrid | A and B analysis (accuracy, errors, gained/lost, dynamics) | Add C and D analysis paragraphs |
| 5b | Reward Interactions | Post-P3 | — | Synergy/interference from full combined run |
| 5c | Limitations | Pre-P3 | 6 limitation paragraphs | — |
| 6. Conclusion | — | Hybrid | (empty — written entirely post-P3) | Full conclusion paragraph |

---

## Requirement Coverage

| Req | Description | Fillable(s) |
|-----|-------------|-------------|
| R1 | Design ≥2 additional rewards | 2a (pre), 2b (pre), 2c (post), 2d (post) |
| R2 | Motivate from P3 error analysis | 2c (post), 2d (post) |
| R3 | Combined run: all rewards | 3c ablation table (pre), 4a summary (post) |
| R4 | Same config as original RL | 3b experimental setup (pre) |
| R5 | Compare combined vs original | 4a summary (post), 5b interactions (post) |
| R6 | Separate runs per reward | 3c ablation table (pre), 4a summary (pre+post) |
| R7 | Compare separate vs original and combined | 4a summary (pre+post), 5a per-reward (pre+post) |
| R8 | Classify mistakes | 4b error analysis (pre+post) |
| R9 | Compare mistake types | 4b error analysis (pre+post) |
| R10 | Comment on reward impact on mistakes | 5a per-reward impact (pre+post) |
| R11 | Visualizations | 4b F1+F2 (pre+post), 4c F3+F4+F5 (pre+post) |
| R12 | Summary table | 4a T1 (pre+post) |
| R13 | Commentary on each change | 5a per-reward impact (pre+post) |
| R14 | Literature justification | 2a (pre), 2b (pre), 2c (post), 2d (post) |
| R15 | W&B logging | 3b setup (pre), 4c dynamics (pre) |
| R16 | Clean reward code | 2a-2d code references (pre+post) |
| R17 | GSM8K accuracy | 4a summary (pre+post) |
| R18 | Failure mode distribution shifts | 4b error analysis (pre+post) |
| R19 | Reward interactions | 5b interactions (post) |

**Pre-P3 coverage**: R1 (partial: A,B), R4, R6 (partial), R7 (partial), R8 (partial), R9 (partial), R10 (partial), R11 (partial), R12 (partial), R13 (partial), R14 (partial), R15, R16 (partial), R17 (partial), R18 (partial)

**Post-P3 required for full coverage**: R1 (C,D), R2, R3, R5, R19 + completing partial items above
