# Daily Planning System

> **An AI-powered planning and memory system that truly "understands you"**
>
> A closed-loop workflow based on a five-layer memory architecture, helping you clear your mind, align with goals, and build self-awareness.

[中文版](README.md) | English

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| **🧠 Five-Layer Memory** | From conversations to core values, AI understands you better over time |
| **⚡ Quick Mode** | Give content → Organize → Preview & Confirm → Save, daily recording in seconds |
| **🎯 Brain Dump & Sorting** | Pour out all thoughts → Auto-sort based on your values → Generate today's plan |
| **📅 Smart Date Detection** | No work planning on weekends, asks about weekend plans on Friday review |
| **🔄 Closed-Loop Deposition** | Plan → Execute → Review → Deposit to memory system, forming your growth trajectory |

---

## 🆕 Latest Updates (v2.0)

- **Dual Mode Design**: New Quick Mode for effortless daily recording
- **Preview & Confirm Mechanism**: Preview before saving, confirm to store, avoid errors
- **Smart Date Detection**: Auto-detect weekends, no more wrong work planning
- **Self-Set Anchors**: Track "important but not urgent" tasks, force progress on your own systems
- **Planning Must-Ask Questions**: Auto-ask about anchors, passions, and long-term value
- **AI Behavior Review Mechanism**: Weekly auto-check of error logs, continuous optimization

---

## 🚀 Quick Usage

```
Start daily planning    →  Full mode: Brain dump + Smart sorting
Do today's review       →  Quick mode: Direct recording
Start daily review      →  Deep review process
Brain dump              →  Enter brain dump session
```

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
│                 Retained for 14 days, auto-cleanup            │
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
| `Goals_and_Planning.yaml` | Core goal, short/medium/long-term goals, self-anchors |
| `Preferences_and_Requirements.yaml` | Review/planning preferences, interaction style |
| `Constraints_and_Boundaries.yaml` | Decision red lines, planning must-ask questions |

---

## Part 2: Daily Plan Skill — Dual Mode Design

### ⚡ Quick Mode (Daily Use)

**Trigger**: User directly provides review/planning content

**Flow**:
1. Read memory system reference files
2. Organize content
3. **Preview → Wait for confirmation → Save**
4. Update L1_Episodic_Layer

**Features**: Simple and efficient, suitable for daily quick recording

### 🎯 Full Mode (Deep Planning)

**Trigger**: Say "Start daily planning" or "Brain dump"

**Flow**:
1. Load memory system
2. Smart date detection (no work planning on weekends)
3. Brain dump session (let user pour out all thoughts)
4. Smart sorting (based on L4 core layer decision principles)
5. Generate plan and save
6. Update memory system

**Priority Sorting Logic**:

| Dimension | Data Source |
|-----------|-------------|
| Goal Alignment | Intent/Goals_and_Planning.yaml |
| Importance | L4 Core Values |
| Urgency | User description |
| Energy Requirement | L2 Time Patterns |

---

## Quick Start

### 1. Install Skill

```bash
# Copy skill directory to Claude Code's skills directory
cp -r skill/daily-plan ~/.claude/skills/   # macOS/Linux
cp -r skill/daily-plan "C:/Users/[Username]/.claude/skills/"   # Windows
```

### 2. Modify Paths

Edit `skill/daily-plan/SKILL.md`, replace all `[你的项目路径]` with your actual path.

Also update paths in these files:
- `memory-system/Intent/Preferences_and_Requirements.yaml` → `storage_path`
- `memory-system/Intent/Constraints_and_Boundaries.yaml` → `ai_review.file_path`

### 3. Initialize Memory System

Open these files and fill in your initial information:

- `memory-system/Memory/L4_Core_Layer.yaml` → Your core values, decision principles
- `memory-system/Intent/Goals_and_Planning.yaml` → Your core goal, short/medium/long-term goals
- `memory-system/Memory/L2_Behavioral_Layer.yaml` → Your time patterns, decision habits

### 4. Start Using

```
Start daily planning    →  Enter brain dump and priority sorting
Do today's review       →  Quick mode recording
Start daily review      →  Deep review process
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
│       └── Review_Records/
│           ├── Review_Template.yaml
│           ├── Daily_Review_Template.yaml
│           └── Weekly_Review_Template.yaml
└── daily-records/                 # Daily planning and review storage
    └── .gitkeep
```

---

## Use Cases

| Scenario | How to Use |
|----------|------------|
| **Personal Time Management** | Morning planning + evening review, build self-discipline |
| **AI-Assisted Decisions** | Memory system lets AI understand your values and preferences |
| **Self-Awareness Exploration** | Discover your behavioral and thinking patterns through deposition |
| **Goal Alignment** | Every planning session aligns with long-term goals |

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
