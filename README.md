<div align="center">

# Evolving with Open Worlds: Towards Recursive Self-Improvement for Future Forecasting [![Paper](https://img.shields.io/badge/Paper-PDF-b31b1b.svg)](sn-article.pdf)

<!-- [![License](https://img.shields.io/badge/License-MIT-blue.svg)](#license) -->


</div>

> **Prometheus** brings us the fire from the changing world, **Branchus** dares to glimpse its future, and **Athena** teaches us to grow from what we have seen. \
> Thus begins the endless journey of self-evolution.

## Content
- [Overview](#overview)
- [The Three Modules](#the-three-modules)
- [The Core Idea: Co-evolving Three Levers](#the-core-idea-co-evolving-three-levers)
- [Key Insights](#key-insights)
- [Quick Start](#quick-start)
- [Resources](#resources)

## Overview

Most AI systems ship with frozen parameters and improve only through external updates. **DeepEvolve** studies the opposite setting — **recursive self-improvement (RSI)**, where an agent keeps growing stronger from its own experience — in the concrete and demanding domain of **real-world event forecasting**.

Forecasting is a natural testbed for RSI because it is:

- **Grounded** in the unfolding world rather than a hand-constructed dataset;
- **Verifiable** through future events whose objective ground truth arrives with time;
- **Non-stationary**, because the world keeps changing.

Together these properties close the loop recursion requires: the agent predicts, receives outcomes, and sharpens its next predictions. DeepEvolve formalizes this as a **closed loop of three modules** in which the agent and its environment co-evolve, so that a stronger agent continually meets a more demanding environment.


## The three modules

DeepEvolve is a closed loop, not a feed-forward pipeline.

### 🔥 Prometheus — a living data environment
Continually ingests real-world news to form a non-stationary, verifiable world. It builds short-horizon prediction questions through **template-based generation** (source-specific adapters over calendars, schedules, and feeds) and **agent-driven open discovery**, spanning sports, economics, monetary policy, energy, weather, public health, technology, government affairs, and cryptocurrency. A three-stage pipeline — temporal validation, deduplication & conflict detection, and diversity-aware selection — publishes each batch. Ground truth is revealed only once events resolve, so **time, not human annotation, supplies supervision**.

### 🌿 Branchus — an agentic forecaster
Produces predictions together with their full trajectories. Its policy is factored into two cooperating teams:

- A **search team** (scheduler, searcher, critic) gathers and vets evidence. It is **time-sensitive** — the same search yields different results depending on when it runs.
- A **predict team** reasons over the search team's *cached* evidence to issue a calibrated probabilistic forecast. It is **time-invariant** — given the same evidence it produces the same forecast.

This **search–prediction decoupling** is what lets forecasting data be trained on at all: a question loses its training signal once it resolves, but freezing the evidence available at forecast time keeps the reward verifiable. Branchus also draws on a layered **skill repository** — hand-authored seed skills plus experience-distilled skills, each a four-level tuple ordered from abstract principle to concrete procedure.

### 🦉 Athena — a recursive-evolution engine
Turns Branchus's trajectories back into capability through three operators:

- **Φ_rl** (parameter level): reinforcement learning on predictions to update weights;
- **Φ_skill** (behavior level): distilling reusable forecasting skills without touching the weights;
- **Φ_env** (environment level): converting observed failures into task-synthesis skills that steer Prometheus toward the agent's weaknesses.

The loop closes when Athena's improvements strengthen Branchus, whose stronger forecasts place new demands on Prometheus, pushing the environment to evolve.


## The core idea: co-evolving three levers

Prior work on self-improvement usually pushes a single lever — the model's weights, its prompts, or its memory. DeepEvolve argues that *sustainable* improvement comes from co-evolving **three** levers from one shared substrate — the forecasting **trajectories** the agent produces:

| Lever | What evolves | How |
|---|---|---|
| **Parameters** | the policy weights `θ` | reinforcement learning (RLVR / GRPO) on verifiable rewards |
| **Skills** | an explicit, reusable skill library `S` | distilling reasoning trajectories into procedural knowledge |
| **Environment** | the task distribution `E` | synthesizing harder, weakness-targeted questions |

One round of recursive self-improvement maps the system state `Σ⁽ᵗ⁾ = (θ⁽ᵗ⁾, S⁽ᵗ⁾, E⁽ᵗ⁾)` to `Σ⁽ᵗ⁺¹⁾`, making the products of one round the raw materials of the next. The triple co-evolves rather than converging to a fixed set of weights.



## Key Insights

- Recursive evolution lifts DeepEvolve to the strongest forecasting system
- Search-prediction decoupling adapts RFT and RLVR to contamination-prone live environments
- Evolving skills unlock recursive self-improvement from fleeting live trajectories
- Skill evolution guides evidence gathering while parameter evolution sharpens evidence use
- An evolving environment continuously turns the agent's own failures into adversarial challenges
- A targeted and challenging environment drives sustained system evolution


## Quick Start



## Resources

We introduce the resources used in our paper, including information sources for discovering real-world events and archived FutureX Overall leaderboard snapshots for tracking forecasting performance.

- [Website Resources](resources/Websites.md): a catalog of 125 information sources across five domains, including science and technology, public affairs, business and finance, culture and sports, and energy and the environment.
- [FutureX Overall Leaderboard snapshots](resources/FutureX%20Leaderboard/): archived leaderboard pages captured on August 17, August 26, and September 3 and 7, 2026.