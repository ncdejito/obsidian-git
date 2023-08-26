Test with [[Use Pytest]]

## Setup
Install on Ubuntu
```
apt install python3
apt install python-is-python3
apt install python3.8-venv
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

```
import json
with open("sample.json", "w") as outfile:
    json.dump(dictionary, outfile)
with open("data_file.json", "r") as read_content:
    print(json.load(read_content))
```
## Next-gen
Codon - compiled python  
[https://techxplore-com.cdn.ampproject.org/c/s/techxplore.com/news/2023-03-python-based-orders-of-magnitude-speedups.amp](https://techxplore-com.cdn.ampproject.org/c/s/techxplore.com/news/2023-03-python-based-orders-of-magnitude-speedups.amp)

Python syntax but C-speed
https://www.modular.com/

[[Use Python for Data Analysis]]

Python robots
https://www.linkedin.com/posts/dannystaple_yay-i-see-my-article-featured-in-geeky-activity-7082378674947125249-lMcV