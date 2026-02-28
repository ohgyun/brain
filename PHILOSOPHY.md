# Brain Philosophy

## Core Assumptions

When I designed Brain, I started with a few observations about how people make decisions.

First, I assumed that when someone makes a decision, they're guided by their core values and fundamental principles—whether they're consciously aware of them or not. These aren't arbitrary preferences; they're deep-seated beliefs about what matters.

Second, I noticed that these values and principles vary depending on the role someone is playing. You might hold the same fundamental beliefs, but apply them differently when you're an individual contributor versus when you're a leader. As a developer, you might prioritize pragmatism. As a founder, you might prioritize speed. It's not inconsistency—it's context-appropriate decision-making.

Third, I realized that even within the same role, the situation matters. You make different decisions on personal projects versus client work, on prototypes versus production systems. The role defines your values, but the project defines your constraints and priorities.

That's why Brain has two layers: **Role** (who you are) and **Project** (what matters here).

## The Problem of Tacit Knowledge

Here's the challenge: most of your decision-making principles are tacit knowledge.

You don't consciously think "I'm applying my pragmatist principle now." You just naturally choose to ship with basic tests instead of comprehensive coverage. The principle exists in your actions, not in your explicit awareness.

This creates a dilemma. Traditional systems ask you to articulate your values upfront. But that's asking you to make explicit what is inherently tacit. It's difficult, burdensome, and often incomplete.

More importantly, forcing upfront articulation misses a crucial insight: **your principles reveal themselves most clearly through your actual decisions, not through introspection.**

When you choose option A over option B, there's a value judgment embedded in that choice. When you make similar choices repeatedly, there's a pattern. That pattern is your principle—whether you've named it or not.

## Discovery Through Dialogue

This led to Brain's core approach: instead of asking users to declare their principles upfront, help them discover principles through practice.

The mechanism is conversations. Every conversation where you make decisions contains your principles in action. When you say "No, let's ship with basic tests first," you're revealing something about what you value.

Brain captures these decisions in logs. Over time, patterns accumulate. Then it analyzes these patterns and says: "You've prioritized shipping over perfection three times in similar situations. Is this a principle worth making explicit?"

This follows a natural learning process:
1. You act based on unconscious principles
2. Patterns emerge through repeated actions
3. You recognize the patterns
4. You make them conscious and explicit
5. You apply them deliberately in future decisions

In knowledge management theory, this is called the SECI model—converting tacit knowledge to explicit knowledge through practice and reflection. Brain systematizes this process.

## The Role of User Approval

Brain never auto-updates your values or rules. Every pattern that gets elevated to a principle requires your approval.

This isn't just a safety mechanism. It's a metacognitive process.

When Brain presents a pattern and asks "Is this your principle?", you're forced to examine your own thinking. You recognize the pattern consciously. You decide whether it truly reflects who you want to be. You take ownership of it explicitly.

This moment of conscious recognition is valuable in itself. It's not just about storing a preference in a system—it's about strengthening your self-awareness. You're transforming an unconscious habit into a deliberate principle.

## Evolution Over Configuration

People change. The developer you are today isn't the developer you were a year ago. Your principles evolve with experience.

Most systems treat preferences as static configuration: set it once, done. But that doesn't match reality.

Brain is designed to evolve:
- Start with minimal principles (or none)
- Capture decisions over time
- Discover patterns
- Elevate patterns to principles
- Continue capturing new decisions
- Discover new patterns
- Refine existing principles
- Repeat

The system grows as you grow. It reflects your current thinking, not your past assumptions.

This makes Brain less like a configuration file and more like a living system that evolves with you.

## The Ultimate Goal

What Brain aims to achieve is this: teach Claude how you think.

Not just what you prefer, but your entire decision-making framework:
- How you weigh trade-offs
- What you prioritize in different contexts
- What patterns guide your choices
- Which values you're willing to compromise and which ones you're not

With enough captured decisions and evolved principles, Claude should be able to make decisions aligned with your specific way of thinking—without you having to explain your preferences each time.

It's not about giving Claude a list of rules to follow. It's about replicating your decision-making DNA.

## Design Consequences

These philosophical choices led to specific design decisions:

**Minimalism:** If capturing decisions feels burdensome, you won't do it. So Brain removes all unnecessary structure. Templates are minimal. Placeholders are removed. "All sections optional." Write only what matters.

**Language Neutrality:** Your principles feel different in your native language. Brain writes values and rules in the language you're speaking, preserving the natural expression of your thoughts.

**Conservative Merging:** When Brain finds patterns, it has to judge: is "Ship fast" the same as "Ship working code fast"? They're similar, but are they identical? Only you can decide. So Brain detects obvious duplicates automatically but asks you to judge similarities.

**Logs as Primary Data:** Abstract principles lack context. "Practicality over perfection" means different things in different situations. Logs capture decisions with their full context—what situation you faced, what options you considered, what you chose, what you gave up. Principles are extracted FROM logs, not written in isolation. Context matters.

## What Brain Is

Brain is a system for converting tacit knowledge to explicit knowledge through practice.

It recognizes that:
- You make decisions differently in different roles
- Your principles are mostly unconscious
- Conversations reveal your values better than introspection
- Your decision-making framework should evolve as you grow

It helps you discover your own thinking patterns, make them explicit, and teach them to Claude.

The result is Claude that makes decisions aligned with your specific way of thinking—because it has learned your decision-making DNA.
