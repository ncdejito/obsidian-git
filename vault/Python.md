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

python_routines.py
```
docker run -it -v `pwd`:`pwd` -w `pwd` -p 8888:8888 jupyter/datascience-notebook:latest

nbqa black 02_Prep_data.ipynb --nbqa-mutate

# create virtual environment
python3 -m venv delibot-sandbox/
source delibot-sandbox/bin/activate

# pandas_routines.py

pd.set_option('use_inf_as_na', True)

# set pandas to not display numbers in scientific notation
pd.set_option('display.float_format', lambda x: '%.6f' % x)

# display df rows completely
pd.set_option('display.max_rows', 500)
pd.set_option('display.max_columns', 500)
pd.set_option('display.width', 1000)
# pd.reset_option('^display')

# plot histogram
(results2['ppd']).hist(bins = 50, grid = False) # in milions

# plot hbar
df = results2[['district', 'ppd']].groupby('district').agg(['median','count'])
df.columns = df.columns.droplevel(0) # delete top multiindex column level
df['w'] = df['median'] * df['count']
df.sort_values('w', ascending = True)['w'].plot.barh(figsize = (5,10), fontsize = 15)

# reload module while interactive
import importlib
import sys
importlib.reload(sys.modules['functions'])
from functions import *

# impute
# https://stackoverflow.com/questions/19966018/pandas-filling-missing-values-by-mean-in-each-group
impute_cols = [
    'vegetation',
    'aridity',
    'temperature',
]

for col in impute_cols:
    df[col] = df.groupby("adm1_name")[col].transform(lambda x: x.fillna(x.median()))

# rownum in pandas
df['C'] = df.groupby(['A','B']).cumcount()+1


# python_routines.py
# reload a module
from importlib import reload
reload(modelutils)
reload(sys.modules['data_prep']) # if importing functions from data_prep.py

# ignore warnings
import logging
import warnings
logging.getLogger().setLevel(logging.ERROR)
warnings.filterwarnings("ignore")

from time import time
start = time()
end = time()
print(end-start)


# writetofile.py
# replace histcounts function to histc for octave
script = """
"""

%cd /content/
!rm {v_dir}hl_predict.m
f = open(v_dir + "hl_predict.m", "w")
f.write(script)
f.close()

# timestamp.py
from datetime import datetime, timedelta
def get_stamp():
  return (datetime.now() + timedelta(hours=8)).strftime("%Y%m%d%H%M")

stamp = get_stamp()
print(stamp)
df.to_csv(PATH/('df_' + stamp + '.csv'))

from datetime import datetime
start = datetime.now()
end = datetime.now()
print(end-start)
```