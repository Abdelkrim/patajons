# Introduction #

## Common ##

| **description** | **command** | **phase** |
|:----------------|:------------|:----------|
| start up a shell | python manage.py shell | common    |
| tbd             | python manage.py update | Common    |
| tbd             | python manage.py rollback | Common    |
| tbd             | python manage.py vacuum\_indexes | Common    |
| starts a Python shell in the context of the Django project—and the development server | python manage.py shell | Common    |
| Python shell that connects to the live application via remote\_api | python manage.py console | Common    |
| Erase the development server datastore (idem reset)  | python manage.py flush | Common    |

## Implementation ##
| **description** | **command** | **phase** |
|:----------------|:------------|:----------|
| create a Django application | python manage.py startapp -=name of the project=- e.g. Patajons | Implementation |

## Testing ##
| **description** | **command** | **phase** |
|:----------------|:------------|:----------|
| Run the App Server | python manage.py runserver | Deployment - Test |
| Load fixtures into the project’s development datastore manually  | python manage.py loaddata bookstore/fixtures/PersonLogin.json | Testing   |
| Run the new test using the test command | python manage.py test -=Directory name =- e.g. PersonLogin | Testing   |
| Clear the datastore |  python manage.py reset | Testing   |
| run the dumpdata command, and redirect its output to a file | python manage.py dumpdata PersonLogin > PersonLogin/fixtures/personlogin.json  | Testing   |


## Indexes ##
| **description** | **command** | **phase** |
|:----------------|:------------|:----------|
| If you are uploading the new application using the version identifier that is currently the “default” version |  (1) upload the index configuration alone using the appcfg.py update\_indexes command (2) When the indexes are built, upload the app | Deployment |
| If you are uploading the application as a new version, or as a version that isn’t the default and that nobody is actively using, you can safely upload the application and index configuration together | (1) appcfg.py update (2) Wait until the indexes are built before making the new version the default | Deployment |
| to purge unused indexes | appcfg.py vacuum\_indexes app-dir | Deployment |

# Do not use those commands! #
| **description** | **command** | **phase** |
|:----------------|:------------|:----------|
| Unlike with Django data models, you do not need to run python manage.py syncdb or related commands when changing App Engine models. The datastore is schemaless, so there are no table definitions to update. | python manage.py syncdb | Never use this! |