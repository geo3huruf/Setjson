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
## Example usage
Basic usage:
```python
import livejson
f = livejson.File("test.json")
f["a"] = "b"
# That's it, the file has been written to!
```
As a context manager:
```python
import livejson
with livejson.File("test.json") as f:
    f["a"] = "b"
```

# Setjson
Setting for livejson


#### Excample for python
#####    $ import requests, livejson 
#####    $ pip install livejson && pip install requests 
#### def json get
```python
    Headers = {}
    _session = request.Session()
    def getJson(self, url, allowHeader=False):
        if allowHeader is False:
            return json.loads(self._session.get(url).text)
        else:
            return json.loads(self._session.get(url, headers=Headers).text)

    settings = livejson.File('setting.json', True, False, 4)
    if not settings:
        print ('LOAD DEFAULT JSON')
        try:
            default_settings = line.getJson('https://raw.githubusercontent.com/geo3huruf/Setjson/main/setting.json')
            """if suda there is a part in server.py
               use == [ line.server.getJson('https://raw.githubusercontent.com/geo3huruf/Setjson/main/setting.json') ]
            """
            settings.update(default_settings)
            print ('LOAD DEFAULT JSON (Success) ')
        except Exception:
            traceback.print_exc()
            print ('LOAD DEFAULT JSON (Failed) ')


