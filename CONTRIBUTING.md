# Contributing to py-cli-tools

Thank you for taking the time to contribute. This document explains how to get involved, what's expected, and how to submit your work cleanly.

---

## Getting Started

### 1. Fork and clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/py-cli-tools.git
cd py-cli-tools
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
pip install -e .
```

### 3. Create a branch

Branch names should follow this pattern:

```bash
git checkout -b feat/your-feature-name
git checkout -b fix/issue-you-are-fixing
git checkout -b docs/what-you-are-documenting
```

---

## Making Changes

### Code style

- Follow standard Python conventions (PEP 8)
- Every function must have a docstring
- Keep functions small and focused — one function, one job
- Use descriptive variable names — no `x`, `tmp`, `data` unless the context makes it obvious

### Adding a new tool

1. Create a new file in `tools/` — e.g. `tools/mytool.py`
2. Write your functions with docstrings
3. Register the subcommand in `main.py`
4. Add tests in `tests/test_mytool.py`
5. Document usage in `README.md`

### Commit messages

Follow the conventional commits format:

```
feat: add currency converter tool
fix: handle empty input in notes add
docs: update README with pomodoro usage
refactor: extract shared JSON helpers
test: add unit tests for task manager
chore: update requirements.txt
```

---

## Testing

Run the full test suite before submitting:

```bash
python -m unittest discover tests
```

All existing tests must pass. New features must include tests.

---

## Submitting a Pull Request

1. Push your branch to your fork
2. Open a PR against the `main` branch of this repo
3. Fill in the PR description — what does it do, why is it needed
4. Wait for review

Keep PRs focused. One feature or fix per PR. Large PRs are harder to review and slower to merge.

---

## Reporting Issues

Use [GitHub Issues](https://github.com/achille010/py-cli-tools/issues) to report bugs or suggest features. Include:

- What you expected to happen
- What actually happened
- Steps to reproduce
- Your Python version (`python --version`)

---

## Questions

Open a discussion on GitHub or reach out via the contact links on [achille010's profile](https://github.com/achille010).