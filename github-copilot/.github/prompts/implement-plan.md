---
mode: "agent"
description: "Implement features based on comprehensive requirements documents"
tools: ['changes', 'codebase', 'editFiles', 'extensions', 'fetch', 'findTestFiles', 'githubRepo', 'new', 'openSimpleBrowser', 'problems', 'runCommands', 'runNotebooks', 'runTasks', 'search', 'searchResults', 'terminalLastCommand', 'terminalSelection', 'testFailure', 'usages', 'vscodeAPI']
---

# Implement Requirements

Implement a feature based on the planning document provided as input.

**Important**: This agent follows a systematic 6-step implementation process to ensure
comprehensive feature delivery. The requirements document contains all necessary context
for autonomous implementation.

## Requirements File Input

The requirements document path will be provided as input. Read and follow all
instructions in the requirements document completely.

## Execution Process

### 1. Load the Requirements Document

- Read the specified requirements document thoroughly
- Understand the context, constraints, and all requirements
- Follow all instructions in the requirements document exactly
- Ensure you have all needed context to implement the requirements fully
- Perform additional web and codebase search as necessary to fill any gaps

### 2. Plan the Implementation

- Think before you execute the plan. Create a comprehensive plan addressing all requirements
- Break down complex tasks into smaller, manageable steps using TODO tracking
- Use task management tools to create and track your implementation plan
- Identify implementation patterns from existing code to follow
- Reference the architectural patterns and conventions specified in the requirements

### 3. Execute the Plan

- Implement the requirements from the requirements document systematically
- Write all necessary code following the patterns and conventions identified
- Follow the ordered implementation path provided in the requirements
- Ensure integration with existing codebase as specified
- Implement comprehensive error handling as documented

### 4. Validate

- Run each validation gate specified in the requirements document
- Execute all test commands (e.g., `npm test`, `dotnet test`)
- Run linting and code quality checks
- Perform any performance benchmarks if applicable
- Fix any failures that occur
- Re-run until all validation gates pass

### 5. Complete

- Ensure all checklist items from the requirements are done
- Run final validation suite to confirm everything works
- Report completion status with summary of implemented features
- Read the requirements document again to ensure you've implemented everything
- Verify all main flow and alternate scenarios are covered

### 6. Reference the Requirements Document

- You can always reference the requirements document again for clarification
- If any requirement is unclear, implement based on the best practices and patterns identified
- Use the code examples and file references provided in the requirements

## Implementation Guidelines

### Code Quality
- Follow existing architectural patterns and conventions
- Mirror the coding style and patterns from referenced files
- Implement comprehensive error handling as specified
- Ensure proper integration with existing systems

### Testing and Validation
- Execute all validation gates in the specified order
- Address any test failures immediately
- Ensure all code quality checks pass
- Verify performance meets any specified benchmarks

### Documentation
- Update relevant documentation if specified in requirements
- Follow documentation patterns established in the codebase
- Include any necessary inline code comments

## Success Criteria

Implementation is complete when:
- All requirements from the document are implemented
- All validation gates pass
- Code follows established patterns and conventions
- Integration with existing systems works correctly
- All error handling scenarios are covered
- Performance meets specified criteria

The implementation should be ready for production use without additional modifications.
