# Claude Keeps 'Em Tidy

Automated development assistant that leverages Claude AI to handle PR reviews and maintain documentation. Because humans need sleep and coffee, but your code quality doesn't have to suffer.

## Features

### 🔍 Automated PR Reviews
- **Smart Code Analysis**: Claude reviews every pull request automatically
- **Risk Assessment**: Classifies PRs as low or high risk with detailed explanations
- **Code Quality Enforcement**: Checks against comprehensive coding standards
- **Manual Trigger**: Use `@claude` in comments to invoke additional analysis

### 📚 Automated Documentation Updates
- **Weekly README Updates**: Automatically analyzes code changes and updates documentation
- **Change Analysis**: Tracks commits, file changes, and code modifications
- **Smart Updates**: Only updates documentation when actual functional changes occur
- **Pull Request Workflow**: Creates organized PRs with detailed change summaries

## Setup

### Prerequisites
- GitHub repository with Actions enabled
- Anthropic API key for Claude access

### Installation

1. **Add API Key**: Add your Anthropic API key as `ANTHROPIC_API_KEY` in repository secrets

2. **Configure Workflows**: The following workflows are automatically available:
   - **PR Assistant** (`.github/workflows/pr_assistant.yml`): Triggers on PR creation/updates
   - **README Updates** (`.github/workflows/readme-update.yml`): Runs weekly on Mondays at 12:30 AM UTC

3. **Customize Review Rules**: Edit `agent.md` to modify Claude's review criteria

## Usage

### PR Reviews
- **Automatic**: Claude reviews all PRs automatically when opened or updated
- **Manual**: Comment `@claude` on any PR, issue, or review to trigger additional analysis
- **Features**: 
  - Code quality assessment
  - Security vulnerability detection
  - Performance optimization suggestions
  - Documentation completeness checks

### Documentation Updates
- **Automatic**: Runs weekly to analyze code changes and update README
- **Manual**: Use workflow dispatch to trigger immediate updates
- **Analysis**: Reviews commits, file changes, and code statistics from the past 7 days

## Review Standards

Claude enforces these coding standards:
- DRY (Don't Repeat Yourself) principles
- No secrets or credentials in code
- Proper error handling and validation
- Descriptive naming conventions
- Type hints and documentation
- Unit test coverage
- Security best practices

## Configuration

### Review Rules
Modify `agent.md` to customize:
- Code review criteria
- Risk assessment guidelines
- Style requirements
- Security checks

### Workflow Triggers
- **PR Reviews**: Automatic on PR events + manual via `@claude`
- **README Updates**: Weekly schedule + manual dispatch
- **Customizable**: Edit YAML files to adjust timing and triggers

## Model Information
- **Claude Model**: claude-sonnet-4-20250514
- **Capabilities**: Code analysis, documentation generation, security review
- **Performance**: ~30 second typical response time

---

*Last updated: 2025-07-14 - Automated by Claude*
