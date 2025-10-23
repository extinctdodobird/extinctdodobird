# ARC Prize 2025 - Competition Requirements

## Official Details

### Competition Info
- **Platform:** Kaggle
- **Competition:** ARC Prize 2025
- **Dataset:** ARC-AGI-2 (new, harder version)
- **URL:** https://www.kaggle.com/competitions/arc-prize-2025
- **Prize Pool:** $600,000+ (Grand Prize unlocked at 85% accuracy)

### Key Dates
- **Competition Opens:** March 26, 2025
- **Team Merger Deadline:** TBD
- **Submission Deadline:** November 3, 2025
- **Our Target:** October 31, 2025 (safety buffer)

---

## Evaluation Format

### Task Structure
- **Total Tasks:** 240 previously unseen tasks
- **Semi-Private Set:** 120 tasks (for leaderboard during competition)
- **Private Set:** 120 tasks (for final ranking)
- **Execution Window:** 12 hours wall-clock time
- **No Internet Access** during execution

### Scoring Method
- **Metric:** Pass@2 (two attempts allowed per task)
- **Success:** Task marked correct if either attempt matches exactly
- **Score:** Percentage of tasks solved correctly
- **Grand Prize Threshold:** 85%+ on private set (204/240 tasks)

### Submission Format
```json
{
  "task_id_1": [
    [[attempt_1_grid]],
    [[attempt_2_grid]]
  ],
  "task_id_2": [
    [[attempt_1_grid]],
    [[attempt_2_grid]]
  ]
}
```

---

## Computational Constraints

### Hardware
- **GPUs:** 4x NVIDIA L4
- **Total GPU Memory:** 96GB (24GB per L4)
- **CPU/RAM:** Standard Kaggle notebook limits
- **Storage:** Standard Kaggle limits

### Performance Targets
- **Time Budget:** 12 hours / 240 tasks = **3 minutes average per task**
- **Efficiency Target:** ~$2.50/task for Grand Prize efficiency bonus
- **Compute Cost:** ~$0.42/task approximate limit

### Restrictions
- ❌ No internet access (no API calls to GPT/Claude/etc.)
- ❌ No pre-downloaded models that don't fit in notebook
- ✅ Can use any open-source libraries/models that fit
- ✅ Can pre-compute/pre-train models offline

---

## Data Format

### Input Format (JSON)
```json
{
  "train": [
    {
      "input": [[0,1,2], [3,4,5]],
      "output": [[5,4,3], [2,1,0]]
    }
  ],
  "test": [
    {
      "input": [[6,7,8], [9,0,1]]
    }
  ]
}
```

### Grid Properties
- **Values:** Integers 0-9 (representing colors)
- **Size:** Variable (typically 3x3 to 30x30)
- **Training Examples:** Usually 2-3 per task
- **Test Cases:** Usually 1-2 per task

---

## Competition Rules

### Open Source Requirement
- Teams must **open source their solutions** before receiving official private eval scores
- Code must be published publicly
- Enables community learning and verification

### Submission Requirements
- **Format:** Kaggle Notebook
- **Execution:** Must run end-to-end in Kaggle environment
- **Outputs:** Must match exact JSON schema
- **Validation:** Automated checking by Kaggle

### Team Rules
- Solo or team participation allowed
- Team mergers allowed until deadline
- Prize split among team members

---

## What Makes ARC-AGI-2 Hard

### Design Philosophy (Chollet)
1. **Novel tasks** - Never seen in training
2. **Few-shot learning** - Only 2-3 examples
3. **No shortcuts** - Can't memorize or pattern match
4. **True reasoning** - Requires abstraction and composition
5. **No neural advantage** - Pure LLMs score 0%

### Task Categories
- Object manipulation (move, rotate, scale)
- Pattern completion (fill missing parts)
- Counting and arithmetic
- Symmetry and spatial reasoning
- Color transformations
- Conditional logic
- Composition of multiple operations

### Difficulty Stats
- **Human Performance:** ~85% (with effort)
- **Pure LLMs (GPT-4, etc.):** 0% on ARC-AGI-2
- **2024 Winner (ARChitects):** 53.5% on ARC-AGI-1
- **Current SOTA:** Single-digit % on ARC-AGI-2

---

## Winning Strategies (2024 Evidence)

### What Worked
1. **Discrete Program Synthesis** - Enumerate and test programs
2. **Test-Time Training** - Fine-tune small models per task
3. **Hybrid Approaches** - Combine synthesis + neural
4. **Augmentation** - Test stability across transformations
5. **Ensembles** - Combine multiple solver strategies

### What Didn't Work
- Pure LLM prompting (0% accuracy)
- Large pre-trained models without adaptation
- Pure pattern matching approaches
- Memorization-based methods

### Key Insight
**40% (program synthesis) + 40% (test-time training) = 53%+ (ensemble)**

Different approaches solve different task types. Combining them wins.

---

## Our Strategic Advantage

### Why Discrete Search First
1. **Proven foundation** - Icecuber (2020) still competitive with pure synthesis
2. **No compute waste** - Efficient exploration of program space
3. **Interpretable** - Can understand and debug solutions
4. **Chollet-aligned** - Tests what the benchmark actually measures

### Why Start Simple
1. **8 days timeline** - Need working solution fast
2. **Beginner-friendly** - Easier to understand and improve
3. **Lower risk** - Less can go wrong
4. **Solid baseline** - Can add complexity if time allows

### Resource Efficiency
- 4xL4 GPUs = plenty for program search
- Most compute for parallel exploration
- Save GPU for small model fallback if needed
- Focus on algorithmic efficiency over scale

---

## Success Metrics

### Minimum Viable (40%+)
- Solves basic transformation tasks
- Handles object manipulation
- Processes symmetry/rotation tasks
- Completes within time limits

### Competitive (50%+)
- Handles complex compositions
- Robust to task variations
- Efficient ensemble of approaches
- Top 10% on leaderboard

### Prize-Winning (85%+)
- Near-human performance
- Generalizes to novel patterns
- Highly efficient (<$2.50/task)
- Grand Prize unlock

---

## References
- ARC Prize Official: https://arcprize.org/
- Kaggle Competition: https://www.kaggle.com/competitions/arc-prize-2025
- ARC-AGI-2 Paper: https://arxiv.org/html/2505.11831v1
- 2024 Technical Report: https://arxiv.org/html/2412.04604v1
