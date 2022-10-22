Poetry - [[Python]] dependency manager

Install 
```
curl -sSL https://install.python-poetry.org | python3 -
```

Create new project
```
cd my_app/
poetry init -n
poetry shell
poetry add pandas
```

Install existing project
```
cd project
poetry install
```

Load venv
```
source $(poetry env info --path)/bin/activate
```

Create requirements.txt
```
# https://github.com/python-poetry/poetry/issues/3472#issuecomment-744356551
poetry export -f requirements.txt --output requirements.txt --without-hashes
```

Use jupyter lab with Poetry
```
poetry add ipykernel
poetry run python -m ipykernel install --user --name poetry_kernel
jupyter lab --notebook-dir=.
```