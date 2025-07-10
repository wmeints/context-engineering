# Github Copilot Instructions

Follow these instructions when writing code or documentation for the project.

## Project goals

TODO: Describe the goals of the project

## Project Structure

TODO: Describe your project structure

- **Tip** Are you using feature slicing or clean architecture?
- **Tip** Where are projects located in the directory structure?
- **Tip** What does each of the projects do in the solution?

## Technology stack

TODO: Describe your technology stack

- **Tip** How do the technologies map on the project structure?
- **Tip** How are technologies used?

## Testing the project

- Always create unit-tests for components you introduce into the application.
- After changing or introducing new logic make sure that the tests are updated
  to match the new situation.
- Include at least the following types of test cases:
  - 1 test case for the expected use
  - 1 edge case
  - 1 failure case

## Documenting the code

Make sure to document the code properly in the architecture documentation
located at `docs/architecture`. We follow the arc42 template for structuring
the architecture documentation.

When changing code, make sure to:

- Document important structures in the building blocks view
- Document important flows in the runtime view
- Update the glossary with new terms introduced in the feature
