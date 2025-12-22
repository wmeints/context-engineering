The documentation should have four main sections:

- Principles
- Approach
- Implementing context engineering
- Examples

## Introduction

### Why use AI in software development



## Principles

The goal of the principles section is to explain the basic rules for our context
engineering approach. It should cover the following principles:

1. We aim to resolve bottlenecks in the development workflow. Using AI isn't a goal by itself.
   AI helps us speed up the development process, and helps us improve quality.

2. We acknowledge that AI isn't perfect. We're embracing that imperfection. The human
   developer leads and the AI follows. We expect the developer to finalize the work
   after the AI is done.

3. We provide a flexible workflow, because every project is different and every
   developer will be at a different level of maturity when it comes to using AI. We also
   acknowledge that sometimes it's better not to use AI and build it yourself.
   Developers are encouraged to modify the workflow whenever they feel the need to. They
   own the agents, prompts, skills, and other content used in context of their project.

4. We use agents with specific instructions to build a virtual team for the developer
   to delegate work to. We use mob elaboration to help the developer work on specification
   and mob construction principles to help the developer build the software.

5. We use templates, and tools where it makes sense instead of delegating everything
   to AI, because templates, and tools are faster, cheaper, and more stable. Only when
   we can't solve it with templates or tools we'll use AI and accept that it can get it
   wrong.

6. We provide composable configuration of the context engineering approach to make it
   easy to replace instructions or to extend the approach with new insights as we learn
   how to use agents in our software projects.

7. We believe that we're constantly learning how to improve our approach. So we
   continuously improve the agents, documentation, and help you share your experience
   with others.

## Approach

The goal of the approach section is to explain how the context engineering approach works.
We should explain how the principles from the previous section can be translated into a workflow.

Teams should be able to choose their own approach. We need to support their approach by providing
the right agents and help them configure agents so they work for their setup.

We can inspire readers with a few example workflows

- 100% spec-driven workflow where we use a spec as input, generate an implementation plan,
  write code, review the code, and run tests all by applying agents.
- alternatively, we can show a workflow where developers build small layers of functionality
  with more control over the actual code. 
- finally, we can show a workflow where the developer does most of the work and the AI supports
  where the developer wants to delegate certain tasks in their workflow.

We should explain the pros and cons of each approach and explain when to choose an approach.

## Implementing context engineering

The goal of the implementation section is to explain how we integrate our context engineering
tools into the environment of the engineer. 

This is how we plan to implement context engineering in a typical project:

- We add an AGENTS.md/CLAUDE.md file to the root of the project as the main entrypoint for the
  coding agent to understand the project. We call this the agent instruction file. In the 
  agent instruction file we explain the purpose of the project, the technology stack, and the
  overall structure of the project. This file should be short and point to more detailed instructions
  elsewhere in the project.
- We add several agent definitions to the project to fulfill roles in the project:
  - Specification writer: Instructed to help write specifications for the project.
  - Specification reviewer: Instructed to help review specifications for the project.
  - Planner: We don't provide a specific planning agent, instead we should point the developer towards the plan mode in Github Copilot/Claude Code to and help them how to translate specifications into implementation plans
  - Code reviewer: Instructed to review the code changes in the project.
    - Security officer
    - Test code reviewer
    - ...
- Each agent we provide should have their own instruction file, but point to specific configuration in the
  `docs/agents/<agent-name>/` directory to help the developer with any customization needs.
  When an agent needs information about the project architecture, we need to point it to a document
  in `docs/architecture`. Likewise for product requirements, we can point the agent to `docs/product`.

## Examples

The previous section explains how to implement context engineering in a project. The examples section
should provide links to example configurations for the following project types:

- Monorepo implementation of a microservice application
- Implementation of a .NET application
- Implementation of a Java application
- Implementation of a Typescript application
- Implementation of a Python application
  - Additional instructions for a package
  - Additional instructions for an agent
  - Additional instructions for an API
