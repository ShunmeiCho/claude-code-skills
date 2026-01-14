# dotclaude

Personal Claude Code configuration - portable across environments.

## Quick Start

```bash
# Clone the repository
git clone https://github.com/ShunmeiCho/dotclaude.git ~/dotclaude
cd ~/dotclaude

# Install configuration (interactive)
./install.sh

# Configure MCP servers
./setup-mcp.sh

# Install skill dependencies (optional)
./setup.sh
```

## Repository Structure

```
dotclaude/
├── install.sh           # Deploy configs to ~/.claude/
├── setup.sh             # Install skill dependencies
├── setup-mcp.sh         # Configure MCP servers via CLI
├── .env.example         # API key template
├── CLAUDE.md            # User instructions
├── .mcp.json            # MCP server configuration
├── .claude/             # Claude Code configuration
│   ├── settings.json    # Official settings format
│   ├── commands/        # Custom slash commands
│   ├── rules/           # Modular rules
│   └── hooks/           # Hook scripts
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

## Installed Directory Structure

After installation, `~/.claude/` will contain:

```
~/.claude/
├── CLAUDE.md            # Project instructions
├── settings.json        # Claude Code settings
├── commands/            # Custom slash commands
├── rules/               # Modular rules
├── hooks/               # Hook scripts
├── skills/              # Skill modules
└── resources/           # Reference materials
```

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
- `claude-code-guide` - Claude Code development guide
- `claude-cookbooks` - API examples
- `claude-skills` - Skill creation guide

### Tools
- `playwright-skill` - Browser automation
- `telegram-dev` - Telegram development
- `proxychains` - Network proxy

## Configuration Files

### CLAUDE.md

Concise project guidelines following [official best practices](https://www.anthropic.com/engineering/claude-code-best-practices):
- Core principles
- Code quality standards
- Working style guidelines

### settings.json

Uses the [official JSON schema](https://json.schemastore.org/claude-code-settings.json):

```json
{
  "$schema": "https://json.schemastore.org/claude-code-settings.json",
  "permissions": {
    "allow": ["Bash(git status:*)", "Read(*)"],
    "deny": ["Read(.env)", "Read(**/*credentials*)"]
  }
}
```

### .mcp.json

Project-level MCP server configuration:

```json
{
  "mcpServers": {
    "notion": {
      "url": "https://mcp.notion.com/mcp"
    }
  }
}
```

### MCP Servers (setup-mcp.sh)

MCP servers are configured using the official `claude mcp add` command:

```bash
./setup-mcp.sh
```

**Core servers (no API key required):**
| Server | Type | Description |
|--------|------|-------------|
| Notion | HTTP | Notion workspace integration |
| GitHub | HTTP | GitHub repository operations |
| Playwright | Stdio | Browser automation |
| Chrome DevTools | Stdio | Browser debugging |

**Optional servers (require API keys):**
| Server | Environment Variable | Description |
|--------|---------------------|-------------|
| Context7 | `CONTEXT7_API_KEY` | Library documentation search |
| Perplexity | `PERPLEXITY_API_KEY` | AI-powered search |

To add optional servers:
```bash
cp .env.example .env
# Edit .env with your API keys
source .env
./setup-mcp.sh
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

## Official References

- [Claude Code Settings Documentation](https://code.claude.com/docs/en/settings)
- [Managing Memory (CLAUDE.md)](https://code.claude.com/docs/en/memory)
- [MCP Server Configuration](https://code.claude.com/docs/en/mcp)
- [Slash Commands](https://code.claude.com/docs/en/slash-commands)
- [Hooks Reference](https://code.claude.com/docs/en/hooks)
- [Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)

## License

MIT
