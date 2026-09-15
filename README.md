# Incubator
Nurturing Cloud and DevOps skills from the ground up.

## Prerequisites
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
From the repository root, install the pre-commit Git hooks:

```bash
pre-commit install
```

Once installed, pre-commit runs automatically when you commit changes. By default, it checks only the files included in the commit.

To run all hooks manually, use:

```bash
# Run all hooks against every file
pre-commit run --all-files

# Run a specific hook
pre-commit run <hook-id>
```

Hook configuration is managed in [`.pre-commit-config.yaml`](.pre-commit-config.yaml). To generate a starter configuration, run `pre-commit sample-config`.

## Contributing

Contributions are welcome! Please open issues or submit pull requests for improvements or new suggestions. Read the [contributing.md](CONTRIBUTING.md) before starting.

## License

This project is licensed under the [MIT License](LICENSE).
