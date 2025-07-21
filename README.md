# claude-keeps-em-tidy

Letting Claude handle our PR reviews and regular doc updates, because humans need sleep and coffee.

## What This Does

This repository provides automated GitHub workflows that use Claude AI to:

- **🔍 Automated PR Reviews**: Claude reviews every pull request against custom coding standards and provides detailed feedback
- **📚 Weekly README Updates**: Claude analyzes code changes weekly and updates documentation automatically
- **💬 Interactive Claude Support**: Mention `@claude` in PR comments to get instant AI assistance

## Features

### Automated Code Reviews
- Triggers on every PR open/update
- Reviews against configurable rules in `agent.md`
- Provides risk classification (Low/High)
- Offers specific improvement suggestions
- Includes usage metrics and cost tracking

### Weekly Documentation Updates
- Runs every Monday at 12:30 AM UTC
- Analyzes last 7 days of commits
- Updates README.md with relevant changes
- Creates pull requests for review
- Skips updates when no meaningful changes detected

### Manual Claude Interaction
- Mention `@claude` in PR comments for manual assistance
- Works in issue comments, PR reviews, and issues
- Uses Claude Sonnet 4 model for best performance

## Setup

1. **Add API Key**: Set `ANTHROPIC_API_KEY` in repository secrets
2. **Configure Rules**: Edit `agent.md` to define your code review standards
3. **Enable Workflows**: Workflows are automatically active once files are in `.github/workflows/`

## Configuration

### Code Review Rules (`agent.md`)
The PR review process follows rules defined in `agent.md`:
- Code quality standards (DRY, naming conventions)
- Security requirements (no secrets, input validation)
- API design guidelines (error handling, backward compatibility)
- Risk classification criteria

### Workflow Permissions
- **PR Assistant**: `contents:read`, `pull-requests:write`, `issues:write`
- **README Update**: `contents:write`, `pull-requests:write`

## Repository Structure

```
├── .github/workflows/
│   ├── pr_assistant.yml      # Claude PR review automation
│   └── readme-update.yml     # Weekly README updates
├── agent.md                  # Code review rules and guidelines
└── README.md                # This file
```

## How It Works

1. **PR Reviews**: When a PR is opened, Claude analyzes the changes against rules in `agent.md`
2. **Documentation**: Weekly cron job analyzes commits and updates README if needed
3. **Manual Support**: `@claude` mentions trigger interactive assistance

---

*Last updated: 2025-07-21 - Maintenance updates*
