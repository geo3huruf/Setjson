# Setjson
Setting for livejson


## Excample for python
### def json get
###
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
            default_settings = line.getJson('https://raw.githubusercontent.com/crash-override404/selfbot-py/master/settingsv2.json')
            """
              jika suda ada bagian di server.py
              gunakan == [ line.server.getJson('') ]
            """
            settings.update(default_settings)
            print ('LOAD DEFAULT JSON (Success) ')
        except Exception:
            traceback.print_exc()
            print ('LOAD DEFAULT JSON (Failed) ')


