Test with [[Use Pytest]]

## Setup
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

Python tips
https://www.linkedin.com/feed/update/urn:li:activity:7026499417461469185?utm_source=share&utm_medium=member_android

## Next-gen
Codon - compiled python  
[https://techxplore-com.cdn.ampproject.org/c/s/techxplore.com/news/2023-03-python-based-orders-of-magnitude-speedups.amp](https://techxplore-com.cdn.ampproject.org/c/s/techxplore.com/news/2023-03-python-based-orders-of-magnitude-speedups.amp)

Python syntax but C-speed
https://www.modular.com/

[[Use Python for Data Analysis]]