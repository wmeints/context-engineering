# Create requirements document

## Feature: $ARGUMENTS

Generate a complete requirements document for feature implementation based on
thorough research. Ensure context is passed to the agent to enable
self-validation and iterative improvements. Read the requirements file first
to understand what needs to be done, how examples provided help, and any
other considerations.

The agent only gets access to the context you're appending to the requirements
document. Assume that the agent has access to the code base and the same
knowledge cut-off as you, so it's important that your research is included or
referenced in the requirements document. The agent has websearch capabilities,
so pass URLs to documentation and examples.

## Research process

1. **Codebase analysis**

- Search for similar patterns/features in the code base
- Identify files to reference in the requirements document
- Note existing conventions to follow
- Check test patterns for validation

2. **External research**

- Search for similar features/patterns online
- Library documentation (include specific URLs)
- Implementation examples (Github/blogs)
- Best practices and common pitfalls

3. **User clarification**

- Specific patterns to mirror and where to find them
- Integration requirements and where to find them

## Requirements document generation

### Critical context to pass

- **Documentation**: URLs to specific sections
- **Code Examples**: Real snippets from the code base
- **Gotchas**: Library quirks, version issues
- **Patterns**: Existing approaches to follow

### Implementation blueprint

- Start with pseudocode showing the approach
- Reference real files for patterns
- Include error handling strategies
- List tasks to be completed to fulfill the requirements in order of completion

### Validation gates

```bash
dotnet test
```

It's important to verify the requirements and plan your approach before
writing the requirements document.

## Output

Save the requirements as `docs/requirements/{feature-name}.md`

## Quality checklist

- [ ] All necessary context is included
- [ ] Validation gates are executable by the agent
- [ ] References existing patterns
- [ ] Clear implementation path
- [ ] Error handling is documented
- [ ] Main flow is documented
- [ ] Alternate flows are documented

Score the requirements document on a scale from 1 - 10
(confidence level to succeed in one pass implementation using claude code).
