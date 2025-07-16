---
mode: "agent"
description: "Generate comprehensive implementation plan through systematic research"
tools: ['codebase', 'fetch', 'findTestFiles', 'githubRepo', 'runCommands', 'search', 'searchResults', 'usages', 'github', 'add_issue_comment', 'get_issue', 'get_issue_comments', 'list_issues', 'search_issues', 'update_issue']
---

# Generate Implementation Plan

Generate a complete implementation plan for a GitHub issue based on thorough
research. **Start by reading issue  ${input:issue}** to understand what needs to be done, how
examples provide help, and any other considerations.

**Important**: The implementation plan will be used by another AI agent for
implementation. Include all necessary context since the implementing agent only gets
access to what you document here. The agent has access to the codebase and web search
capabilities, so include specific URLs and code references.

## Research Process

### 0. Task Analysis

- Read the referenced issue ${input:issue} in `wmeints/agenttalks` GitHub repository in the project root
- Extract the feature description, examples, documentation references, and considerations
- Use this as the foundation for all subsequent research

### 1. Codebase Analysis

- Search for similar patterns/features in the workspace
- Identify files to reference in the requirements document
- Note existing conventions and architectural patterns to follow
- Check test patterns and validation approaches

### 2. External Research

- Find relevant library documentation (include specific URLs)
- Look for implementation examples and best practices
- Identify common pitfalls and gotchas
- Research integration patterns

### 3. Context Gathering

- Identify specific patterns to mirror and their locations
- Document integration requirements and dependencies
- Note any version-specific considerations

## Requirements Document Structure

### Critical Context to Include

- **Documentation URLs**: Link to specific sections
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

- Test commands (e.g., `npm test`, `dotnet test`)
- Linting and code quality checks
- Performance benchmarks if applicable
- Integration test requirements

## Output Requirements

Append the implementation plan to the issue as a comment. The plan should be structured, clear, and
detailed enough for another AI agent to implement without needing further clarification.

## Quality Checklist

Before finishing, verify the requirements include:

- [ ] All necessary context for autonomous implementation
- [ ] Validation gates that are executable
- [ ] References to existing patterns and conventions
- [ ] Clear, ordered implementation path
- [ ] Comprehensive error handling documentation
- [ ] Main flow and alternate scenarios covered
- [ ] Specific code examples and file references

**Quality Score**: Rate the requirements document on a scale from 1-10 for confidence in successful single-pass implementation. Explain the score and suggest improvements if below 8.
