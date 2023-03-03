Install on Ubuntu
```
apt install python3
apt install python-is-python3
```

Create virtual env
```
python -m venv venv/
source venv/bin/activate
deactivate
pip freeze > requirements.txt
```

Manage dependencies with [[Poetry]]
[benchmarks](https://lincolnloop.github.io/python-package-manager-shootout/)
[blogpost](https://aseifert.com/p/python-environments/)

Run simple webserver
```
python3 -m http.server
```

Find source file for specific object
```
import inspect
inspect.getsource(Object)
```

Load dict as variables to runtime
```
locals().update(_dict)
```

