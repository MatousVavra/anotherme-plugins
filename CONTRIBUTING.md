# AnotherMe Community Plugins

This repository is the curated index for AnotherMe community plugins.
Adding or updating a plugin happens via pull request — the PR is the review gate.

## Submitting a plugin

1. Create a plugin repository. The repo root must contain `plugin.yaml` and
   your `plugin/` package.
2. Tag a release (e.g. `v1.0.0`). The GitHub zipball is what users install.
3. Open a PR adding an entry to `plugins.json`:

   ```json
   {
     "name": "your_plugin",
     "repo": "yourname/your-plugin",
     "tag": "v1.0.0",
     "description": "One sentence on what it does",
     "author": "Your Name"
   }
   ```

`name` must match the `name` in your `plugin.yaml`, which must be lowercase
snake_case (letters, digits, underscores — no hyphens). Repository names MAY
contain hyphens; only the plugin `name` is restricted.

## Review checklist

Reviewers verify, before merging:

- [ ] `manifest.name` matches the index entry `name`
- [ ] Plugin uses only the Python stdlib and app dependencies (no pip installs)
- [ ] No network calls except through `ctx.llm_client` or documented endpoints
- [ ] No reading/writing outside the plugin's own tables and vault paths
- [ ] Capabilities declared in `plugin.yaml` match what the code uses
- [ ] No `exec`, `eval`, `subprocess`, or dynamic imports of remote code
- [ ] Archive is under 50 MB

## Updating a plugin

Bump the `tag` in a PR. Users only ever install tags listed here — pinning
is the point of curation.
