# ⚡ Prompt-Pilot

> **Adaptive Prompt Intelligence & Goal Decomposition Engine for Gemini 3.8 Flash & Google Antigravity**

[![Antigravity Skill](https://img.shields.io/badge/Antigravity-Skill-4285F4?style=flat-square&logo=google)](https://github.com/vammp4/prompt-pilot)
[![Model](https://img.shields.io/badge/Optimized%20for-Gemini%203.8%20Flash-00BFFF?style=flat-square)](https://deepmind.google)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

**Prompt-Pilot** is an agent skill engineered to bridge raw human intent and high-potency execution in **Gemini 3.8 Flash** and **Antigravity**. It eliminates manual bureaucracy, heavy templating, and shallow execution by dynamically adapting to your task's scope in real-time.

---

## 🚀 Key Highlights

- **🧠 Zero-Bureaucracy Adaptive Engine**: Automatically detects whether you need a micro-fix or an autonomous overnight loop. No complex question forms or rigid templates.
- **⚡ Flash-Speed Guardrails**: Specifically mitigates Gemini 3.8 Flash weaknesses (such as hasty assumption-making before grounding) while leveraging its strengths (high tokens/sec, long-context window).
- **🛡️ Anti-Shallow Rushing & Decoupled Verification**: Implements deterministic verification gates (tests, linters, build commands) instead of speculative assertions.
- **🔄 Autonomous Loop Architecture**: Built-in XML tag isolation (`<OBJECTIVE>`, `<CONSTRAINTS>`, `<EXECUTION_PLAN>`) and state-tracking rules (`tasks/todo.md`) to run seamlessly inside Antigravity `/goal` loops without hallucinating or looping.

---

## 🧭 The 4 Execution Modes

```
                      [ Raw User Intent / Idea ]
                                  │
         ┌────────────────────────┼────────────────────────┐
         ▼                        ▼                        ▼
 ⚡ Quick Spark           🧭 Strategic Roadmap      🔄 Loop Engine
 (Micro-boost)            (Multi-step Features)     (Autonomous Coding)
 Single fixes, quick      3-5 milestones, gates,    State machine, 3-strike
 edits, 5-15 line prompt  architecture breakdown    circuit breaker, `/goal`
```

### 1. ⚡ Quick Spark
* **Best for**: Small edits, bug investigations, one-liner scripts, rapid questions.
* **Output**: Ultra-dense, punchy 5–15 line instructions with zero filler.

### 2. 🧭 Strategic Roadmap
* **Best for**: Full features, component redesigns, API integrations, migrations.
* **Output**: Master goal definition, 3–5 vertical milestone slices, and strict **Verification Gates** per step.

### 3. 🔄 Autonomous Loop Engine
* **Best for**: Hands-off long runs (`/goal`), loop-coding agents, multi-hour refactors.
* **Output**: Structured around **The Long-Context Sandwich** pattern, XML context fencing, explicit circuit breakers, and state file management (`tasks/todo.md`).

### 4. 💬 Socratic Intuition
* **Best for**: Ambiguous architectural forks (e.g. SQL vs NoSQL, Serverless vs Container).
* **Behavior**: Never halts execution needlessly. Proposes a battle-tested default option and asks one razor-sharp question.

---

## 📦 Installation & Setup

### Option 1: Automatic One-Shot Prompt (Antigravity)
Copy and paste this instruction directly into your Antigravity chat:

```markdown
Install and configure the prompt-pilot skill from GitHub:

1. Clone or download https://github.com/vammp4/prompt-pilot into ~/.gemini/skills/prompt-pilot
2. Verify SKILL.md and directory structure.
3. Confirm installation and report available triggers.
```

### Option 2: Manual Installation via Git

```bash
# Navigate to your global Antigravity skills directory
cd ~/.gemini/skills

# Clone repository
git clone https://github.com/vammp4/prompt-pilot.git prompt-pilot
```

For Windows PowerShell:
```powershell
Set-Location "$env:USERPROFILE\.gemini\skills"
git clone https://github.com/vammp4/prompt-pilot.git prompt-pilot
```

---

## 💡 Usage Examples

Prompt-Pilot triggers organically from plain language:

- *"Make this prompt smarter for Gemini Flash: [your idea]"*
- *"Decompose this feature into micro-goals with verification steps: [description]"*
- *"Prepare this task for an autonomous Antigravity loop"*
- *"Optimize my prompt: I want to build a real-time notification service"*

---

## 📂 Repository Structure

```
prompt-pilot/
├── SKILL.md                 # Core skill declaration and operational guidelines
├── README.md                # Documentation and quickstart
├── LICENSE                  # MIT License
└── examples/
    └── modes_guide.md       # In-depth breakdown and output examples for each mode
```

---

## 📄 License

Distributed under the [MIT License](LICENSE). Feel free to adapt and build upon it!
