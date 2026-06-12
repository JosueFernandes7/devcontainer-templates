🇧🇷 [Leia em Português](README.pt-BR.md)

# Devcontainer Templates

A collection of ready-to-use [Dev Container](https://containers.dev/) configurations for different languages and stacks. Drop the relevant `.devcontainer` folder into any project to get a consistent, isolated development environment with linting, formatting, debugging, and dependency management already set up.

## Why

Setting up a good dev environment from scratch every time is repetitive: installing the right extensions, configuring linters and formatters, wiring up type checking, handling caching, etc. This repo keeps those setups in one place so they can be reused and improved over time.

## Structure

```
devcontainer-templates/
├── python/
│   └── .devcontainer/
│       └── devcontainer.json
├── node/
│   └── .devcontainer/
│       └── devcontainer.json
├── go/
│   └── .devcontainer/
│       └── devcontainer.json
└── ...
```

Each folder contains a self-contained `.devcontainer` setup for that language/stack.

## Usage

1. Copy the `.devcontainer` folder from the stack you need into your project root:

   ```bash
   cp -r devcontainer-templates/python/.devcontainer ./my-project/
   ```

2. Open the project in VS Code.
3. Run **Dev Containers: Reopen in Container** (Command Palette).
4. VS Code will build the container, install extensions, and run the setup command automatically.

## Available Templates

### Python

- Base image: `mcr.microsoft.com/devcontainers/python:3.12`
- Linting & formatting via [Ruff](https://docs.astral.sh/ruff/) (format on save, auto-fix, import sorting)
- Type checking via Pylance (`basic` mode)
- Debugging via `debugpy`
- Auto-installs `requirements.txt` or `pyproject.toml` dependencies if present
- Pip cache persisted via Docker volume

### Node *(planned)*

### Go *(planned)*

### Rust *(planned)*

## Requirements

- [Docker](https://docs.docker.com/get-docker/) (or Docker Engine on Linux/WSL)
- [VS Code](https://code.visualstudio.com/) with the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Contributing

When adding a new template:

- Keep it minimal and generic — avoid project-specific assumptions.
- Document any non-obvious settings in this README.
- Test that the container builds cleanly and the `postCreateCommand` doesn't fail on a project with no dependency files.

## License

MIT
