# Daily Planning System

> **An AI-powered planning and memory system that truly "understands you"**
>
> A closed-loop workflow based on a five-layer memory architecture, helping you clear your mind, align with goals, and build self-awareness.

[中文版](README.md) | English

---

## Why Do You Need This System?

Do you struggle with these problems?

- 🧠 **Mental Overload**: Too many things to do, don't know where to start
- 🎯 **Goal Drift**: Busy all day, but realize you've drifted from what truly matters
- 📝 **Repetitive Decisions**: Having to re-explain your preferences and style every time
- 💭 **Self-Lost**: Unclear about your behavioral patterns and core values

**Daily Planning System** creates a closed loop of "Memory + Planning + Review", making AI understand you better over time. It helps you build order from chaos and discover patterns from repetition.

---

## Core Concept: One Loop, Three Layers of Value

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│     ┌──────────────┐      ┌──────────────┐      ┌───────────┐  │
│     │ Memory System│ ──▶ │ Daily Plan   │ ──▶ │  Execute   │  │
│     │  (Who You Are)│      │(What to Do)  │      │(What Done)│  │
│     └──────────────┘      └──────────────┘      └───────────┘  │
│            ▲                                           │        │
│            │              ┌──────────────┐              │        │
│            └──────────────│ Daily Review │◀─────────────┘        │
│                           │ (What Learned)│                       │
│                           └──────────────┘                       │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

| Phase | Purpose | Output |
|-------|---------|--------|
| **Morning Planning** | Reference memory system to prioritize today's tasks | Today's execution list |
| **Interactive Confirmation** | Dialogue with AI to clarify daily focus | Clear priorities |
| **Evening Review** | Summarize behaviors, deposit insights back to memory | AI that knows you better |

---

## Part 1: Memory System — Five-Layer Architecture

The memory system uses a "passive deposition" track, letting AI gradually understand you through daily conversations:

```
┌─────────────────────────────────────────────────────────────┐
│                        L4 Core Layer                         │
│         Core Values · Life Beliefs · Decision Principles      │
│                    ⚠️ Manual editing only                     │
├─────────────────────────────────────────────────────────────┤
│                     L3 Cognitive Layer                       │
│       Thinking Patterns · Decision Frameworks · Mental Models │
│              Deposited after annual review confirmation       │
├─────────────────────────────────────────────────────────────┤
│                     L2 Behavioral Layer                      │
│       Work Habits · Communication Style · Time Patterns       │
│             Deposited after quarterly review confirmation     │
├─────────────────────────────────────────────────────────────┤
│                      L1 Episodic Layer                       │
│       Recent Events · Project Status · To-Do Items            │
│                 Retained for 30 days, auto-cleanup            │
├─────────────────────────────────────────────────────────────┤
│                      L0 State Layer                          │
│                Temporary state of current dialogue            │
│                   Disappears when session ends                │
└─────────────────────────────────────────────────────────────┘
```

### Deposition Rules

| Layer Transition | Trigger Condition |
|------------------|-------------------|
| L0 → L1 | Session ends, significant event occurs |
| L1 → L2 | Same behavioral pattern appears 3+ times |
| L2 → L3 | Stable thinking pattern discovered |
| L3 → L4 | Annual deep reflection (manual confirmation) |

### Active Input Track (Intent)

Besides passive deposition, you can also actively tell AI:

| File | Purpose |
|------|---------|
| `Goals_and_Planning.yaml` | Short/Medium/Long-term goals |
| `Preferences_and_Requirements.yaml` | Interaction style, format preferences |
| `Constraints_and_Boundaries.yaml` | Decision red lines, prohibitions |

---

## Part 2: Daily Plan Skill — Complete Closed Loop

### 🌅 Morning: Daily Planning

```
Say: "Start daily planning"
```

**What the Skill does:**

1. **Load Memory** → Read your goals, preferences, values
2. **Brain Dump** → Let you pour out all tasks without judgment
3. **Value Sorting** → Calculate priority for each task based on your core layer
4. **Task Splitting** → Distinguish "Protected Time Tasks" from "Agent Auto Tasks"
5. **Generate List** → Output today's execution table, auto-save

