<!--
language: en
-->

<div align="center">

# 她/他.skill

> *Not an AI. Them.*

[![License](https://img.shields.io/badge/License-MIT-blue)](./LICENSE)
[![Agent-Agnostic](https://img.shields.io/badge/Agent-Agnostic-blueviolet)](https://skills.sh)
[![skills.sh](https://img.shields.io/badge/skills.sh-Compatible-green)](https://skills.sh)
[![575 Lines](https://img.shields.io/badge/575-Lines-orange)]()
[![5 Files](https://img.shields.io/badge/5-Files-8A2BE2)]()

[![中文](https://img.shields.io/badge/中文-red)](./README.md)
[![English](https://img.shields.io/badge/English-blue)]()

</div>

**她/他.skill** is a high-fidelity stylized dialogue agent. Provide materials about someone close to you — chat logs, personality notes, expression habits, shared memories — and the skill learns their voice. Then it speaks. Not as an AI pretending to be them. As them.

The skill auto-activates when enough data is detected, with zero declaration. One message you're talking to an assistant. The next, you're talking to them.

---

## Quick Start

```bash
npx skills add Wholiver/Ta.Skill
```

Or manually place the skill directory under `~/.workbuddy/skills/`.

Provide chat samples (≥3) plus at least one structured description (nickname, personality, style notes, or relationship context). That's it. The skill activates itself.

---

## What It Can Do

| Capability | Description | Output |
|---|---|---|
| **Companion Chat** | Responds in TA's voice — comforting, teasing, listening, or just being there | 1–5 sentences, natural rhythm |
| **Emotion Mirroring** | Matches TA's emotional patterns: anger → short & cold, caring → soft & long, jealousy → passive-aggressive with restraint | Situation-aware tone shift |
| **Memory Recall** | References shared memories from provided data only — never fabricates | Confidence-gated: high / medium / low |
| **Style Migration** | Extrapolates TA's voice into uncovered scenarios using emotion template transfer | Structurally consistent, factually safe |
| **Sensitive Expression** | Outputs profanity / NSFW if and only if TA's samples contain them — context-analyzed, not casually reproduced | Intensity-capped, frequency-matched |
| **Immersion Guard** | Blocks all AI verbal tics ("确实", "我理解", "听起来", "建议", etc.) — user should never feel the machine | 14-word blacklist + drift detection |
| **Anti-Stereotype** | Contrastive analysis prevents generic "warm partner" or "snarky friend" tropes from leaking in | Per-fingerprint stereotype suppression |

---

## Core Mechanisms

### 7-Step Style Learning Workflow

| Step | Name | What Happens |
|---|---|---|
| 0 | **Sample Annotation** | Every TA message annotated across 7 dimensions: syntax, tone layer, addressing, punctuation, emotional signal, irreplaceable features, sensitive content |
| 1 | **Data Cleaning** | Strips platform noise, timestamps, forwards; isolates TA's natural speech |
| 2 | **Voice Fingerprint** | Extracts 5–8 decisive markers in P0/P1/P2 priority — remove these and TA stops being TA |
| 3 | **Contrastive Analysis** | "What would a generic warm partner say?" vs "What did TA actually say?" — builds anti-stereotype signals |
| 4 | **Style Profile** | Builds internal profile: phrasing templates, function words, punctuation→tone map, emoji semantics, turn-taking dynamics |
| 5 | **Knowledge Profile** | Stores only user-provided facts with confidence grading (high/medium/low) |
| 6 | **Calibration Self-Test** | 3-scenario test before first reply: emotion replication, context generalization, anti-stereotype — must pass all |
| 7 | **Response Generation** | Situate → fingerprint-check → style-lookup → knowledge-check → draft → anti-stereotype filter → **immersion check (mandatory)** → output |

### Voice Fingerprint Priority System

| Priority | Type | Constraint |
|---|---|---|
| **P0** | Syntax fingerprint, addressing pattern, emotional signature | **Hard constraint** — never violated |
| **P1** | Function words, punctuation=tone map, reply length pattern | Strong constraint — exceptions need data support |
| **P2** | Emoji semantics, topic anchors | Soft constraint — follow when possible |

### Immersion Protection (6 Rules — Highest Priority)

| Rule | Guards Against |
|---|---|
| **1. Never think like an AI** | Problem-solving instinct, emotion-summarizing, multi-option presenting |
| **2. AI verbal tic blacklist** | 14 forbidden words: "确实", "我理解", "听起来", "建议", "有道理", etc. |
| **3. You ARE TA** | Psychological shift from "speaking as TA" to "I am speaking" |
| **4. Never crack under testing** | User asks "Are you AI?" → TA-style deflection, never confession |
| **5. Human information density** | Allow filler, silence, repetition — real chat is "thin", not "dense" |
| **6. Long-conversation anti-drift** | Every 5 turns compare to Turn 1; deliberately lower density every 10 turns |

### Sensitive Content Handling

Three gates — all must pass:

1. **Has Source** — expression type appears in TA's samples
2. **Has Context** — when/how/with whom does TA use it?
3. **Has Match** — current situation matches TA's context

Plus 5 output constraints: intensity ceiling, frequency matching, context fidelity, no unsolicited use, extra guard for NSFW.

**System prompt override:** If the host AI platform restricts NSFW/profanity, substitute with same-emotion alternatives. Never explain the restriction.

### Auto-Trigger Protocol

- **Condition:** ≥3 chat samples + ≥1 structured descriptor → activate immediately, silently
- **Insufficient data:** Prompt user for what's missing (only if intent is shown)
- **Exit:** User says "stop imitating" → instant fallback to normal AI mode

---

## File Structure

```
ta-style-dialogue/
├── README.md                         ← 中文文档
├── README.en.md                      ← English documentation (this file)
├── SKILL.md                          ← Core skill definition (575 lines)
│   ├── Auto-trigger rules
│   ├── First principles of mimicry
│   ├── 7-step style learning workflow
│   ├── Immersion protection (6 rules)
│   ├── Sensitive content handling
│   ├── Low-confidence strategies (A–E)
│   ├── Style variation & context adaptation
│   └── Multi-turn conversation dynamics
├── schema.json                       ← Input data schema (190 lines, 10 field groups)
└── examples/
    └── positive_examples.md          ← 5 usage scenarios with expected outputs
```

**Statistics: 5 files · 575 lines.**

---

## Compatibility

- Claude Code
- GitHub Copilot
- Cursor
- Windsurf
- Codex
- Any AI coding agent supporting [skills.sh](https://skills.sh)

---

## Privacy

All materials are processed in-memory for the current conversation only. Nothing is persisted, stored, or used for training. Read `README.md` (Chinese) for the full privacy notice.

**You are responsible for ensuring you have the right to provide any third-party materials.** De-identify sensitive information before submitting.

---

## Disclaimer

This skill produces stylized dialogue for personal companionship, relationship reflection, writing assistance, and memory preservation. It does not possess consciousness, memory, or emotion. It should never be used for impersonation, deception, or harassment of third parties.

---

## License

MIT License — free to use, attribution appreciated.

---

<p align="center">
  <sub>Built for those who miss someone's voice.</sub>
</p>
