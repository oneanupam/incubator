# App Repo Template

A ready-to-use template repository for quickly bootstrapping new projects.

## Prerequisites

- [pre-commit](https://pre-commit.com/) >= 4.2.0
- [kubectl](https://kubernetes.io/docs/tasks/tools/) >= v1.30.5
- [helm](https://helm.sh/) >= 3.13.1

> [!NOTE]
> See [Installation Guide](https://kubernetes.io/docs/tasks/tools/) on how to install Kubernetes Tools.

## Repo Layout
At a high level, these folders make up the `github.com/oneanupam/app-repo-template` repository.

- [`.github/`](./.github) - This folder contains the codeowners, pull request template and github action yaml files.
- [`.vscode/`](./.vscode) - It contains project-specific settings and configurations to customize how VS Code behaves for the workspace.
- [`build/`](./build) - This folder contains the build config files to build/deploy the application code.
- [`docs/`](./docs) - This folder contains the documentations related to the repository.
- [`examples/`](./examples) - This folder contains the examples to use the module or code.
- [`helm-charts/`](./helm-charts) - This folder contains the helm chart to deploy the kubernetes manifests.
- [`helm-overrides/`](./helm-overrides) - This folder contains the override files to pass to variables declared in helm charts.
- [`src/`](./src) - This folder contains the application code or scripts.
- [`.pre-commit-config.yaml`](.pre-commit-config.yaml) - This file contains the plugin configuration for pre-commit.
- [`.editorconfig`](.editorconfig) - This file has the configuration for the editorconfig plugin.

## How to run pre-commit
Run the below commnad from the git repo root to set up the git hook scripts into your git hooks. It will be installed at .git/hooks/pre-commit

```bash
pre-commit install
```

now pre-commit will run automatically on git commit. Usually, it runs only for the changed files. Its good to run the hooks against all the files when adding new hooks. To manually run all pre-commit hooks on a repo, use below -

```bash
# to run hooks on all files
pre-commit run --all-files

# to run individual hook
pre-commit run <hook_id>
```

Once you have pre-commit installed, adding pre-commit plugins to your project is done with the .pre-commit-config.yaml configuration file. You can generate a very basic configuration using `pre-commit sample-config`. Every time you clone a project using pre-commit running pre-commit install should always be the first thing you do.

## Contributing

Contributions are welcome! Please open issues or submit pull requests for improvements or new suggestions. Read the [contributing.md](CONTRIBUTING.md) before starting.

## License

This project is licensed under the [MIT License](LICENSE).
