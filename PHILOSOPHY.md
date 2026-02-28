# Brain: Background & Philosophy

## The Core Insight

**People don't make decisions the same way in every context.**

The same person will make different decisions depending on their role and situation:

- As an **employee**, you consult with the team before acting
- As a **founder**, you ship first and iterate based on feedback
- As a **developer**, you prioritize working code over perfect architecture
- As a **designer**, you prioritize user experience over implementation speed

This isn't inconsistency—it's **context-appropriate decision-making**.

Brain is built on the recognition that you are not one person with one decision-making framework. You are multiple roles, each with its own values, constraints, and priorities.

## The Problem: Tacit Knowledge

Most of your decision-making principles are **unconscious**.

You don't think "I'm applying my pragmatist principle now." You just naturally choose to ship with basic tests instead of comprehensive coverage. The principle emerges through your actions.

**Traditional approach:**
1. Sit down and write your principles
2. Hope you remember them all
3. Try to be consistent

**The problem:**
- You might not be aware of all your principles
- Forcing upfront articulation feels burdensome
- Principles evolve with experience

## Brain's Approach: Discovery Through Dialogue

Brain assumes your principles **reveal themselves naturally in conversation**.

### The Flow

```
1. You have conversations with Claude
   └─ Decisions emerge naturally
      "No, let's ship with basic tests first"

2. /brain-log captures the session
   └─ What you decided and why

3. /brain-update analyzes patterns
   └─ "You've prioritized shipping over perfection 3 times"

4. You review and approve
   └─ "Yes, that IS my principle as a Developer"

5. Principle becomes explicit
   └─ Added to Developer role's values

6. Claude applies it next time
   └─ Makes decisions the way YOU would
```

### From Tacit to Explicit

This is a **knowledge conversion process**:

- **Tacit knowledge**: The unconscious principles guiding your decisions
- **Socialization**: Principles emerge through dialogue with Claude
- **Externalization**: Patterns captured in logs
- **Combination**: Patterns elevated to formal rules/values
- **Internalization**: Claude applies these rules in future decisions

Brain doesn't ask you to know yourself perfectly upfront. It helps you **discover yourself through practice**.

## Layers of Context

Brain recognizes two layers of decision-making context:

### Role: "Who am I in this conversation?"

**Definition:** The identity and responsibilities you're assuming

**Examples:**
- Developer: "Ship working code over perfect design"
- Founder: "Speed over consensus"
- Product Manager: "User value over technical elegance"

**Key insight:** Same person, different roles, different core values

### Project: "What matters in this specific situation?"

**Definition:** The constraints and priorities of the current context

**Examples:**
- Personal project: "Learning over shipping"
- Client work: "Completeness over speed"
- Prototype: "Speed over quality"

**Key insight:** Even within the same role, priorities shift based on situation

### Why Both?

```
Developer role + Personal project:
"Try the experimental approach, learning matters more than stability"

Developer role + Client project:
"Use the proven approach, reliability matters more than learning"
```

The combination creates nuanced, context-appropriate decisions.

## Evolution, Not Configuration

Brain is not a static settings file. It's a **living system that evolves with you**.

### Traditional Systems

```
1. Set preferences upfront
2. Use system
3. Preferences stay fixed
```

### Brain

```
1. Start with minimal values (or none)
2. Have conversations
3. Capture meaningful decisions
4. Discover patterns
5. Elevate to principles
6. Repeat → System grows with you
```

**Why this matters:**
- Your principles change as you gain experience
- You discover new principles through new situations
- The system reflects your current thinking, not past assumptions

## User Approval: A Conscious Choice

Brain never auto-updates your values or rules. You must review and approve changes.

**Why?**

This isn't just a safety mechanism—it's a **metacognitive process**.

When Brain suggests:
> "You've prioritized practicality over perfection in 3 recent decisions.
> Add this to your Developer values?"

You're forced to:
1. Recognize the pattern consciously
2. Decide if it's truly your principle
3. Own the decision explicitly

This moment of conscious recognition **strengthens your self-awareness**. The act of approval transforms an unconscious habit into a deliberate principle.

## The Goal: Replicate Your Decision-Making DNA

Brain's ultimate aim is to teach Claude **how you think**.

Not just what you prefer, but:
- How you weigh trade-offs
- What you prioritize in different contexts
- How you approach uncertainty
- What patterns guide your choices

Over time, with enough captured decisions and evolved principles, Claude should be able to:

**Predict your thinking:**
"Given your Developer values and this project's constraints, you'd probably choose X because Y."

**Explain in your terms:**
"Based on your principle of 'practicality over perfection', let's ship with basic coverage."

**Make decisions you'd agree with:**
Not generic advice, but decisions aligned with your specific decision-making framework.

## Design Principles

These philosophical insights led to specific design choices:

### 1. Minimalism

**Philosophy:** Lower the barrier to capturing insights.

**Implementation:**
- Templates are minimal
- Placeholders removed
- "All sections optional"
- Write only what matters

**Why:** If capturing decisions feels burdensome, you won't do it. Friction kills adoption.

### 2. Language Neutrality

**Philosophy:** Principles are most authentic in your native language.

**Implementation:**
- Write values/rules in conversation language
- Templates in English, content in user's language
- Preserves natural expression

**Why:** Translating your inner principles loses nuance. "실용성" isn't quite "practicality."

### 3. Conservative Merging

**Philosophy:** Only obvious duplicates auto-merge; similarities need human judgment.

**Implementation:**
- AI detects clear duplicates
- User decides on similar items
- Never auto-modify without approval

**Why:** Subtle differences in principles matter. "Ship fast" ≠ "Ship working code fast."

### 4. Logs as Primary Data

**Philosophy:** Decisions in context are richer than abstract principles.

**Implementation:**
- Capture decisions with situation/options/trade-offs
- Principles extracted FROM logs
- Logs remain source of truth

**Why:** "Practicality over perfection" means different things in different situations. Context matters.

## Summary

Brain is based on four core beliefs:

1. **Context shapes decisions**: You think differently as Developer vs. Founder, in personal vs. client projects
2. **Principles are unconscious**: They emerge through action, not introspection
3. **Discovery through dialogue**: Conversations reveal your values better than forced articulation
4. **Evolution over configuration**: Your decision-making framework grows and changes with you

The system creates a feedback loop:

```
Unconscious decisions → Captured patterns → Conscious principles → Better future decisions → New patterns...
```

The result: Claude that makes decisions the way you would, because it has learned your decision-making DNA.

---

This is not a preference storage system. It's a **self-discovery and decision-making replication system**.
