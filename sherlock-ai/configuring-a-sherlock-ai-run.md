# Configuring a Sherlock AI Run

Runs can be configured in two ways: a quick per-run setup in the UI, and a shared default via a repo config file.

***

### UI flow

1. Click **Create Codebase Run** at the top of the dashboard.
2. Select the **repository**, then its **branch**, then the exact **commit**.
3. The **Advanced options** toggle appears. Open it to:
   * Choose **Files to analyze** (whitelist specific files or folders from that commit).
   * Add **Additional context files** (docs/configs that help the model).
   * Provide an **Additional context prompt** such as key areas to focus on, vulnerabilities to skip, or relevant information about the codebase.

Changes made here apply only to that run.

***

### Repo defaults with `.sherlock-ai.json`

Place a `.sherlock-ai.json` at the repo root (on the branch/commit being run). When the commit is selected in the UI, these defaults prefill the advanced options:

Example:

```json
{
  "whitelist_files": ["contracts/core/Vault.sol", "contracts/periphery/Router.sol"],
  "context_files": ["docs/security-model.md", "specs/withdrawals.md"],
  "extra_prompt": "Prioritize withdrawal logic and pause/unpause controls."
}
```

Fields:

* `whitelist_files` (string\[]): if empty, the whole repo is eligible. Only paths to files are supported. Paths should be relative to the repo root. Only `.sol` files are supported.
* `context_files` (string\[]): documentation to load and help the model. Only paths to files are supported. Paths should be relative to the repo root. The following file extensions are supported: `.md`, `.txt`, `.json`, `.yml`, `.yaml`
* `extra_prompt` (string): concise guidance. Useful for specifying key areas to focus on, vulnerabilities to skip, and relevant information about the codebase.

Configurations done through the UI will override what's defined in `.sherlock-ai.json`   &#x20;
