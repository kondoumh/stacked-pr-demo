# Stacked PR Demo

This repository is a minimal example for trying GitHub Stacked Pull Requests locally.

## Branch flow
- main: base branch
- feature/01-setup: adds initial project files
- feature/02-add-logic: adds sample logic
- feature/03-add-docs: adds documentation and workflow notes

## Local workflow
1. Create a branch from the previous branch in the stack.
2. Open a PR targeting that previous branch.
3. Merge the earlier PR and continue the chain.
