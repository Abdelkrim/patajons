## SDK rollback error ##

If the SDK bugs when you try to deploy and ask for a rollback execute

_python interpreter_ appcfg.py rollback _path\_to\_app_

Win32 example(from ydo):

C:\Program Files (x86)\Google\google\_appengine> c:\Python25\python.exe appcfg.py rollback C:\dev\git\patajons.paranyo\paranyo\src

## Google PIL API ##

- resize() can generate only jpeg , png and webp for output , we choose for jpeg with 90 quality compression

- resize() quality parameter only works on google app engine not the SDK see :http://code.google.com/intl/fr/appengine/docs/python/images/imageclass.html#Image_resize

## Index.yaml ##


If you have this error:

NeedIndexError : no matching index not found:
the suggested index fot this query is:
- kind : XXXX
> ....


it means the index.yaml was not up to date during the last deployement , you need to do a query on kind who is needing an index before deploying

more info here : http://groups.google.com/group/google-appengine/browse_thread/thread/d0f9084366926dea

## Google mail API ##

If you get this errror : InvalidSenderError: Unauthorized sender

It means that the senders mail is invalid for GAE , the restrictions of the online doc are outdated(https://developers.google.com/appengine/docs/python/mail/sendingmail)

the releases notes of the SDK(http://code.google.com/p/googleappengine/wiki/SdkReleaseNotes) indicates :

```
Version 1.5.0 - May 10, 2011
...
We have added two restrictions to the Mail API to improve the reliability of the service for all application.

    Emails must be sent from email accounts managed by Google (either Gmail or a domain signed up for Google Apps).
    Reduced the number of free recipients per day from 2000 to 100 for new applications. 
```

So this means that the sender email must be registred as devlopper in the app

for paranyo we use noreplyparanyo@gmail.com for the moment

## text search in db ##

google app engine does not inplement a like clause in the gql so use this instead :
http://googlecode.blogspot.com/2010/05/google-app-engine-basic-text-search.html
enough to look for string starting with a certain word