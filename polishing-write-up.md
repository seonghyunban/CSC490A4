# Agt1
## Intro
- Rename Introduction to Summary of Finding
- this section should give an high level understanding of what we did, and what we found and concluded
## Limitation 
- A single concise paragraph acknowledging the limitation (but limitatio of what? answer this first) this should be a separate section at the end before reference instead of part in the discussion.
## Reference
- Scan the tex file for all the citation, explicitly cited or implicitly cited, and add reference and link. Make sure to add the correct working reference link


<!------------------------------------->
# Agt2

## Reward
- the overview of reward design section should high level introduction to the kind of reward used, and based on what we ground or justified our choice (also high level)
- For each reward we chose, give two subsection: What is it and Why we chose it
- What is it should give definition, formal definition, interpretation (what does this reward suppose to mean?)
- Why we chose it should give clear honest justification that explains our reasoning as well as the grounding (literature / research). If there was alternative considered, but not selected, concisely explain why. If there is more advanced (and presume to be better) but not chosed, justify it as well. the key is Clarity and Transparency and Honesty. 
- If there is any interactions between reward, identify them and give a diagram to show this.

## Methodology
- rename Comparison tiers to Dimensions of Analysis
- Reorder this section as following: 
1. Ablation design
2. Evaluation Metrics
3. Dimensions of analysis
4. Significance Criteria
5. Experimental setup
- For ablation design and Dimension of analysis, 
A four-dimensional ablation analysis:                           
                                                                  
  1. Individual impact analysis — does each reward help on its    
  own? (accuracy deltas, gained/lost)
  2. Interaction analysis — do rewards help or hurt when combined?
   (synergy, interference, additivity)                          
  3. Failure mode distribution analysis — do rewards change what
  goes wrong? (error category shifts)
  4. Training dynamics analysis — how do rewards shape learning
  over time? (reward curves, components, sequence length)

  So the full picture is:
  - Ablation design = what we run (10 configurations varying
  reward composition)
  - Dimensions of analysis = how we evaluate the runs (4 lenses
  above)

  Together: we ran a reward ablation study and analyzed it along
  four dimensions.



<!------------------------------------->
# Agt3

## Result
Role: Present data. What happened?                              
                                                                  
  Four subsections, one per dimension:                            
  1. Individual Impact — Pass@1, Pass@8, extraction failure,    
  gained/lost tables
  2. Interaction Effects — Combined vs. constituent runs,
  additivity comparison
  3. Failure Mode Distribution — Error category table, category
  shifts across runs
  4. Training Dynamics — Reward curves, component breakdowns,
  sequence length trends

  No interpretation beyond direct observations from the data.

## Discussion
Role: Interpret data. What does it mean?

  Four subsections mirroring Results, plus limitations:
  1. Individual Impact — Why E > C > A > D > B, mechanisms behind
  each reward's effect
  2. Interaction Effects — Why A+B interferes, why C+D+E has
  widest gap, loss stability explanation
  3. Failure Mode Distribution — Format→reasoning shift as
  structural finding, what the residual errors reveal
  4. Training Dynamics — Why C peaks late, what sequence length
  trends indicate about learning
  5. Limitations — Scope, statistical rigor, reward hacking risk,
  taxonomy limitations

## Conclusion
Section 6: Conclusion

  Role: Synthesize across dimensions. What's the takeaway?

  No subsections. One cohesive narrative that connects findings
  across all four dimensions to answer: which rewards work, why,
  and what that tells us about RL reward design for math
  reasoning.
