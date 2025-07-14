# Context Engineering with Claude Code

This folder contains the necessary setup to get started with Context Engineering in
Claude Code. Please follow the instructions to apply the files to your own project.

## Getting started

### Cloning the repository

First, clone this repository to disk:

```bash
git clone https://github.com/wmeints/context-engineering/
```

### Setting up the project

Then, copy the following files to your project:

```text
claude-code/.claude/commands/generate-requirements.md    # Prompt template to create requirements documents.
claude-code/.claude/commands/implement-requirements.md   # Prompt template to implement requirements.
claude-code/requirements/.gitkeep                        # Folder to store the requirements documents.
claude-code/src/.gitkeep                                 # Source folder (optional)
claude-code/CLAUDE.md                                    # General instructions for the project
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

**Tip**: Unsure of what to write in the `CLAUDE.md` file for your project? 
You can ask Claude Code to generate the file for you. Use the `/init` 
command inside Claude Code to get an initial set of instructions based on
what your project looks like.

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

```bash
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

```bash
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