**Priority Formula:**
```
Priority Score = Goal Alignment(40%) + Importance(30%) + Urgency(20%) + Energy Match(10%)
```

**Time Block Matching:**
- Morning → High-energy tasks (complex thinking, creative work)
- Afternoon → Medium-energy (communication, collaboration, learning)
- Evening → Low-energy (organizing, exploring)

### 🌙 Evening: Daily Review

```
Say: "Start daily review"
```

**What the Skill does:**

1. **Read Plan** → Compare with this morning's plan
2. **Guided Questions** → 5 questions to help you reflect on the day
3. **Generate Report** → Completion status, key insights, pending depositions
4. **Update Memory** → Write new insights to L1 Episodic Layer
5. **Deposition Queue** → Discover behavioral patterns, add to queue

**Review Question List:**
1. What tasks did you actually complete today?
2. What tasks weren't completed? Why?
3. Any unexpected gains or discoveries today?
4. How was your energy level today?
5. What's important for tomorrow?

---

## Quick Start

### 1. Install Skill

```bash
# Copy skill directory to Claude Code's skills directory
cp -r skill/daily-plan ~/.claude/skills/   # macOS/Linux
cp -r skill/daily-plan "C:/Users/[Username]/.claude/skills/"   # Windows
```

### 2. Modify Paths

Edit `skill/daily-plan/SKILL.md`, replace all `[Your_Project_Path]` with your actual path.

### 3. Initialize Memory System

Open these files and fill in your initial information:

- `memory-system/Memory/L4_Core_Layer.yaml` → Your core values, decision principles
- `memory-system/Intent/Goals_and_Planning.yaml` → Your short/medium/long-term goals

### 4. Start Using

```
Start daily planning    →  Enter brain dump and priority sorting
Start daily review      →  Summarize the day and deposit memories
```

---

## Project Structure

```
daily-planning-system/
├── skill/                          # Claude Code Skill
│   └── daily-plan/
│       └── SKILL.md               # Skill definition
├── memory-system/                  # Memory System
│   ├── README.yaml                # Framework design document
│   ├── User_Guide.md              # Detailed usage guide
│   ├── Memory/                    # Passive deposition track (5 layers)
│   │   ├── L0_State_Layer_Info.yaml
│   │   ├── L1_Episodic_Layer.yaml
│   │   ├── L2_Behavioral_Layer.yaml
│   │   ├── L3_Cognitive_Layer.yaml
│   │   └── L4_Core_Layer.yaml
│   ├── Intent/                    # Active input track
│   │   ├── Goals_and_Planning.yaml
│   │   ├── Preferences_and_Requirements.yaml
│   │   └── Constraints_and_Boundaries.yaml
│   └── Meta/                      # System metadata
│       ├── Insights_Queue.yaml
│       ├── Framework_Evolution.yaml
│       └── Review_Records/Review_Template.yaml
└── daily-records/                 # Daily planning and review storage
```

---

## Use Cases

| Scenario | How to Use |
|----------|------------|
| **Personal Time Management** | Morning planning + evening review, build self-discipline |
| **AI-Assisted Decisions** | Memory system lets AI understand your values and preferences |
| **Self-Awareness Exploration** | Discover your behavioral and thinking patterns through deposition |
| **Team Collaboration** | Agent task splitting, one person works like a small team |

---

## Design Philosophy

> I wanted to build a memory system for AI interaction that helps me abstract and distill my values, personality traits, mental models, thinking patterns, work habits, behavioral preferences, and decision principles. Let AI understand me better the more I use it, and even simulate my decisions.

Core values of this system:

- **Make AI truly understand you**: No need to re-explain every time
- **Make goals clearly visible**: Every planning session aligns with long-term goals
- **Make growth traceable**: What's deposited is your growth trajectory

---

## Requirements

- [Claude Code CLI](https://claude.ai/code)
- Support for YAML and Markdown formats

---

## License

[MIT License](LICENSE)

---

**If you find this project helpful, please give it a Star ⭐**
