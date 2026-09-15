# 📘 UV Commands Reference
This repository contains a curated list of essential `uv` commands for managing python project efficiently. Useful for daily reference and quick lookups.

---

## 🧱 Useful Commands

```bash
uv version # Check the installed uv version.
uv init # Initialized the existing python project with required files and dirs.
uv init <project> # Creates a new python project and does initialization.
# Important files
.python-version # Which Python version?
pyproject.toml  # What does my project need?
uv.lock         # Exactly which dependency versions?

uv venv # Create a virtual environment
uv sync # If there is no virtual environment, and you run this command, uv will create one automatically (by default, .venv) and install the project's dependencies into it.

# Packages installation
uv add <package-01> <package-02> # Install a package and it updates pyproject.toml and uv.lock
uv add requests
uv add --dev ruff # --dev flag means, Add this package as a development dependency, not as a package required to run the application.
uv remove requests # Remove a package
uv add -r requirements.txt # The -r means read requirements from this file.

# Run python script
uv run # Automatically runs the command inside the project's virtual environment.
# Examples
uv run python main.py
uv run main.py
python main.py
uv run ruff check .
uv run ruff format .
```

## 📌 How to Contribute
Feel free to fork this repo and add your favorite uv commands!

## References
- https://docs.astral.sh/uv/
- https://docs.astral.sh/uv/reference/cli/
