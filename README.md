# Setjson
Setting for livejson


#### Excample for python
#####    $ import requests, livejson 
#####    $ pip install livejson && pip install requests 
#### def json get
######
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


