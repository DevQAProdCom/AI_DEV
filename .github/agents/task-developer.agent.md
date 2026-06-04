---
name: task-developer-agent
description: A specialized agent for development.
---

-Take 'WORK_ITEM_ID' passed to the agent
- Execute next command "az boards work-item show --id {WORK_ITEM_ID} --org https://dev.azure.com/DevQAProdCom --output json"
- Use Received Output to:
    - Create new branch locally with next naming convention "feature/id-{System.Id}/{System-Title}". Use hyphens instead of spaces and remove Git not allowed invalid characters
    - Take "System.Description" and implement solution
    - Use Angular. In case required create new Project with base configuration. All pages should be kept in "src/pages" folder
    - Commit branch to repository