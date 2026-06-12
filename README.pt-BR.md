🇺🇸 [Read in English](README.md)

# Devcontainer Templates

Uma coleção de configurações de [Dev Container](https://containers.dev/) prontas para uso em diferentes linguagens e stacks. Basta copiar a pasta `.devcontainer` relevante para qualquer projeto para ter um ambiente de desenvolvimento consistente e isolado, já com lint, formatação, debug e gerenciamento de dependências configurados.

## Por quê

Configurar um bom ambiente de desenvolvimento do zero toda vez é repetitivo: instalar as extensões certas, configurar linters e formatadores, ligar o type checking, lidar com cache, etc. Este repositório mantém essas configurações em um só lugar para reuso e melhoria contínua.

## Estrutura

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

Cada pasta contém um setup `.devcontainer` independente para aquela linguagem/stack.

## Uso

1. Copie a pasta `.devcontainer` da stack desejada para a raiz do seu projeto:

   ```bash
   cp -r devcontainer-templates/python/.devcontainer ./meu-projeto/
   ```

2. Abra o projeto no VS Code.
3. Execute **Dev Containers: Reopen in Container** (Command Palette).
4. O VS Code vai buildar o container, instalar as extensões e rodar o setup automaticamente.

## Templates Disponíveis

### Python

- Imagem base: `mcr.microsoft.com/devcontainers/python:3.12`
- Lint e formatação via [Ruff](https://docs.astral.sh/ruff/) (format on save, auto-fix, organização de imports)
- Type checking via Pylance (modo `basic`)
- Debug via `debugpy`
- Instala automaticamente dependências de `requirements.txt` ou `pyproject.toml` se existirem
- Cache do pip persistido via volume Docker

### Node *(planejado)*

### Go *(planejado)*

### Rust *(planejado)*

## Requisitos

- [Docker](https://docs.docker.com/get-docker/) (ou Docker Engine no Linux/WSL)
- [VS Code](https://code.visualstudio.com/) com a extensão [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Contribuindo

Ao adicionar um novo template:

- Mantenha minimalista e genérico — evite suposições específicas de projeto.
- Documente configurações não óbvias neste README.
- Teste se o container builda corretamente e se o `postCreateCommand` não falha em projetos sem arquivos de dependência.

## Licença

MIT
