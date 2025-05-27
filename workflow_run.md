This workflow is triggered when an activity type occurs for a different workflow. `completed`, `requested`, or `in_progress`. This action will only run if the workflow is already defined in the `default` branch. 

Even if the branch does not directly run on the main branch but runs on another. It has to first exist on the default branch. This means in order to test the workflow. You have to make a PR to the default branch with the workflow already created.
#### References
- [[Github Actions]]