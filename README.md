# dotclaude

Personal Claude Code configuration - portable across environments.

## Quick Start

```bash
# Clone the repository
git clone https://github.com/ShunmeiCho/dotclaude.git ~/dotclaude
cd ~/dotclaude

# Install configuration (interactive)
./install.sh

# Install skill dependencies (optional)
./setup.sh
```

## Repository Structure

```
dotclaude/
├── install.sh           # Deploy configs to ~/.claude/
├── setup.sh             # Install skill dependencies
├── CLAUDE.md            # User instructions (thinking protocol, RIPER-5)
├── settings.json        # Claude Code settings (plugins, etc.)
├── mcp.json             # MCP server configuration
├── skills/              # 41 Skills
│   ├── ccxt/            # Cryptocurrency trading
│   ├── claude-code-guide/
│   ├── postgresql/
│   ├── playwright-skill/
│   └── ...
└── resources/           # Reference materials
    ├── documents/       # Methodology, tutorials
    └── prompts/         # System prompts, templates
```

## Installation Options

### Interactive Mode
```bash
./install.sh
```
Choose between symlink (recommended) or copy mode.

### Symlink Mode (Recommended)
```bash
./install.sh --link
```
Creates symlinks to this repo. Changes sync automatically.

### Copy Mode
```bash
./install.sh --copy
```
Copies files to `~/.claude/`. Standalone installation.

### Skills Only
```bash
./install.sh --skills-only
```
Only install skills, keep existing CLAUDE.md and configs.

## Skills (41)

### Development Workflow
- `brainstorming` - Creative exploration before implementation
- `test-driven-development` - TDD workflow
- `git-pushing` - Commit and push workflow
- `software-architecture` - Architecture design
- `prompt-engineering` - LLM prompt optimization

### Document Processing
- `docx` / `pdf` / `pptx` / `xlsx` - Office documents

### Database
- `postgresql` - PostgreSQL
- `timescaledb` - Time-series database

### Cryptocurrency
- `ccxt` - Trading library
- `coingecko` - Market data
- `cryptofeed` - Real-time feeds
- `hummingbot` - Trading bot
- `polymarket` - Prediction markets

### Claude Ecosystem
- `claude-code-guide` - Claude Code 高级开发指南
- `claude-cookbooks` - API examples
- `claude-skills` - Skill creation guide

### Tools
- `playwright-skill` - Browser automation
- `telegram-dev` - Telegram development
- `proxychains` - Network proxy

## Configuration Files

### CLAUDE.md
Contains:
- Deep thinking protocol with `ultrathink` trigger
- RIPER-5 programming mode system (Research/Innovate/Plan/Execute/Review)
- Code quality standards
- Output format specifications

### settings.json
```json
{
  "enabledPlugins": {
    "claude-mem@thedotmack": true,
    "document-skills@anthropic-agent-skills": true,
    "superpowers@superpowers-marketplace": true
  },
  "alwaysThinkingEnabled": true
}
```

### mcp.json
```json
{
  "mcpServers": {
    "notion": {
      "url": "https://mcp.notion.com/mcp"
    }
  }
}
```

## Updating

```bash
cd ~/dotclaude
git pull

# If using symlinks, changes apply automatically
# If using copy mode, re-run install
./install.sh --copy
```

## Resources

The `resources/` directory contains reference materials:

- `documents/` - Methodology guides, tutorials
- `prompts/` - System prompt examples, coding prompts
  - `system_prompts/CLAUDE.md/` - 10 CLAUDE.md variants

## License

MIT
