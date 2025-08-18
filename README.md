# Claude Keeps 'Em Tidy 🤖

Letting Claude handle our PR reviews and regular doc updates, because humans need sleep and coffee.

## Overview

This repository showcases automated code maintenance using Claude AI through GitHub Actions. It demonstrates two key automation workflows:

- **🔍 Automated PR Review**: Claude analyzes pull requests against predefined coding standards and provides detailed feedback
- **📚 Weekly README Updates**: Claude automatically updates documentation based on code changes from the past week

## Features

### Automated PR Review
- Triggered automatically on PR creation and updates
- Manual trigger available via `@claude` mentions in comments
- Reviews code against comprehensive coding standards (see `agent.md`)
- Provides risk classification (Low/High) with justification
- Offers specific improvement suggestions with inline comments

### Weekly Documentation Updates
- Runs every Monday at 12:30 AM UTC via scheduled workflow
- Analyzes code changes from the past 7 days
- Updates README.md with relevant documentation changes
- Creates pull requests with detailed change summaries
- Includes usage metrics and analysis details

## Workflow Configuration

### PR Assistant (`pr_assistant.yml`)
- **Model**: Claude Sonnet 4 (claude-sonnet-4-20250514)
- **Triggers**: PR events, issue comments, manual `@claude` mentions
- **Rules**: Defined in `agent.md` covering code quality, security, and best practices

### README Updater (`readme-update.yml`)
- **Schedule**: Weekly on Mondays
- **Model**: Claude Sonnet 4 (claude-sonnet-4-20250514)  
- **Analysis**: Git diff, commit history, file changes over 7-day periods
- **Output**: Automated PR with documentation updates

## Setup Requirements

1. **GitHub Secrets**:
   - `ANTHROPIC_API_KEY`: Your Anthropic API key for Claude access

2. **Permissions**:
   - `contents: write` - For creating branches and commits
   - `pull-requests: write` - For creating and managing PRs
   - `issues: write` - For commenting on issues

## Code Review Standards

The automated reviews follow comprehensive guidelines covering:
- DRY principles and code organization
- Security best practices (no secrets, input validation)
- Error handling and API design
- Code documentation and naming conventions
- Testing requirements and type hints
- Performance and async programming patterns

*Last updated: 2025-08-18*
