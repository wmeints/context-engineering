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

To help you get started with context engineering, I made this repository.
You can copy the contents of this repository to your project to get started
quickly.

### Cloning the repository

First, clone this repository to disk:

```bash
git clone https://github.com/wmeints/context-engineering/
```

### Setting up the project

Then, copy the following files to your project:

```
.claude/commands/generate-requirements.md    # Prompt template to create requirements documents.
.claude/commands/implement-requirements.md   # Prompt template to implement requirements.
requirements/.gitkeep                        # Folder to store the requirements documents.
src/.gitkeep                                 # Source folder (optional)
CLAUDE.md                                    # General instructions for the project
```

If you're using this on a completely new repository I recommend setting up the
project structure using some kind of project template first. For example, you
can use `create-react-app`, `dotnet new`, `quarkus create app`, or `uv init`
to start new projects in various languages. **Setting up a completely new
project structure with an LLM is bad idea**.

### Writing the initial context

To start working on the project, make sure to fill in the details in the
CLAUDE.md file. You'll need to provide the following:

- **Goals for the solution**: What is the solution supposed to do?
- **Technology stack**: What technology stack do you want to use?
- **Project structure**: How is the project structured?
- **Testing the project**: How do you want things to be tested?
- **Documenting the code**: Where and how should details be documented?

I recommend writing short and concise instructions for the LLM. This helps
keep enough space available in the context window for actual work.

### Writing the work item instructions

Before you start using Claude Code to write code, you'll need to come up with
an initial set of instructions for the requirements generation. Create a new
file `TASK.md` in the root of the repository with the following content:

```text
# Feature

<Describe the feature that you want to implement here.>

## Examples

<Insert examples here. You can provide them inline, or list files located in
the `examples` folder if you have longer examples.>

## Documentation

<Refer to any relevant documentation such as input from a client or online
documentation for libraries you want to use in the implementation later.>

## Other considerations

<Provide other considerations that are relevant to the feature. You can list
things here that the agent is missing a lot.>
```

I prefer to keep the `TASK.md` file checked in as a reminder to myself of what
I need to provide as input for generating requirements.

### Generate a requirements document

After you've created the requirements document, you can start to generate
requirements. Start Claude Code with `claude` and then issue the following
command:

```
/generate-requirements TASK.md
```

It will take a few minutes for Claude Code to write the full requirements
document. You can continue to iterate on the requirements manually or by
opening Claude Code in the terminal inside VSCode. The agent will automatically
focus on the requirements document when you have it open in VSCode alongside
Claude Code in the built-in terminal.

The generated requirements document will be stored in the `docs/requirements`
directory.

Once you're happy with the requirements, you can start to generate code.

### Generating code

Use the following command in the Claude Code terminal to kick off the
implementation of the generated requirements document.

```
/implement-requirements requirements/<your-requirements-doc.md>
```

This will again take a few minutes to complete. This is a great time to get
hydrated, take a bio break, and talk to a colleague.

### Reviewing code

Once you have the code it's important to verify that the code is to your liking.
You can do this by [configuring Claude Code as a
PR reviewer](https://docs.anthropic.com/en/docs/claude-code/github-actions).

I recommend manually reviewing your code because the AI can't catch every
problem in your code.

## Tips and tricks

### :bulb: Break up tasks into smaller pieces

I recommend taking a close look at the generated requirements and breaking them
up into smaller chunks. While Claude Code can write impressive amounts of
correct code, it's quite hard for you to review since you'll be overwhelmed.

I typically copy/paste chunks into new markdown files, but of course you can
ask Claude Code to split the generated requirements into smaller chunks in a
more semantic way.

### :bulb: Add project documentation

The more details you can provide about your solution in documentation the
easier it will be for Claude to find out how to approach the problem. I
recommend writing architecture documentation using
[Arc42](https://docs.arc42.org/home/) and storing it in the `docs/architecture`
directory in the project.

Requirements are already stored in `docs/requirements` to follow this
convention.

### :bulb: Use MCP Servers

One of the most powerful features of using an agent is the availability of the
Model Context Protocol (MCP). You can connect the agent to a lot more
context information through this protocol. Make sure to check out
the [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers)
repository for a collection of MCP servers that can provide additional
context information.

### :bulb: Store personal preferences

Add a `CLAUDE.local.md` to the project root with personal communication
preferences. Make sure you include only personal preferences. Place
project-level preferences in the `CLAUDE.md` file.

### :bulb: Add more hierarchy in the instructions

This template uses a single `CLAUDE.md` file in the root but you can add more
detail by putting a `CLAUDE.md` file within your project directories. For
example, you can provide specific instructions for your web frontend by placing
a `CLAUDE.md` in the web frontend directory.
