# Prepare MU Plugins

This action will place the contents of a repo that should contain MU Plugins for an installation, in an `mu-plugins/` folder. 
By default [this repo](https://github.com/saucal/saucal-mu-plugins-built) is used as source.

The action will deploy MU Plugins only if a `client-mu-plugins` directory does exist, and if a `vip-config` directory does not exist.
This behavior can be overriden using the `add-mu-plugins` argument.

## Getting Started

You should be all set with these defaults.

```yml
- name: Prepare MU Plugins
    uses: saucal/action-prepare-mu-plugins@main
    with:
        path: "source"
        git-token: ${{ secrets.CI_BOT_TOKEN }}

```
## Full options

```yml
- name: Prepare MU Plugins
    uses: saucal/action-prepare-mu-plugins@main
    with:
        # Relative path to where the source code is
        # Typically where package.json and composer.json are located
        path: ""

        # Token to use throughout the process
        git-token: ""

        # The MU Plugins repo.
        mu-repo: "saucal/saucal-mu-plugins-built"

        # The branch of the MU Plugins repo that should be used
        mu-branch: "main"

        # Whether or not to override the auto-detection of a suitable repo.
        # Possible values: "auto"|"true"|"false"
        add-mu-plugins: "auto"

        # The relative path to use for MU Plugins. By default set to "mu-plugins"
        mu-plugins-path: "mu-plugins"
```
