<h1 align="center">livejson</h1>

<p align="center">
    <a href="https://travis-ci.org/controversial/livejson" align="center">
        <img alt="Build Status" src="https://travis-ci.org/controversial/livejson.svg?branch=master">
    </a>
    <a href="https://coveralls.io/github/controversial/livejson?branch=master" align="center">
        <img alt="Coverage Status" src="https://coveralls.io/repos/github/controversial/livejson/badge.svg?branch=master">
    </a>
    <a href="https://www.python.org/dev/peps/pep-0008/" align="center">
        <img alt="PEP8" src="https://img.shields.io/badge/PEP8-compliant-brightgreen.svg">
    </a>
</p>

![Demo gif](https://media3.giphy.com/media/3o6Zt481isNVuQI1l6/giphy.gif)

`livejson` is:

Thanks to [dgelessus](https://github.com/dgelessus) for naming this project.

# Setjson
Setting for livejson


#### Excample for python
```python
import requests, livejson
```
```bash
pip install livejson && pip install requests
```
#### def json get
```python
import requests
Headers = {}
_session = requests.Session()
def getJson(url, allowHeader=False):
    if allowHeader is False:
        return json.loads(_session.get(url).text)
    else:
        return json.loads(_session.get(url, headers=Headers).text)
```
```python
import livejson
settings = livejson.File('setting.json', True, False, 4)
if not settings:
    print ('LOAD DEFAULT JSON')
    try:
        default_settings = getJson('https://raw.githubusercontent.com/geo3huruf/Setjson/main/setting.json')
        """if suda there is a part in server.py
        use == [ line.server.getJson('https://raw.githubusercontent.com/geo3huruf/Setjson/main/setting.json') ]"""
        settings.update(default_settings)
        print ('LOAD DEFAULT JSON (Success) ')
    except Exception:
        traceback.print_exc()
        print ('LOAD DEFAULT JSON (Failed) ')
```
