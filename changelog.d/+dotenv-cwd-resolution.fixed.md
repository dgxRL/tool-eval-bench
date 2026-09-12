The CLI now resolves the project `.env` from the current working directory. `load_dotenv()`
previously searched upward from the installed package directory, so non-editable installs
(`uv tool install`, pip wheels) never found a project's `.env` and fell through to localhost
auto-discovery even with `TOOL_EVAL_BASE_URL` configured. `--base-url` and exported
environment variables still take precedence.
