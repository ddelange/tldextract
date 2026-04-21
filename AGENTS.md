# Repository Guidance

See [README.md](README.md) for contributor setup.

## Tests

Before wrapping up a change, run the relevant validation commands from the
README:

```zsh
tox --parallel       # Test all Python versions
tox -e py310         # Test specific Python version
ruff format .        # Format code
```

Prefer the minimum Python version while iterating, `tox -e py310`. Then use
broader validation when the scope of the change warrants it.

Most `tox` environments forward to `pytest`. To focus one environment's tests,
use a `pytest` selector such as `tox -e py310 -- -k private`, or run a specific
test file such as `tox -e py310 -- tests/cli_test.py`.
