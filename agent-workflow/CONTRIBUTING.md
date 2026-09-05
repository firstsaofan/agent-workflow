# Contributing to Agent Workflow

Thank you for your interest in contributing to Agent Workflow! This document provides guidelines and information for contributors.

## How to Contribute

### Reporting Issues

If you find a bug or have a suggestion:

1. Check existing issues to avoid duplicates
2. Create a new issue with:
   - Clear title
   - Description of the problem or suggestion
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior

### Submitting Changes

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Make your changes
4. Test your changes with a real project
5. Commit with clear message: `git commit -m "Add: description of change"`
6. Push to your fork: `git push origin feature/your-feature`
7. Create a Pull Request

## What We're Looking For

### High Priority

- **Tech-stack presets**: Add presets for popular frameworks
  - React/Next.js
  - Vue/Nuxt
  - Spring Boot
  - Rails
  - Laravel
  - Flutter
  - etc.

- **Integration guides**: How to use with specific tools
  - Cursor setup guide
  - DeepSeek configuration
  - VS Code + Copilot
  - etc.

- **Examples**: Real-world usage examples
  - Small project example
  - Team project example
  - Enterprise example

### Medium Priority

- **Improvements to prompts**: Better agent prompts
- **New scenarios**: Additional workflow scenarios
- **Documentation**: Translations, tutorials, guides
- **Bug fixes**: Any issues you find

### Low Priority

- **Formatting improvements**
- **Typo fixes**
- **Additional comments**

## Tech-Stack Preset Template

When adding a new tech-stack preset, use this template:

```markdown
# Tech Preset: [NAME]

## File Scope Rules

### Frontend Agent Scope
- Files: [list file patterns]
- Test command: [command]
- Build command: [command]

### Backend Agent Scope
- Files: [list file patterns]
- Test command: [command]
- Build command: [command]

## Project Detection
- How to identify this tech stack
- Key config files

## Common Agent Commands
- Install dependencies: [command]
- Run tests: [command]
- Run linter: [command]
- Build: [command]

## File Patterns to Protect
- [list patterns]

## .editorconfig Snippet
[stack-specific config]

## .gitignore Additions
[stack-specific ignores]
```

Save as: `references/tech-presets/your-stack.md`

## Code Style

- Use clear, concise language
- Write in English (translations welcome)
- Use markdown formatting
- Keep lines under 80 characters when possible
- Use consistent indentation (2 spaces for markdown)

## Commit Messages

Use clear, descriptive commit messages:

- `Add: React tech-stack preset`
- `Fix: incorrect file scope in backend agent prompt`
- `Update: tutorial with new examples`
- `Docs: improve contributing guidelines`

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Questions?

If you have questions about contributing, feel free to open an issue with the label "question".

Thank you for helping make Agent Workflow better!
