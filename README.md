# Prompt Clarifier

Prompt Clarifier is a lightweight Codex skill that turns rough, ambiguous, or underspecified requests into clear choices before work begins.

It helps Codex ask fewer but better questions, recommend sensible defaults, and avoid acting too early when a task is risky, irreversible, or externally visible.

## What It Does

- Detects missing details that materially affect the result.
- Offers 2-4 concrete options with a recommended default.
- Proceeds with defaults for low-risk tasks when the path is obvious.
- Stops for confirmation before high-risk or irreversible actions.
- Restates a compact working brief before execution.

## Good Fits

- Writing and content requests with unclear audience, tone, or length.
- Coding tasks with unclear scope, behavior, or verification requirements.
- Design tasks with unclear style, target user, or delivery format.
- Research tasks with unclear source policy, depth, or recency needs.
- Automation or publishing tasks that need explicit confirmation.

## Installation

Install from GitHub with Codex's skill installer:

```bash
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo haihaihai112/prompt-clarifier --path skills/prompt-clarifier
```

On Windows, the script is usually here:

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-installer\scripts\install-skill-from-github.py" --repo haihaihai112/prompt-clarifier --path skills/prompt-clarifier
```

After installation, the skill is available on the next Codex turn.

## Example

User:

```text
Help me write a WeChat article.
```

Codex with Prompt Clarifier:

```text
I need two quick choices, then I will continue:

1. Article direction:
A. Practical expert angle (Recommended): best for trust
B. Emotional resonance angle: best for sharing and comments
C. Conversion angle: best for consultations or purchases

2. Length:
A. 1500-2000 words (Recommended): balanced for WeChat reading
B. 800-1200 words: faster to read
C. 2500+ words: better for deep analysis
```

## Repository Layout

```text
prompt-clarifier/
├── README.md
├── LICENSE
├── examples/
└── skills/
    └── prompt-clarifier/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

## Design Notes

The skill itself stays intentionally small. Codex skill bodies are loaded into the model context when triggered, so the core workflow should remain concise. Longer documentation and examples live in this repository README and `examples/` folder instead.

## License

MIT

## 作品导航 / Project navigation

[个人主页与完整项目索引 / Profile and project index](https://github.com/haihaihai112)
