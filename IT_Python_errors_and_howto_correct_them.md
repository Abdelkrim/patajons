# Introduction #

| Description |solution |
|:------------|:--------|
| Error: Unable to serialize database: 'ascii' codec can't encode character u'\xe9' in position 2: ordinal not in range(128) | no solution yet! see issues |
| UnacceptableVersionError: django 1.2 was requested, but 0.96.4.None is already in use | `you need to define  *use_library('django', '1.2')* before *from google.appengine.ext.webapp import template*` |

# WARNING:root:Could not import settings 'paranyo.settings' (Is it on sys.path? Does it have syntax errors?): No module named settings #
```
pydev debugger: warning: psyco not available for speedups (the debugger will still work correctly, but a bit slower)
pydev debugger: starting
WARNING:root:Could not import settings 'paranyo.settings' (Is it on sys.path? Does it have syntax errors?): No module named settings
INFO:root:Loading __main__, app version = None
Traceback (most recent call last):
  File "/Users/<username>/dev/eclipse/plugins/org.python.pydev.debug_2.2.4.2011121401/pysrc/pydevd.py", line 1307, in <module>
    debugger.run(setup['file'], None, None)
  File "/Users/<username>/dev/eclipse/plugins/org.python.pydev.debug_2.2.4.2011121401/pysrc/pydevd.py", line 1060, in run
    pydev_imports.execfile(file, globals, locals) #execute the script
  File "/Users/<username>/git/patajons.paranyo/paranyo/src/main.py", line 42, in <module>
    main()
  File "/Users/<username>/git/patajons.paranyo/paranyo/src/main.py", line 39, in main
    run_wsgi_app(application)
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/ext/webapp/util.py", line 98, in run_wsgi_app
    run_bare_wsgi_app(add_wsgi_middleware(application))
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/ext/webapp/util.py", line 118, in run_bare_wsgi_app
    for data in result:
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/ext/appstats/recording.py", line 903, in appstats_wsgi_wrapper
    start_recording(environ)
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/ext/appstats/recording.py", line 1035, in start_recording
    time=config.LOCK_TIMEOUT, namespace=config.KEY_NAMESPACE):
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/api/memcache/__init__.py", line 788, in add
    namespace=namespace)
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/api/memcache/__init__.py", line 872, in _set_with_policy
    time, '', namespace)
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/api/memcache/__init__.py", line 974, in _set_multi_async_with_policy
    (server_keys, user_key))
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/api/memcache/__init__.py", line 383, in _make_async_call
    rpc = create_rpc()
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/api/memcache/__init__.py", line 294, in create_rpc
    return apiproxy_stub_map.UserRPC('memcache', deadline, callback)
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/api/apiproxy_stub_map.py", line 393, in __init__
    self.__rpc = CreateRPC(service, stubmap)
  File "/Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/google/appengine/api/apiproxy_stub_map.py", line 67, in CreateRPC
    assert stub, 'No api proxy found for service "%s"' % service
AssertionError: No api proxy found for service "memcache"
```

## how to correct? ##