# Generate Implementation Plan from GitHub Issue

## Issue: $ARGUMENTS

Generate a complete implementation plan for a GitHub issue based on thorough
research. **Start by researching the issue** from the provided GitHub issue URL
or issue description to understand what needs to be done, how examples provide
help, and any other considerations.

**Important**: The implementation plan will be used by another Claude Code agent for
implementation. Include all necessary context since the implementing agent only gets
access to what you document here. The agent has access to the codebase and web search
capabilities, so include specific URLs and code references.

## Research Process

### 0. Issue Analysis

- Research the GitHub issue using web search if URL provided, or analyze the provided issue description
- Extract the feature description, examples, documentation references, and considerations
- Use this as the foundation for all subsequent research

### 1. Codebase Analysis

- Search for similar patterns/features in the workspace
- Identify files to reference in the requirements document
- Note existing conventions and architectural patterns to follow
- Check test patterns and validation approaches

### 2. External Research

- Find relevant library documentation using web search (include specific URLs)
- Look for implementation examples and best practices
- Identify common pitfalls and gotchas
- Research integration patterns and similar implementations

### 3. Context Gathering

- Identify specific patterns to mirror and their locations
- Document integration requirements and dependencies
- Note any version-specific considerations

## Requirements Document Structure

### Critical Context to Include

- **Documentation URLs**: Link to specific sections found through web search
- **Code Examples**: Real snippets from the codebase showing patterns to follow
- **Architectural Patterns**: Existing approaches that should be mirrored
- **Integration Points**: How this feature connects with existing code
- **Gotchas**: Library quirks, version issues, common mistakes

### Implementation Blueprint

- Start with high-level approach and pseudocode
- Reference specific files for patterns to follow
- Include comprehensive error handling strategies
- Provide ordered task list for step-by-step implementation
- Document validation and testing approach

### Validation Gates

Define specific commands and criteria for validation:

- Test commands (e.g., `npm test`, `dotnet test`, `python -m pytest`)
- Linting and code quality checks
- Performance benchmarks if applicable
- Integration test requirements

## Output Requirements

Save the implementation plan as `docs/implementation-plans/gh-issue-{issue-number-or-name}.md`.
The plan should be structured, clear, and detailed enough for another Claude Code agent
to implement without needing further clarification.

## Quality Checklist

Before finishing, verify the requirements include:

- [ ] All necessary context for autonomous implementation
- [ ] Validation gates that are executable
- [ ] References to existing patterns and conventions
- [ ] Clear, ordered implementation path
- [ ] Comprehensive error handling documentation
- [ ] Main flow and alternate scenarios covered
- [ ] Specific code examples and file references
- [ ] Research from external sources with URLs

**Quality Score**: Rate the requirements document on a scale from 1-10 for confidence
in successful single-pass implementation using Claude Code. Explain the score and
suggest improvements if below 8.

