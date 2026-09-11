2026-09-08 10:32

Tags: machine learning reinforcement learning PPO policy gradient

---

### General idea:

PPO has two neural networks:

- **Actor:** learns the policy — given a state, outputs probabilities for the possible actions.
    
- **Critic:** estimates how much future reward we can expect from a state.
    

We repeatedly:

1. Let the current actor interact with the environment and collect a **rollout**.
    
2. Store the states, actions, rewards, and the probability of each chosen action under the policy that generated the rollout.
    
3. Calculate the **reward-to-go** and the **advantage** for each timestep.
    
4. Train the critic to predict the reward-to-go.
    
5. Train the actor using the PPO objective.
    
6. Repeat with a new rollout.
    

The important idea behind PPO is:

> **Advantage tells the actor which direction to change the probabilities, and clipping limits how much the objective rewards changing them.**

---

### Rollouts and the old policy:

During a rollout, the actor is the policy that generated the experience. We therefore store:

$π_{old}(a_t∣s_t)\pi_{old}(a_t|s_t)$

This is the probability that the old actor gave to the action that was actually taken.

After collecting the rollout, we can update the actor multiple times using the same data.

The stored old probability stays fixed.

The updated actor produces a new probability:

$π_θ(a_t∣s_t)\pi_\theta(a_t|s_t)$

We compare them with the probability ratio:

$r_t(θ)=π_θ(a_t∣s_t)π_{old}(a_t∣s_t)r_t(\theta)= \frac{\pi_\theta(a_t|s_t)} {\pi_{old}(a_t|s_t)}$

For example, if the old probability was 0.25 and the new actor gives the action probability 0.30:

$r_t =\frac{0.30}{0.25}=1.2$

If later the actor gives it 0.40:

$r_t=\frac{0.40}{0.25}=1.6$

The old probability doesn't change. It is part of the stored experience.

---

### Advantage:

The advantage roughly tells us whether an action turned out better or worse than what the critic expected:

$A_t \approx \text{reward-to-go}_t - V(s_t)$

Positive advantage:

> This action was better than expected → increase its probability.

Negative advantage:

> This action was worse than expected → decrease its probability.

So:

> **Advantage tells us which direction to push the policy.**

(More sophisticated PPO implementations often calculate advantage using GAE.)

---

### PPO objective:

The actor uses the clipped objective:

$L^{CLIP}(\theta) = \mathbb{E}_t \left[ \min \left( r_t(\theta)A_t, \operatorname{clip}(r_t(\theta),1-\epsilon,1+\epsilon)A_t \right) \right]$

The scary-looking equation is basically doing three things:

**1. Ratio**

$r_t= \frac{\text{new probability}} {\text{old probability}}$

This tells us how much the policy changed.

**2. Advantage**

$r_tA_t$

This determines whether changing the probability in that direction is good or bad.

**3. Clipping**

With e.g.

$\epsilon=0.2$

the ratio is clipped to:

$[0.8,1.2]$

This does **not** hard-limit the network's probabilities to this range. It changes the objective so that excessively large policy changes stop being rewarded.

So the intuition is:

> **Advantage says where to go; clipping limits how far you're rewarded for going.**

---

### Why the min?

We calculate both:

$r_tA_t$

and

$\operatorname{clip}(r_t,1-\epsilon,1+\epsilon)A_t$

and take the smaller one.

This makes PPO conservative.

For a positive advantage, increasing the probability is good, but once the ratio goes above $1+\epsilon$, we stop rewarding further increases.

For a negative advantage, decreasing the probability is good, but once the ratio goes below $1-\epsilon$, we stop rewarding further decreases.

The clipping therefore prevents the actor from getting an artificially large objective by making an excessively large policy change.

It is a **soft constraint in the objective**, not a hard guarantee that the policy cannot move outside the clipping range.

---

### What does $\mathbb{E}_t$ mean?

It basically means:

> **Average this over the sampled timesteps.**

If we have 10,000 timesteps:

$L^{CLIP} = \frac{1}{10000} \sum_{t=1}^{10000}L_t$

In practice we usually work with a minibatch, e.g. 256 timesteps:

$L_{\text{minibatch}} = \frac{1}{256} \sum_{t=1}^{256}L_t$

So we calculate one PPO score for every timestep and then average them into **one scalar objective**.

---

### Objective vs. loss:

The PPO objective is something we want to **maximize**.

This is similar to a normal neural-network loss in the sense that it is the scalar we differentiate and optimize, except that here we want it to become larger.

Since neural-network optimizers are commonly used as minimizers, implementations often use:

$L_{\text{actor}}=-L^{CLIP}$

So maximizing the PPO objective is equivalent to minimizing its negative.

It is important that this is **not literally the total reward**. It is a surrogate objective designed to improve the policy using the collected experience.

---

### Actor update:

Once we have the average PPO objective, the rest is just normal neural-network optimization:

$L^{CLIP} \rightarrow \text{gradient} \rightarrow \text{backpropagation} \rightarrow \text{optimizer} \rightarrow \text{actor weights}$

The actor isn't directly told "increase this output by X."

The PPO objective creates a gradient that tells the network which parameter changes would improve the policy according to the collected experience.

Conceptually:

$\boxed{ \text{rollout} \rightarrow A_t,\pi_{old} \rightarrow r_t \rightarrow L^{CLIP} \rightarrow \text{average} \rightarrow \text{gradient} \rightarrow \text{actor update} }$

---

### Training cycle:

A typical PPO cycle looks roughly like:

**Collect rollout**

→ e.g. 10,000 timesteps using the current policy

**Calculate**

→ reward-to-go  
→ value estimates  
→ advantages  
→ old action probabilities

**Split into minibatches**

→ e.g. batches of 256

**Train**

→ run several epochs over the same rollout  
→ calculate new action probabilities  
→ calculate PPO objective  
→ backpropagate  
→ update actor and critic

**Discard old rollout**

→ collect fresh experience with the updated policy

The minibatches don't need to correspond to individual episodes. Once the necessary quantities have been calculated, timesteps from different episodes can be mixed together.

---

### Mental model:

**Actor:**

> "What should I do in this state?"

**Critic:**

> "How good do I think this state is?"

**Advantage:**

> "Was the action we actually took better or worse than expected?"

**Probability ratio:**

> "How much did the new policy change the probability of that action?"

**Clipping:**

> "Don't let the objective reward an excessively large change."

**PPO objective:**

> "Overall, how good is this proposed policy update across my sampled experience?"

**Optimizer:**

> "Change the actor's weights so that this objective gets better."

---

![[Pasted image 20260908122700.png]]

### References

[https://arxiv.org/abs/1707.06347](https://arxiv.org/abs/1707.06347)
[Simply Explaining Proximal Policy Optimization (PPO) | Deep Reinforcement Learning - YouTube](https://www.youtube.com/watch?v=5VHLd9eCZ-w&t=1123s)