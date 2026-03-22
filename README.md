<div align="center">

# py-cli-tools

A personal developer CLI toolkit built in Python that lets you manage notes, tasks, files, and timers, check live weather and GitHub stats, and evaluate math expressions — all from your terminal.

[![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](./LICENSE)
[![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=flat-square)]()

[Installation](#installation) · [Commands](#commands) · [Configuration](#configuration) · [Contributing](#contributing)

</div>

---

## Overview

`py-cli-tools` is a modular command-line toolkit you run from your terminal. Each tool is independent, lightweight, and designed for everyday developer use. No GUI, no bloat — just fast commands that get things done.

---

## Installation

### Prerequisites

- Python 3.11 or higher
- pip

### Setup

```bash
git clone https://github.com/achille010/py-cli-tools.git
cd py-cli-tools
pip install -r requirements.txt
pip install -e .
```

Once installed, the `pytool` command is available globally from any directory:

```bash
pytool --help
pytool --version
```

---

## Commands

### Notes

Manage quick notes saved locally as JSON.

```bash
pytool notes add "Fix the auth bug"     # Save a new note
pytool notes list                        # List all notes
pytool notes delete 2                    # Delete note by ID
```

### Tasks

A todo list with done/pending status tracking.

```bash
pytool task add "Review open PRs"       # Add a task
pytool task list                         # List pending tasks
pytool task list --all                   # List all tasks including completed
pytool task done 1                       # Mark task as done
pytool task clear                        # Remove all completed tasks
```

### Files

File inspection and bulk operations.

```bash
pytool files list                        # List files in current directory
pytool files list --path ./src           # List files in a specific path
pytool files count main.py               # Count lines in a file
pytool files find main.py "import"       # Search for keyword in a file
```

### Calculator

Safely evaluate math expressions without opening a browser.

```bash
pytool calc "sqrt(144) + 2**8"
pytool calc "round(pi, 4)"
pytool calc "log10(1000)"
```

Supported functions: `sqrt`, `floor`, `ceil`, `abs`, `round`, `pow`, `log`, `log10`, `sin`, `cos`, `tan`, `pi`, `e`

### Weather

Live weather for any city. No API key required.

```bash
pytool weather Kigali
pytool weather "New York"
pytool weather                           # Uses default_city from config
```

### GitHub Stats

Fetch public GitHub profile data straight from the terminal.

```bash
pytool github stats achille010          # Profile overview
pytool github repos achille010           # Top repos by stars
pytool github stats                      # Uses github_user from config
```

### Pomodoro Timer

A countdown timer with optional label and auto-break.

```bash
pytool pomodoro 25                       # 25-minute work session
pytool pomodoro 5 --label "Break"        # 5-minute labeled session
```

### Config

Set persistent defaults used across all tools.

```bash
pytool config set default_city Kigali
pytool config set github_user achille010
pytool config get default_city
pytool config list
```

---

## Configuration

Config values are stored in `~/.pytool_config.json`. Set them once and tools will use them automatically.

| Key | Used by | Example |
|---|---|---|
| `default_city` | `weather` | `Kigali` |
| `github_user` | `github` | `achille010` |

---

## Project Structure

```
py-cli-tools/
├── main.py               # CLI entry point and argparse router
├── setup.py              # Package config for pip install
├── requirements.txt      # Dependencies
├── tools/
│   ├── __init__.py
│   ├── text.py           # Echo, reverse, word count
│   ├── notes.py          # Note management
│   ├── tasks.py          # Task manager
│   ├── filetools.py      # File operations
│   ├── calc.py           # Math evaluator
│   ├── weather.py        # Weather lookup
│   ├── github.py         # GitHub stats
│   ├── pomodoro.py       # Countdown timer
│   └── config.py         # Persistent config
├── tests/
│   ├── test_calc.py
│   ├── test_notes.py
│   └── test_tasks.py
└── .github/
    └── workflows/
        └── test.yml
```

---

## Running Tests

```bash
python -m unittest discover tests
```

---

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](./CONTRIBUTING.md) before submitting a pull request.

---

## Code of Conduct

This project follows a Contributor Code of Conduct. See [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md).

---

## License

MIT — see [LICENSE](./LICENSE) for full terms.

---

<div align="center">
Built by <a href="https://github.com/achille010">achille010</a> · Kigali, Rwanda
</div>