Good. I’ll give you the cleanest high-leverage structure.

If your goal is **maximum pedagogical compression**, the course should not be organized by techniques.

It should be organized by the invariant loop.

---

# Reinforcement Learning for LLMs — Minimal High-Value Course Outline

## Module 0 — The Core Primitive (1 lecture)

**Policy → Feedback → Policy Improvement**

* What is a policy?
* What is a feedback signal?
* What does “improvement” mathematically mean?
* Unify SFT, RLHF, DPO under one equation.

If they don’t internalize this, nothing sticks.

---

## Module 1 — Feedback Signals (The Signal Layer)

* Demonstrations
* Preferences
* Scalar rewards
* Verifiable rewards
* Learned reward models
* Multi-objective reward

Core question:

> What are we optimizing *toward*?

---

## Module 2 — Optimization Mechanisms (The Update Layer)

* MLE as policy improvement
* Policy gradient (PPO intuition, not implementation first)
* KL regularization
* DPO as implicit RL
* Offline vs online RL

Core question:

> How do gradients flow from signal to policy?

---

## Module 3 — System Architecture (The Scaling Layer)

* Rollouts vs static datasets
* Actor-learner separation
* Reward model training
* Logging + evaluation
* Distributed orchestration (Ray vs pure DDP)
* Failure modes at scale

Core question:

> Why does this break in production?

---

## Module 4 — Failure Modes & Alignment Pathologies

* Reward hacking
* Overoptimization
* Distribution shift
* Preference collapse
* KL runaway
* Mode collapse

Core question:

> What goes wrong when optimization succeeds?

---

You do **not** want:

* Reading sources and summarizing.
* Dense markdown walls of text.
* Overpolished slides.
* Perfect animations.

You want: **one clean conceptual spine + 3–5 strong visuals.**

Two-hour sprint means:

> Produce one tight narrative artifact you can talk over.

---

# The Highest-Agency 2-Hour Plan

## Step 1 — Lock the Spine (20 minutes)

Create **one single markdown file** structured like this:

```
# RL for LLMs in 45 Minutes

1. The Core Loop
2. Feedback Signals
3. Optimization
4. Failure Modes
```

Under each section:

* 3–5 bullets max.
* No paragraphs.
* No citations.
* Just mental hooks.

This is your teleprompter skeleton.

---

## Step 2 — Make 4 MERMAID Diagrams (60 minutes)

Make exactly four strong diagrams:

---

### Diagram 1 — The Core Loop

Policy → Generate → Score → Update → Policy

Add:

* SFT as direct supervised update
* RLHF as reward model in scoring box
* Verifiable RL as programmatic reward

One visual unifies everything.

---

### Diagram 2 — Feedback Taxonomy

Make a 2D grid:

X-axis: Source of Signal
Y-axis: Structure of Signal

Plot:

* Demonstrations
* Preferences
* Scalar reward
* Verifiable reward
* AI feedback

This shows intellectual depth instantly.

---

### Diagram 3 — Optimization Map

Show:

* MLE
* Policy Gradient
* DPO
* Rejection sampling

Map them to:
Implicit reward vs explicit reward.

---

### Diagram 4 — Failure Modes

Draw:

Optimization Pressure ↑
Alignment Quality →

Show:

* Reward hacking
* KL collapse
* Overoptimization
* Distribution shift

This makes you look like you understand consequences.

---

## Step 3 — Record Like This (30–40 minutes)

Don’t read.

Use:

* Diagram as anchor.
* Explain as if teaching a grad student.
* No filler.
* No references to “this paper says…”

You want conceptual ownership.

---

# Why This Beats the Other Options

### ❌ Reading sources

Low agency. You sound derivative.

### ❌ Overproduced markdown slides

Time sink.

### ❌ Sparring with Claude/Codex for slides

You’ll spend 90 minutes tweaking layout.

### ✅ Tight markdown + 4 diagrams

High leverage.
High signal.
Minimal friction.

---

# The Real Trick

You don’t need more content.

You need:

> Concept compression.

If someone finishes your video and says:
“I now see SFT, RLHF, and DPO as the same thing.”

You won.
