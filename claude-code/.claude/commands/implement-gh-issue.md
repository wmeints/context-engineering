# Implement GitHub Issue

Implement a feature based on a GitHub issue implementation plan.

## Issue: $ARGUMENTS

## Execution process

1. **Load the implementation plan**

- Look for the implementation plan in `docs/implementation-plans/gh-issue-{issue-number-or-name}.md`
- If no plan exists, inform the user they need to run `/plan-gh-issue` first
- Read and understand the context and requirements from the plan
- Follow all instructions in the implementation plan document
- Ensure you have all needed context to implement the requirements fully
- Do more web and code base search as necessary

1. **Plan the implementation**

- Think before you execute the plan. Create a comprehensive plan addressing all requirements.
- Break down complex tasks into smaller, manageable steps using your TODO tools.
- Use the TodoWrite tool to create and track your implementation plan.
- Identify implementation patterns from existing code to follow as specified in the plan.

1. **Execute the plan**

- Implement the requirements from the implementation plan document
- Write the code necessary following the architectural patterns identified
- Reference the specific files and examples mentioned in the plan
- Follow the ordered task list provided in the implementation blueprint

1. **Validate**

- Run each validation gate specified in the plan
- Execute test commands, linting, and quality checks as documented
- Fix any failures
- Re-run until all validation gates pass

1. **Complete**

- Ensure all checklist items from the plan are done
- Run final validation suite
- Report completion status
- Read the implementation plan again to ensure you've implemented everything

1. **Reference the implementation plan**

- You can always reference the implementation plan document again
- The plan contains all the research and context needed for successful implementation

## Usage

Use this command by providing the same identifier used in `/plan-gh-issue`:

- `/implement-gh-issue 123` (for issue number 123)
- `/implement-gh-issue feature-name` (for issues saved by name)
- `/implement-gh-issue https://github.com/owner/repo/issues/123` (will extract issue number)

The command will automatically locate the corresponding implementation plan file.
