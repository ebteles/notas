## Configurações

### Poetry

**1. Criar projeto e ambiente (.venv)**

```bash
poetry new [nome_do_projeto]
poetry config virtualenvs.in-project true
poetry shell

## outros comandos
poetry list
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

```yml
site_name: Notas
repo_url: https://github.com/ebteles/notas
repo_name: ebteles/notas
edit_uri: tree/master/docs

theme:
  name: material
  language: pt-BR
  logo: assets/notas_001.png
  favicon: assets/notas_001.png

markdown_extensions:
  - attr_list

extra_css:
  - stylesheets/extra.css

plugins:
  - mkdocstrings:
      handlers:
        python:
          paths: [notas]
```

**6. Configuraçõeos do PyTest**

Configurações realizadas diretamente dentro do **pyproject.toml**.

```bash
[tool.pytest.ini_options]
pythonpath = "."
addopts = "--doctest-modules"
```

**7. Taskpy**

Simplicar linhas de comando no terminal.
Configurações realizadas diretamente dentro do **pyproject.toml**.

```bash
# instalação:
poetry add --group dev taskipy

# execução
task [nome_da_task]
exemplo: task test

# configuração
[tool.taskipy.tasks]
docs = "mkdocs serve"
test = "pytest -s -x --cov=notas -vv"
post_test = "coverage html
```
