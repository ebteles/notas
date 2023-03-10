## Configurações

### Poetry

```

-- Criar projeto e ambiente (.venv)

    poetry new [nome_do_projeto]
    poetry config virtualenvs.in-project true
    poetry shell

-- adicionar pytest
    poetry add --group dev pytest
    poetry add --group dev pytest-cov

-- lint
   poetry add --group dev blue
   poetry add --group dev isort

-- documentação
   poetry add --group doc mkdocs-material
   poetry add --group doc mkdocstrings
```
