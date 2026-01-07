<p align="center">
  <h1 align="center">Claude Code Skills Collection</h1>
  <p align="center">
    <strong>My curated collection of Claude Code skills for enhanced AI-assisted development</strong>
  </p>
  <p align="center">
    <a href="#-quick-start">Quick Start</a> •
    <a href="#-skills-overview">Skills</a> •
    <a href="#-requirements">Requirements</a> •
    <a href="#-troubleshooting">Troubleshooting</a>
  </p>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/skills-27-blue?style=flat-square" alt="Skills Count">
  <img src="https://img.shields.io/badge/submodules-6-green?style=flat-square" alt="Submodules">
  <img src="https://img.shields.io/badge/python-3.10+-yellow?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/node-18+-green?style=flat-square&logo=node.js&logoColor=white" alt="Node.js">
</p>

---

## 🚀 Quick Start

### One-Line Install

**HTTPS (Recommended):**
```bash
git clone --recurse-submodules https://github.com/ShunmeiCho/claude-code-skills.git ~/.claude/skills && cd ~/.claude/skills && ./setup.sh
```

**SSH (requires SSH key):**
```bash
git clone --recurse-submodules git@github.com:ShunmeiCho/claude-code-skills.git ~/.claude/skills && cd ~/.claude/skills && ./setup.sh
```

### Step by Step

```bash
# 1. Clone with submodules (choose one)
git clone --recurse-submodules https://github.com/ShunmeiCho/claude-code-skills.git ~/.claude/skills  # HTTPS
git clone --recurse-submodules git@github.com:ShunmeiCho/claude-code-skills.git ~/.claude/skills      # SSH

# 2. Run setup
cd ~/.claude/skills
./setup.sh
```

> **Note:** If you forgot `--recurse-submodules`, run: `git submodule update --init --recursive`

### Setup Options

| Command | Description |
|---------|-------------|
| `./setup.sh` | Install all dependencies (Python + Node.js) |
| `./setup.sh --all` | Same as above |
| `./setup.sh --python` | Python dependencies only |
| `./setup.sh --node` | Node.js dependencies only |
| `./setup.sh --minimal` | Submodules only, no dependencies |

---

## 📦 Skills Overview

### 💬 Prompt-Only Skills

These skills work out of the box with no dependencies:

| Skill | Description |
|:------|:------------|
| 📰 `article-extractor` | Extract clean article content from URLs |
| 💡 `brainstorming` | Creative exploration before implementation |
| 📋 `changelog-generator` | Generate changelogs from git commits |
| 📈 `developer-growth-analysis` | Analyze coding patterns and growth |
| 📁 `file-organizer` | Intelligently organize files and folders |
| 🏁 `finishing-a-development-branch` | Guide for completing dev branches |
| 🚀 `git-pushing` | Smart git commit and push workflow |
| ♻️ `kaizen` | Iterative improvement techniques |
| ✍️ `prompt-engineering` | Writing effective prompts for LLMs |
| 👀 `review-implementing` | Process code review feedback |
| 🏗️ `software-architecture` | Quality-focused architecture guidance |
| 🤖 `subagent-driven-development` | Dispatch subagents for parallel tasks |
| 🖥️ `terminal-title` | Update terminal title for task context |
| 🧪 `test-driven-development` | TDD workflow guidance |
| 🔧 `test-fixing` | Systematically fix failing tests |
| 🌳 `using-git-worktrees` | Git worktree management |

### 🐍 Python Skills

| Skill | Dependencies | Install |
|:------|:-------------|:--------|
| 📄 `docx` | lxml | `pip install lxml` |
| 📑 `pdf` | pypdf, pymupdf, reportlab, pillow | `pip install pypdf pymupdf reportlab pillow` |
| 📊 `pptx` | lxml, html2pptx | See skill directory |
| 📈 `xlsx` | openpyxl | `pip install openpyxl` |
| 📓 `notebooklm-skill` | patchright | Uses venv (see setup.sh) |

<details>
<summary><b>Quick install all Python dependencies</b></summary>

```bash
pip install lxml pymupdf pypdf reportlab pillow openpyxl
```

</details>

### 🟢 Node.js Skills

| Skill | Dependencies | Install |
|:------|:-------------|:--------|
| 🎭 `playwright-skill` | playwright | `npm install && npx playwright install chromium` |
| ⚡ `n8n-skills` | n8n, typescript | `npm install && npm run build` |

### 🔗 Third-Party Skills (Submodules)

These track their upstream repositories and can be updated independently:

| Skill | Author | Description |
|:------|:-------|:------------|
| 📊 `claude-d3js-skill` | [@chrisvoncsefalvay](https://github.com/chrisvoncsefalvay/claude-d3js-skill) | D3.js data visualizations |
| 🌳 `family-history-planning` | [@emaynard](https://github.com/emaynard/claude-family-history-research-skill) | Genealogy research planning |
| ⬡ `move-code-quality` | [@1NickPappas](https://github.com/1NickPappas/move-code-quality-skill) | Move language code quality |
| ⚡ `n8n-skills` | [@haunchen](https://github.com/haunchen/n8n-skills) | n8n workflow automation |
| 📓 `notebooklm-skill` | [@PleasePrompto](https://github.com/PleasePrompto/notebooklm-skill) | Google NotebookLM integration |
| 🧪 `pict-test-designer` | [@omkamal](https://github.com/omkamal/pypict-claude-skill) | PICT combinatorial testing |

---

## 🔄 Updating

```bash
# Update all submodules
cd ~/.claude/skills
git submodule update --remote --merge

# Update specific submodule
cd ~/.claude/skills/notebooklm-skill
git pull origin main
```

---

## 📁 Directory Structure

```
~/.claude/skills/
├── 📄 README.md
├── 🔧 setup.sh              # One-click setup script
├── 📝 .gitignore
├── 🔗 .gitmodules           # Submodule definitions
│
├── 💬 Prompt-only skills
│   ├── article-extractor/
│   ├── brainstorming/
│   └── ...
│
├── 🐍 Python skills
│   ├── docx/
│   ├── pdf/
│   └── ...
│
├── 🟢 Node.js skills
│   ├── playwright-skill/
│   └── n8n-skills/
│
└── 🔗 Third-party submodules
    ├── claude-d3js-skill/
    ├── notebooklm-skill/
    └── ...
```

---

## 📋 Requirements

| Requirement | Version | Purpose |
|:------------|:--------|:--------|
| Git | 2.x+ | Repository management |
| Python | 3.10+ | Python-based skills |
| Node.js | 18+ | Node.js-based skills |
| Claude Code | Latest | CLI tool |

---

## ❓ Troubleshooting

<details>
<summary><b>Submodules are empty</b></summary>

```bash
git submodule update --init --recursive
```

</details>

<details>
<summary><b>Permission denied on setup.sh</b></summary>

```bash
chmod +x setup.sh
./setup.sh
```

</details>

<details>
<summary><b>NotebookLM browser issues on headless server</b></summary>

NotebookLM requires a display for browser automation. Options:
- Use Xvfb for virtual display
- Run authentication on a machine with display first
- Use SSH with X11 forwarding

</details>

---

## 📜 License

Individual skills retain their original licenses. See each skill directory for details.

---

## 🙏 Credits

Skills curated from [awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) community collection.

<p align="center">
  <sub>Made with ❤️ for Claude Code</sub>
</p>
