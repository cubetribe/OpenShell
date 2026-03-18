# Policy Workspace

Store custom sandbox policy files here once runtime validation starts.

Suggested conventions:

- keep one policy file per named sandbox intent
- separate exploratory policies from stable baseline policies
- annotate each policy with the agent, endpoints, and file paths it is expected to allow
- record why a policy exists, not only what it allows

Do not add speculative policy YAML yet. The official docs and current issue traffic suggest the first runtime validation should happen before policy files are frozen.
