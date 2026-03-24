---
description: Rewrite a GitHub issue content to match repository templates or a standard format.
agent: build
---

STEPS:

1. Identify the issue number. If it was not provided as an argument, ask the user for it.
2. Retrieve the issue details (state, title, and body) using the GitHub CLI (`gh issue view <number> --json state,title,body`).
3. Check the issue state. If it is "CLOSED", inform the user and terminate.
4. Locate any GitHub issue templates in the repository (e.g., `.github/ISSUE_TEMPLATE/` or `.github/ISSUE_TEMPLATE.md`).
5. If templates exist:
    - Analyze the current issue's title and body.
    - Select the template that best matches the intent (e.g., Bug Report, Feature Request, Documentation).
    - Rewrite the title and body to strictly follow the chosen template's structure, populating sections with information from the original issue.
6. If no templates are found:
    - Rewrite the issue content to a high-quality, professional standard.
    - Include clear sections like "Problem Description", "Steps to Reproduce", "Expected Behavior", and "Proposed Solution" if applicable.
    - Ensure the title is concise and descriptive.
7. Update the issue on GitHub with the rewritten title and body using the GitHub CLI (`gh issue edit <number> --title "<new-title>" --body "<new-body>"`).
8. Notify the user that the issue has been updated and provide a summary of the changes made to the structure.
