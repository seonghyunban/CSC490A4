# Cross-Part Coherence Review — CSC490 A4

## 1. What to Fix (Part 3)

### Part 3 changes pushed to the wrong branch

Part 3 changes were pushed to the `a3` branch. TAs may not have marked A3 yet, so modifying that branch may pollute the marking process. Let's make it clean, part 3 edits should live on a separate branch created from `a4`.

**Example fix:** Revert Part 3 changes from `a3`, create a new branch off `a4`, and apply the fixes there.

---

### Potential use of non-Karpathy-default for decoding method

Part 3 reports 17.89% strict accuracy (p.12) but never states it used greedy decoding (temperature=0.0). Part 4 uses temperature=1.0 (Karpathy's default) on the same checkpoint and gets 9.7% Pass@1. The gap is entirely due to decoding method, but Part 3 doesn't say this.

**Example fix:** Add one sentence to §3.1 stating that offline evaluation used greedy decoding (temperature=0.0), which differs from Karpathy's default of temperature=1.0.

---

### Error analysis lacks quantitative grounding

Part 3's error analysis (§3.3, pp.15-16) describes five error categories but gives no counts, percentages, or examples. The assignment asks to "cluster these problems and answers into different categories and conduct some exploratory data analysis." 

**Example fix:** Add counts and percentages to §3.3's error categories, or forward-reference Part 4 §4.2 which provides the full quantitative taxonomy on the same checkpoint. Or, point to part 4.

---

### Missing parseable rate

Part 2 reports 88.93% parseable (p.10). Part 4 reports 39.7% parseable on the RL baseline (p.17). Part 3 sits between these two stages but never reports this metric, even though the eval script already computes it.

**Example fix:** Add a fourth bullet to §3.1 reporting the parseable rate, which the eval script already computes but Part 3 never surfaces. Or, point to part 4.

---

### Degenerate output frequency understated

Part 3 (p.16) calls degenerate outputs "less frequent than ordinary reasoning mistakes." Part 4 data (p.17) shows degenerate text at 32.8% of baseline responses — the second-largest failure mode.

**Example fix:** Ground your assesment, or remove the "less frequent" claim in §3.3 or replace it with a forward-reference to Part 4's quantification (32.8% degenerate text).

---

### BPB reported without interpretation

Part 3 lists BPB = 3.4418 (p.12) with no explanation. BPB measures general text compression efficiency — a language modeling metric, not an RL metric. Part 2 reports BPB between 0.78 and 1.52, but Part 3 never explains why it jumped to 3.44 or whether that matters for GSM8K.

**Example fix:** Either remove BPB from §3.1's bullet list, or add one sentence explaining what it shows in the context of part 3.

---

## 2. What is Covered by Part 4

### Use of default decoding method

Part 4 uses temperature=1.0 (Karpathy's default). Part 3 uses greedy without saying so. Part 4 §4.4.5 (p.24) lists its temperature setting and §4.2.2 (p.18) explains why its numbers differ from Part 2/3.

**Part 3 doesn't need to explain the 17.89% vs 9.7% discrepancy.** Part 4 already covers it. Part 3 just needs one sentence: "we used greedy decoding."

---

### Qualitative error analysis without data

Part 3's error analysis (pp.15-16) describes error types in prose with no numbers. Part 4 EDA (pp.17-19) provides the quantitative version: 6-category taxonomy with counts and percentages (Table 9), reward hacking analysis (Figure 15). Part 3's five categories roughly map to Part 4's six.

**Part 3 doesn't need to redo the analysis.** Part 4 §4.2 (Tables 8-9, pp.18-19) provides the full quantitative taxonomy on the same checkpoint.

---

### Parseable rate regression after RL

Parseable rate drops from 88.93% (Part 2 SFT, p.10) to 39.7% (Part 4 RL baseline, p.17). Part 4 (p.18) attributes this to temperature=1.0 sampling and the absence of KL regularization.

**Part 3 doesn't need to address this.** Part 4 §4.2 explains the cause and designs rewards to fix it.

---

### Cross-method accuracy not directly comparable

Part 2 reports 15.39% strict accuracy under greedy (p.10); Part 4 reports 9.7% Pass@1 under temp=1.0 (p.17). Different decoding methods make these numbers not directly comparable. Part 4 (p.18) states this explicitly.

**Part 3 doesn't need to explain this gap.** Part 4 §4.2.2 (p.18) already does. Part 3 only needs to disclose its decoding method (see "Undisclosed decoding method" above).

---

### Pass@k gap reframed as extraction failure

Part 3 (p.16) attributes the pass@8 >> pass@1 gap to "sample-to-sample instability." Part 4 (pp.17-18) shows the real driver is extraction failure — most failed samples lack a parseable answer, not wrong reasoning.

**Part 3 doesn't need to revise its framing.** Part 4 §4.2 provides the deeper explanation; Part 3's "instability" interpretation is compatible and gets refined later.

---

### RL improvement magnitude unspecified

Part 3 (p.16) says RL "improve[s] performance beyond the earlier reproduced Karpathy baseline" without quantifying how much. Part 4 (p.25) provides exact numbers across all 10 configurations.

**Part 3 doesn't need to quantify the improvement.** Part 4 §4.5 (p.25) provides the exact numbers.
