# Introduction #

  * https://developers.google.com/appengine/docs/appcfg

# example #

  * appcfg.py --email=emailaddress@gmail.com --noisy request\_logs src/ mylogs.txt
    * you need to be a directory above the app.yaml
    * ensure that the email has access to the application
    * ensure that the version AND the app-id stored in app.yaml do exist on the server!

  * appcfg.py vacuum\_indexes src
    * you need to be a directory above the app.yaml