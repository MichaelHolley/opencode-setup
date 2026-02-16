---
description: Create a GitHub pull request for the current branch
agent: build
---

STEPS:

1. Identify the current branch name.
2. Use the GitHub MCP or GitHub CLI to check if a pull request already exists for the current branch.
3. If a pull request already exists, display the PR link to the user and terminate the command.
4. If no pull request exists, search the repository for a pull request template file (e.g., `.github/PULL_REQUEST_TEMPLATE.md`).
5. If a template is found, use it to prepare the pull request body.
6. Create the pull request using the GitHub MCP or GitHub CLI. If no template was found, use the `--fill` flag (if using CLI) or equivalent to automatically generate the title and body from the branch's commits.
7. Confirm the successful creation of the pull request and provide the URL to the user.
