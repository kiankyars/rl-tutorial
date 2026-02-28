## 1. The Core Loop

- Every post-training method is the **same loop**: Policy → Behavior → Feedback → Update
- **SFT**: feedback = demos (x,y), update = MLE
- **RLHF**: feedback = prefs → reward model, update = PPO + KL
- **DPO**: feedback = prefs, update = implicit RL (no RM needed)
- Three axes of variation: source of feedback, structure of signal, optimization rule
- There are NOT 10 methods. There is ONE loop.

## 2. Feedback Signals

- **Demonstrations** — human writes the ideal output (SFT)
- **Preferences** — human picks winner from pair (RLHF, DPO)
- **Scalar reward** — learned RM assigns score (classic RLHF)
- **Verifiable reward** — programmatic check, e.g. math correctness (DeepSeek-R1, GRPO)
- **AI feedback** — LLM-as-judge (constitutional AI, RLAIF)
- Key insight: richer signal ≠ better. Verifiable > learned when available.

## 3. Optimization

- **MLE** — maximize log p(y|x) on gold data. Simplest. No exploration.
- **Policy gradient (PPO)** — sample from policy, score, reinforce good trajectories. KL penalty keeps you near base.
- **DPO** — rewrite the RL objective so reward is implicit in policy logits. No RM, no sampling loop.
- **Rejection sampling / Best-of-N** — generate N, keep best. Offline. Simple but wasteful.
- **GRPO** — group relative policy optimization. No critic, normalize rewards within batch.
- Online vs offline: online = fresh rollouts, offline = static dataset. Online sees its own mistakes.

## 4. Failure Modes

- **Reward hacking** — policy exploits RM quirks, RM score ↑ but quality ↓
- **Overoptimization** — too many gradient steps against proxy reward
- **KL collapse** — KL penalty too weak → policy drifts far from base, loses coherence
- **Mode collapse** — policy converges to one "safe" style, loses diversity
- **Distribution shift** — RM trained on base policy outputs, but policy has moved
- **Preference collapse** — annotators disagree, model learns average = bland

## Closing Hook

> If you leave with one thing: SFT, RLHF, and DPO are not different paradigms.
> They are the same loop with different feedback and different update rules.
