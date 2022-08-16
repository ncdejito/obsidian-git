Install on Ubuntu
```
apt install python3
apt install python-is-python3
```

Run simple webserver
```
python3 -m http.server
```

Create virtual env
```
python -m venv venv/
source venv/bin/activate
deactivate
```

Manage dependencies with poetry
```
cd my_app/
poetry init
poetry shell
poetry add pandas
poetry install
poetry export -f requirements.txt --output requirements.txt

```

Find source file for specific object
```
import inspect
inspect.getsource(Object)
```