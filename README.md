# Context Engineering

This repository is an experimental approach to software engineering with the
help of agents based on the principle of Context Engineering. Currently I am
testing this approach with [Claude Code](https://www.anthropic.com/claude-code).

**Important**: I'm still testing many things, but here's the initial
version of what I'm up to.

## What is context engineering?

Context engineering is a systematic methodology for optimizing AI agent
performance in software development tasks by strategically curating and
structuring the information provided to the agent. Rather than giving agents
brief, ad-hoc instructions, context engineering emphasizes deliberate
preparation of comprehensive context that enables agents to produce
higher-quality, more consistent results.

### Core Principles

**1. Layered Context Architecture**

- **Project-level context** (CLAUDE.md): Architecture, technology stack,
  coding standards, and testing approaches
- **Task-level context** (TASK.md): Feature descriptions, examples,
  documentation references, and special considerations
- **Requirements context**: Detailed implementation blueprints generated
  through research and analysis

**2. Research-Driven Requirements Generation**
The methodology employs a two-phase approach:

- **Phase 1**: Generate detailed requirements documents through systematic
  research of the codebase, external documentation, and best practices
- **Phase 2**: Implement features using the enriched requirements rather
  than original brief descriptions

**3. Self-Validating Workflows**
Context engineering incorporates validation gates and quality checklists that
enable agents to verify their own work against established criteria.

### Key Benefits

- **Higher Code Quality**: Agents have access to comprehensive context including existing patterns, conventions, and architectural decisions
- **Documentation as a Byproduct**: Requirements documents serve as lasting project documentation
- **Reduced Iteration Cycles**: Well-researched context reduces the need for back-and-forth clarification
- **Consistency**: Structured approach ensures consistent code quality across different features and team members

### Implementation Framework

The methodology provides concrete tools including command templates for
requirements generation (`/generate-requirements`) and
implementation (`/implement-requirements`), along with quality scoring
mechanisms to assess the completeness of context before proceeding with
implementation.

Context engineering represents a shift from prompt engineering to systematic
context curation, treating AI agents as collaborative team members who benefit
from the same thorough preparation and documentation that human developers
require for complex tasks.

## Getting started

To help you get started with context engineering, I made this repository. I've created
two versions of my approach. One for
[Github Copilot in VSCode](https://code.visualstudio.com/docs/copilot/overview) and one
for [Claude Code](https://www.anthropic.com/claude-code)

Choose your own adventure:

1. [Github Copilot](./github-copilot/README.md)
2. [Claude Code](./claude-code/README.md)

## Feedback/Ideas

Have you used my templates and have improvement ideas?
[Leave an issue in this repository](https://github.com/wmeints/context-engineering/issues)!
