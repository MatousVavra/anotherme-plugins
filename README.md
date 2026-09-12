# anotherme-plugins

Community plugin index for [AnotherMe](https://github.com/MatousVavra/AnotherMe).

`plugins.json` is a JSON array; each entry:

    {"name": "<plugin-name>", "repo": "<owner>/<repo>", "tag": "vX.Y.Z",
     "description": "...", "author": "..."}

The app fetches the raw file from this branch's `main`. Entries here are the
reviewed install path (`install_from_index`); unreviewed plugins can be
installed by GitHub URL from the store UI.

To add a plugin: fork this repo, add your entry, open a PR.
