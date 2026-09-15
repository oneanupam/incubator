# Pre-commit

It is a multi-language package manager for pre-commit hooks. You specify a list of hooks you want and pre-commit manages the installation and execution of any hook written in any language before every commit. pre-commit is specifically designed to not require root access.

## How to run pre-commit

Run these commands from the repository root.

### Install the hooks

Install the Git hooks for the repository:

```bash
pre-commit install
```

If the configuration file has a non-standard name, specify it with `--config`:

```bash
pre-commit install --config <config-file>
```

This installs the hook into `.git/hooks/pre-commit`. Once installed, pre-commit runs automatically when you commit changes. By default, it checks only the files included in the commit.

### Validate the configuration

Validate the repository's pre-commit configuration with:

```bash
pre-commit validate-config
```

### Run the hooks manually

Run all hooks against every file:

```bash
pre-commit run --all-files
```

To use a non-standard configuration file, add the `--config` option:

```bash
pre-commit run --all-files --config <config-file>
```

Run a specific hook with:

```bash
pre-commit run <hook-id>
```

Hook configuration is managed in `.pre-commit-config.yaml`. To generate a starter configuration, run:

```bash
pre-commit sample-config
```

## References
- https://pre-commit.com/
