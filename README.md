# AI Study Tutor

A skill for **terminal AI agents** (AI coding agents / agentic CLIs such as Claude Code, Codex CLI, Gemini CLI, OpenCode …) that teaches you your study materials (PDFs, lecture notes, slides, even scans) step by step, like a very good **private tutor**. You don't just read summaries. You build up the material from a few core rules, derive things yourself and explain them back, until you really **understand why** things are the way they are.

## What you get

- **A learning plan**: the material is split into short units that build on each other, with the **core rules first**: the 3–5 principles from which the rest can be derived.
- **Small chunks**: one idea per message, with the *why*, an everyday comparison and the technical terms explained.
- **You think, not just read**: before a new detail is revealed, you are asked to derive it from what you already know.
- **Real understanding checks** after every chunk. Never "understood?". Instead: explain it, predict it, compare, apply it to a case.
- **A different explanation** when something doesn't land: another comparison, an example, a sketch, a smaller step. Never the same text again.
- **Unit wrap-ups**: you summarise in your own words, get a correct mnemonic and the key points, then a mini review of earlier units.
- **It keeps going** until you say *stop*.
- **Progress file** (`<Material>_Progress.md`) with the plan, what is still shaky and the core rules, so the next session continues seamlessly.
- **Automatic conversion** of your materials to Markdown (`to_md.sh`), including detection of scanned PDFs.

## How it works

1. **Convert:** all files in your folder are converted to `.md` with `markitdown` (fallback: `pandoc` for Word files). For scanned pages, the AI looks at rendered page images directly or runs OCR.
2. **Plan:** the AI reads all of the material, finds the core rules and builds learning units in a logical order.
3. **Teach:** hook → chunk with the why → you derive → understanding question → feedback → next chunk. Each unit ends with your summary and a short review.
4. **Save:** when you say *stop*, you get a short review and the progress file is written or updated next to your materials.

## Requirements

- A terminal AI agent that can read files and run shell commands. Skill support is a plus, but not required.
- Linux or macOS (Windows via WSL)
- [`markitdown`](https://github.com/microsoft/markitdown): `pipx install 'markitdown[all]'`
- `poppler`: `sudo pacman -S poppler` / `sudo apt install poppler-utils` / `brew install poppler`
- Optional: [`pandoc`](https://pandoc.org) (fallback for Word files), `tesseract` plus the language packs you need (for scans)

## Installation

```bash
git clone https://github.com/blackpaired/ai-study-tutor.git
cd ai-study-tutor
bash install.sh
```

By default the script copies the skill to `~/.claude/skills/study-tutor/`. Claude Code and some other tools read skills from there (`SKILL.md` is an open format used by several AI agents). If your AI tool loads skills from a different folder, pass it:

```bash
bash install.sh ~/.my-ai-tool/skills
```

The script also shows which required programs are missing.

To install by hand instead:

```bash
mkdir -p <skills-folder>
cp -r skills/study-tutor <skills-folder>/
chmod +x <skills-folder>/study-tutor/to_md.sh
```

Then restart your AI agent.

**Tool without skill support?** It still works: tell the AI *"follow the instructions in `<skills-folder>/study-tutor/SKILL.md` for ~/Documents/Physiology/"*.

## Usage

Put the materials for one exam into one folder, then in your AI agent type:

```
/study-tutor ~/Documents/Physiology/
```

Plain language works too: *"teach me ~/Documents/Physiology"*, or *"explain chapter 3 to me from the beginning"*.

The tutor works in the language of your materials and of your messages.

### Commands during a session

| Say | What happens |
|---|---|
| `slower` / `faster` | chunk size and depth are adapted |
| `example` | a concrete example |
| `explain differently` | a completely different explanation |
| `sketch` | a table or ASCII sketch |
| `summarise` | summary of the current unit |
| `plan` | learning plan: done / current / open |
| `skip` | unit is marked as open, next unit |
| `quiz me` | switch to quiz mode (needs ai-study-quiz) |
| `stop` | review + progress file |

### Converting only

```bash
<skills-folder>/study-tutor/to_md.sh ~/Documents/Physiology/
```

## Works well with

- [ai-study-quiz](https://github.com/blackpaired/ai-study-quiz): quizzes you like an oral examiner to check whether it really sits.
- [ai-study-notes](https://github.com/blackpaired/ai-study-notes): turns your materials into study notes that explain the connections, exported as a PDF.

- [ai-study-anki](https://github.com/blackpaired/ai-study-anki): turns your materials into Anki flashcards (CSV, one-click import).

## Important

- Facts come from your materials. Explanations, comparisons and mnemonics partly come from general knowledge. **If anything contradicts your lecture or textbook, your lecture wins.**
- The AI can make mistakes. If an explanation looks wrong to you, say so and ask for the location in your notes.
- Every session uses your AI usage (tokens / plan limits). Long sessions and large materials mean more usage.

---

*This repo was created with the help of Claude Opus 5.5.*
