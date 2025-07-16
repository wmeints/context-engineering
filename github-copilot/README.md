# Context Engineering with Github Copilot in Visual Studio Code

This folder contains the necessary setup to get started with Context Engineering in
Visual Studio Code. Please follow the instructions to apply the files to your own
project.

## Getting started

### Cloning the repository

First, clone this repository to disk:

```bash
git clone https://github.com/wmeints/context-engineering/
```

### Setting up the project

Then, copy the following files to your project:

```text
github-copilot/.github/prompts/generate-plan.prompt.md      # Prompt to generate a requirements document
github-copilot/.github/prompts/implement-plan.prompt.md     # Prompt to generate a requirements document
github-copilot/.github/copilot-instructions.md              # Project-level instructions for Github Copilot
github-copilot/docs/requirements/.gitkeep                   # Directory for storing requirements documents
github-copilot/TASK.md                                      # The template for the initial feature description
```

If you're using this on a completely new repository I recommend setting up the
project structure using some kind of project template first. For example, you
can use `create-react-app`, `dotnet new`, `quarkus create app`, or `uv init`
to start new projects in various languages. **Setting up a completely new
project structure with an LLM is bad idea**.

**Important**: Make sure you have
[the web search extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-websearchforcopilot)
installed in VSCode and configured. You'll need it to get high quality requirements
documents.

### Writing the initial context

To start working on the project, make sure to fill in the details in the
`.github/copilot-instructions.md` file. You'll need to provide the following:

- **Goals for the solution**: What is the solution supposed to do?
- **Technology stack**: What technology stack do you want to use?
- **Project structure**: How is the project structured?
- **Testing the project**: How do you want things to be tested?
- **Documenting the code**: Where and how should details be documented?

I recommend writing short and concise instructions for the LLM. This helps
keep enough space available in the context window for actual work.

**Tip**: Unsure of what to write in the `copilot-instructions.md` file for your project?
You can ask Copilot to write the file for you. In the latest release you can
run `Ctrl+Shift+P` (`Cmd+Shift+P` on mac) and type in "generate instructions". 

### Writing work item instructions

After you've configured the instructions for your project you can start to work on
implementing features. I added two methods for this:

1. Planning work with Github Issues
2. Planning work with TASK.md on your local computer

#### Planning work with TASK.md on your local computer

The process of implementing a feature using the context engineering approach
starts with generating an implementation plan. If you want to work locally without GitHub 
you can edit the `TASK.md` file in the root of the repository with the following content:

```text
# Feature: <Feature Name>

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

#### Generate a requirements document

After you've created the work item in `TASK.md`, you can start to generate requirements.
Open the Github Copilot Chat window in VSCode and enter the following command:

```bash
/generate-plan
```

**Important:** Make sure that you're using Agent Mode!

It will take a few minutes for Github Copilot to write the full requirements document.
You can continue to iterate on the requirements file in the same chat window.

The generated requirements document will be stored in the `docs/requirements`
directory.

Once you're happy with the requirements, you can start to generate code. If you find that
the generated requirements get too large, you can split the file into multiple separate
requirements documents. You can even ask Github Copilot to do this for you.

#### Generating code

Open the generated requirements document, and type the following command in the Github
Copilot Chat window making sure you're using Agent Mode.

```bash
/implement-plan
```

This will again take a few minutes to complete. This is a great time to get
hydrated, take a bio break, and talk to a colleague.

### Planning work with Github Issues

If you prefer to use Github Issues as the basis for your feature implementation you
can skip writing the `TASK.md` file and use the `/plan-gh-issue: issue={issue-number}`
prompt. Replace `{issue-number}` with the actual issue number.

The implementation plan will be posted as comment to your issue so you can edit and
refine the plan on Github. As with all prompts, you can continue to iterate in the chat
window.

After generating the plan, you can implement the GitHub issue with the prompt `/implement-gh-issue: issue={issue-number}`.
Replace `{issue-number}` with the actual issue number.

### Reviewing code

Once you have the code it's important to verify that the code is to your liking.
You can ask Github Copilot to review the code for you.

I recommend manually reviewing your code because the AI can't catch every
problem in your code.

## Tips and tricks

### :bulb: Break up tasks into smaller pieces

I recommend taking a close look at the generated requirements and breaking them
up into smaller chunks. While Github Copilot can write impressive amounts of
correct code, it's quite hard for you to review since you'll be quickly overwhelmed.

I typically copy/paste chunks into new markdown files, but of course you can
ask Github Copilot to split the generated requirements into smaller chunks in a
more semantic way.

### :bulb: Add project documentation

The more details you can provide about your solution in documentation the
easier it will be for Github Copilot to find out how to approach the problem. I
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

Configure instruction files in your VSCode user settings for personal communication preferences.
You can find more about this [in the manual](https://code.visualstudio.com/docs/copilot/copilot-customization#_specify-custom-instructions-in-settings).

### :bulb: Add more hierarchy in the instructions

This template uses a single `.github/copilot-instructions.md` file but you can add more
detail by putting additional `*.instructions.md` files in the `.github/instructions` directory.
[Please refer to the documentation](https://code.visualstudio.com/docs/copilot/copilot-customization#_use-instructionsmd-files)
how to use these files.
