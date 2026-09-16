# Incubator

A space to learn, practice, and explore the concepts, tools, and workflows that shape modern Cloud and DevOps.

## Prerequisites
Install the required tools before contributing to this project:

- [pre-commit](https://pre-commit.com/) >= 4.2.0

## Repo Layout
At a high level, these folders make up the `github.com/oneanupam/incubator` repository.

- [`.github/`](./.github) - This folder contains the codeowners, pull request template and github action yaml files.
- [`.vscode/`](./.vscode) - It contains project-specific settings and configurations to customize how VS Code behaves for the workspace.
- [`build/`](./build) - This folder contains the build config files to build/deploy the application code.
- [`docs/`](./docs) - This folder contains the documentations related to the repository.
- [`src/`](./src) - This folder contains the application code or scripts.
- [`.pre-commit-config.yaml`](.pre-commit-config.yaml) - This file contains the plugin configuration for pre-commit.
- [`.editorconfig`](.editorconfig) - This file has the configuration for the editorconfig plugin.

## Run pre-commit
This repository already includes a `.pre-commit-config.yaml`. Run the following commands to install the hooks locally:

```bash
python -m pip install pre-commit
pre-commit install
pre-commit validate-config
```

This installs the hook into `.git/hooks/pre-commit`. Once installed, pre-commit runs automatically when you commit changes. By default, it checks only the files included in the commit.

To run all hooks manually, use:

```bash
pre-commit run --all-files
pre-commit run <hook_id>
```

## Contributing

Contributions and suggestions are welcome. Before opening an issue or pull request:

1. Review the [contribution guidelines](CONTRIBUTING.md).
2. Install the pre-commit hooks and run them against your changes.
3. Open an issue for bugs or ideas, or submit a pull request with a clear description of the change.

## License

This project is licensed under the [MIT License](LICENSE).
