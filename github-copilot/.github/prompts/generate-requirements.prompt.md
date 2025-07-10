---
mode: "agent"
description: "Generate comprehensive requirements document through systematic research"
tools: ['codebase', 'fetch', 'githubRepo', 'runCommands', 'search', 'FastMCP', 'websearch']
---

# Generate Requirements Document

Generate a complete requirements document for feature implementation based on thorough
research. **Start by reading the TASK.md file** to understand what needs to be done, how
examples provided help, and any other considerations.

**Important**: The requirements document will be used by another AI agent for
implementation. Include all necessary context since the implementing agent only gets
access to what you document here. The agent has access to the codebase and web search
capabilities, so include specific URLs and code references.

## Research Process

### 0. Task Analysis
- **First step**: Read and analyze the TASK.md file in the project root
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

Save the requirements document as: `docs/requirements/{feature-name}.md`

The document should be comprehensive enough for autonomous implementation without additional clarification.

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
