# Problem & Validation

**Team:** Product Management  
**Contributors:** Radha D S and Teams  
**Status:** In Development  
**Launching on:** ChatGPT Mobile - India  
**Resources:** Milestone1 Milestone 2 annotated wireframes ([Wireframes / Wireflow Reference](https://www.dropbox.com/scl/fo/p9ln0cqxrbi6k6pjepf06/AJ-_T0BjjRxD3KCii-jqiHU?rlkey=tl9qwbev37a27wz55sqihq945&st=z0w0zqtm&dl=0)), Clickable Simulation

**Objective:** Increase Voice adoption and repeat usage among Indian mobile ChatGPT users by helping them discover when Voice is more useful than typing.

## Problem Definition

| Question | Answer |
|---|---|
| What is the problem? | Low ChatGPT mobile voice adoption in India |
| Who is facing the problem? | Indian mobile-first, multilingual ChatGPT users who often default to typing and may face barriers related to language, accent, dialect, or conversational context when using Voice. |
| What is the business value that will be unlocked by solving the problem? | Higher voice adoption and repeat usage can drive stronger engagement and retention among Indian ChatGPT users |
| How will the target users benefit if the problem is solved? | Users can have more natural conversations with ChatGPT when speaking is more convenient or useful than typing. |
| Why is it urgent to solve this problem now? | Helping users discover when Voice is more useful than typing can increase Voice adoption and repeat usage in a large, mobile-first, multilingual user base in India. |

## Success Metrics

| Metric Type | Metric | What it measures? | Formula |
|---|---|---|---|
| North Star | Voice adoption rate | How many eligible users use Voice | Voice users ÷ Eligible users × 100 |
| Leading | Voice start rate | How often users start Voice after seeing a contextual entry point | Voice starts ÷ Voice entry-point views × 100 |
| Lagging | Repeat Voice rate | How many Voice users come back to use it again | Users with ≥2 Voice sessions ÷ Voice users × 100 |

## Guardrail Metrics

| Guardrail Metric | What it measures? | Formula |
|---|---|---|
| Voice abandonment rate | How often users leave Voice without completing the interaction | # abandoned Voice sessions ÷ # Voice sessions started |
| Negative feedback rate | How often users report a poor Voice experience | # negative feedback responses ÷ # users who provide feedback |

## Goals

| Priority | Goal | What it aims to achieve? |
|---|---|---|
| P0 | Increase Voice adoption | More eligible users use Voice |
| P0 | Improve Voice discoverability | More users recognize and start Voice through relevant contextual entry points |
| P1 | Increase repeat usage | More Voice users return and use Voice again |

# Problem & Validation — Validation of the Problem

## Non-functional Metrics

| P | Non-functional metric | What it measures | Formula / unit |
|---|---|---|---|
| P0 | Entry-point render rate | Whether the right contextual Voice card appears when eligible | Rendered cards ÷ Eligible card opportunities |
| P0 | Voice launch success rate | Whether tapping a contextual card successfully starts Voice exploration | Successful Voice launches ÷ Card taps |
| P0 | Multilingual comprehension rate | How reliably Voice understands mixed-language and language-switching turns | Correctly understood multilingual turns ÷ Total multilingual turns |
| P1 | Exploration turn completion rate | Whether users can complete a Voice turn without technical failure or interruption | Completed turns ÷ Voice turns started |
| P1 | Exploration response latency | Whether Voice responds quickly enough to maintain back-and-forth flow | Seconds — P50 / P95 |

## Validation of the Problem

### Insights from competitive landscape

Existing products give users familiar reasons to use voice:

| Product | Clear role of voice |
|---|---|
| WhatsApp | Voice for fast communication. |
| Alexa | Voice as a primary way to interact |
| YouTube/Search | Voice for search and discovery. |

**Key Insight for ChatGPT:** Users know Voice exists, but they don't always know when or why to use it instead of typing.

### Insights from User Research and Survey

Research identified several barriers to Voice adoption. 50% prefer typing, and 50% have tried Voice only once. This suggests we need to help users see when Voice is useful enough to use again.

## Non-Goals

| Non-goal | Scope boundary |
|---|---|
| Replace typing with Voice | Voice remains an option, not a replacement. |
| Redesign ChatGPT Voice | Focus on contextual entry points and exploratory Voice interactions |
| Change underlying Voice/model capabilities | Leverage existing speech and model capabilities |
| Cover all Voice use cases | Focus on selected contexts where multilingual exploratory Voice adds value. |

## How Might We Question

**How might we help Indian multilingual mobile ChatGPT users discover and act on moments where Voice is more useful than typing?**

# Target User & Opportunity

## Selected User Segment

Indian multilingual mobile ChatGPT users who may use English, Hindi, Hinglish, or other languages in everyday interactions.

**Mobile-first, multilingual context:** 85.5% of Indian households had at least one smartphone in 2025, while 97.1% of 15–29-year-olds reported using a mobile phone. India’s voice landscape spans 15 languages and 139 regional clusters.

**Sources:** Government of India, Ministry of Statistics & Programme Implementation, Comprehensive Modular Survey: Telecom, 2025; Bhogale et al., “Voice of India,” 2026.

**Prototype scenarios:** Women, teenagers, professionals, and homemakers are used to test different scenarios in the prototype, not as separate user groups.

## User Jobs & Needs

The JTBDs point to a common need:

> When I'm exploring an idea, I want to express incomplete or multilingual thoughts naturally and work through them in a rapid back-and-forth conversation, without having to know exactly what to ask or formulate the perfect text prompt.

For details, see the JTBD diagram.

## Solution

We identified four opportunities for Voice and prioritized them based on Impact, Voice advantage, Multilingual fit, and Habit potential.

| Solution area | Impact | Voice advantage | Multilingual fit | Habit potential |
|---|---|---|---|---|
| **Explore an idea/topic through rapid back-and-forth – Selected opportunity.** | High | High | High | High |
| Manage an unexpected problem while I'm busy | High | High | Medium | Medium |
| Communicate naturally in my language | High | Medium | High | High |
| Talk through a personal situation | Medium | High | Medium | Medium |

# Solution & Experience

In the proposed solution, users discover a situation → Start Voice → Speak naturally → Explore through conversation → Get value → Give feedback → Use Voice again.

See voice discovery and habit flow.

## Key Features

| Feature | Description |
|---|---|
| Situation-led Voice discovery | Show users situations where Voice may be more useful than typing. |
| Conversational exploration | Let users start with an unfinished thought and work through it with ChatGPT through real-time voice conversation. |
| Natural multilingual interaction | Let users speak in the language mix that feels natural instead of translating or carefully structuring the request first. |
| Post-conversation feedback | Capture perceived value and intent to use Voice again after the experience. |

See more wireflows.

## Key Logic

What needs to change behind the experience? For the prototype, keep the data model small.

| Item | Details |
|---|---|
| Seed/template data | Voice discovery contexts; Conversation titles; Starting conversation context; Feedback options |
| Interaction state | Selected context; Current conversation; Voice active/inactive state; Conversation messages; Feedback response |

Do not add user profiles, persona databases, language databases, analytics dashboards, or production Voice infrastructure unless a screen or interaction needs them.

The final implementation handoff can translate this into a minimal JSON data model + matching Mermaid ER diagram.

# Prototype, Logic & Measurement

## Launch Readiness

### Key Milestones

1. PRD finalized
2. User flow finalized
3. Annotated wireframes completed
4. Prototype data model defined
5. Responsive clickable prototype built
6. Prototype QA across mobile and desktop
7. User testing / feedback completed
8. Metrics and experiment plan finalized

### Launch Checklist

- All five screens are connected.
- All primary interactions are clickable.
- Back-and-forth Voice conversation works as intended.
- Feedback appears after each conversational experience.
- Prototype works across mobile and desktop.
- Prototype is shareable.
- No unsupported product features are introduced.

### Experimentation Plan

Test whether situation-led Voice discovery improves the journey from:

**Discovery → Voice trial → Successful experience → Repeat Voice usage**

Compare the new contextual entry point with the current Voice experience to see whether users are more likely to discover, try, and return to Voice.

## Key Trade-off

We are focusing on one opportunity rather than trying to solve every Voice adoption barrier:

**Help users discover situations where conversational exploration is more useful than typing.**

# Open Questions & Decisions Taken

| Question / Decision | Status |
|---|---|
| What is the core adoption problem? | **Decided:** Users don't consistently understand when or why Voice is better than typing. |
| Which opportunity should we prioritize? | **Decided:** Explore an idea or topic through rapid back-and-forth. |
| Should Voice replace typing? | **Decided:** No. Voice should be the better option when it adds value. |
| Is multilingual a separate solution? | **Decided:** No. It is a lens across use cases. |
| What are the prototype use cases? | **Decided:** Presentation, interview, decision-making, plus a multilingual/multitasking scenario. |
| Should there be a separate habit-reinforcement screen? | **Decided:** No. Repeat use should come from useful experiences. |
| Where should feedback appear? | **Decided:** After each conversational experience. |
| What does feedback measure? | **Decided:** Perceived value and repeat intent, not actual retention. |
| Should login/access friction be part of the core prototype? | **Descoped:** Keep it as a separate product/business hypothesis. |
| Should we solve Voice recognition quality? | **Descoped:** Outside this solution's scope. |
| Should we build production Voice infrastructure? | **Descoped:** No production Voice infrastructure will be built. The prototype will demonstrate the Voice interaction without building production infrastructure. |
