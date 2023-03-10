## Configurações

### Poetry

**1. Criar projeto e ambiente (.venv)**

```bash
poetry new [nome_do_projeto]
poetry config virtualenvs.in-project true
poetry shell
```

**2. Adicionar pytest e Lint**

```bash
poetry add --group dev pytest
poetry add --group dev pytest-cov

poetry add --group dev blue
poetry add --group dev isort
```

**3. Documentação**

```bash
poetry add --group doc mkdocs-material
poetry add --group doc mkdocstrings
poetry add --group doc mkdocstrings-python
```

### Configurar MkDocs

**4. Criar documentacao dentro do projeto principal**

```bash
mkdocs new .  # pasta "docs" será criada
```

**5. Configuraçõeos do Mkdocs em "mkdocs..yml"**
