

# Introduction #

Install step by step the development tools as well as third parties to develop and debug Google App Engine web applications

URL : http://code.google.com/intl/en/appengine/downloads.html

# Windows PC #

Install the tools in order :

| python 2.5.4 | url : http://www.python.org/download/releases/2.5.4/ | installé dans c:\python25 |
|:-------------|:-----------------------------------------------------|:---------------------------|
| Google app engine sdk python 1.6.2 | http://code.google.com/intl/fr/appengine/downloads.html#Google_App_Engine_SDK_for_Python | installé avec les options par defaut. configuration du path nécessaire ,  python path = c:\python25\python.exe |
| jre 6 update 31 version 32-bit |  http://www.java.com/fr/download/manual.jsp          | None                       |
| 7-zip        | http://www.7-zip.org/                                | None                       |
| eclipse classic 3.7.1 Indigo version 32-bit | http://www.eclipse.org/downloads/packages/eclipse-classic-371/indigosr1 | options par defaut. We use the 32 bits version in order to increase the compatibility  |
| pydev pour eclipse | http://pydev.org/updates                             | **idem que plus haut** TBR. puis aller dans "windows"->"preferences"->"python" cliquer sur "auto config" |
| Eclipse plugin for google app engine | http://code.google.com/intl/fr/eclipse/docs/download.html | None                       |
| django 1.3.1 | https://www.djangoproject.com/download/              | (A) download the archive and open it with 7zFM.exe (B) extract the files unders "django" (C) Run the shell (D) 'cd django' (E) setup.py install |
| PIL imaging library for python | http://www.pythonware.com/products/pil/              | default options. install v1.1.7 |

# MAC OS X #

## pydev on Eclipse ##
http://www.joelennon.ie/2011/03/25/using-pydev-for-google-app-engine-development-on-a-mac/

| python 2.5.4 | http://www.python.org/download/releases/2.5.4/ | None |
|:-------------|:-----------------------------------------------|:-----|
| Google App Engine SDK python v1.6.2 | http://code.google.com/p/googleappengine/downloads/list | download v1.6.2 |
| eclipse classic 3.7.1 Indigo version 32-bit | http://code.google.com/intl/en/appengine/downloads.html#Google_App_Engine_SDK_for_Python | (A) install indigo (B) run Indigo (C) perform the tasks : http://code.google.com/intl/en/eclipse/docs/install-eclipse-3.7.html (D) Install the "Google Plugin for Eclipse 3.7" |
| Aptana       | Window > Install software > Add http://download.aptana.com/studio3/plugin/install | (A) Install "Aptana studio 3" (B) follow steps: http://www.joelennon.ie/2011/03/25/using-pydev-for-google-app-engine-development-on-a-mac/ |
| PIL imaging library for python | http://code.google.com/intl/fr/appengine/docs/python/images/installingPIL.html | None |

# MAC OS X & WINDOWS #
## Eclipse environment ##

```
${GOOGLE_APP_ENGINE}
${GOOGLE_APP_ENGINE}/lib/antlr3
${GOOGLE_APP_ENGINE}/lib/django
${GOOGLE_APP_ENGINE}/lib/fancy_urllib
${GOOGLE_APP_ENGINE}/lib/graphy
${GOOGLE_APP_ENGINE}/lib/ipaddr
${GOOGLE_APP_ENGINE}/lib/simplejson
${GOOGLE_APP_ENGINE}/lib/webob
${GOOGLE_APP_ENGINE}/lib/yaml/lib

GOOGLE_APP_ENGINE environment: /Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine

GOOGLE_APP_ENGINE for DJANGO: /Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google_appengine/lib/django_1_2
```


## GIT source control ##
  * url: http://www.eclipse.org/egit/
    * (install egit) - install all the tools:
      1. EGit - Git Team Provider 1.3.0

  * URL: http://www.eclipse.org/egit/documentation/
    1. read the user guide

  * url: http://git-scm.com/download

## GIT correct configuration ##
**pay attention, the configuration of google is wrong**

  * url: http://stackoverflow.com/questions/9344566/authenticating-sourcetree-with-a-google-code-project
  * the file .git/config should contain the following:
  * **instead of:** https://USER@code.google.com/p/PROJECT/
    * **use:** https://code.google.com/p/PROJECT/

```
[core]
	repositoryformatversion = 0
	filemode = true
	logallrefupdates = true
	autocrlf = false
[remote "origin"]
	url = https://code.google.com/p/patajons.paranyo/
	fetch = +refs/heads/*:refs/remotes/origin/*
	
[branch "master"]
    remote = origin
    merge = refs/heads/master
```

## GIT .gitignore ##
  1. add ~/.gitignore file into your %home% directory *** URL: http://help.github.com/ignore-files/
    * URL: http://antoniolorusso.com/2009/03/09/ignore-ds_store-forever-in-git/
  1. Add the following content
```
# Compiled source #
###################
*.com
*.class
*.dll
*.exe
*.o
*.so

# Packages #
############
# it's better to unpack these files and commit the raw source
# git has its own built in compression methods
*.7z
*.dmg
*.gz
*.iso
*.jar
*.rar
*.tar
*.zip

# Logs and databases #
######################
*.log
*.sql
*.sqlite

# OS generated files #
######################
.DS_Store*
ehthumbs.db
Icon?
Thumbs.db


# iOS generated files #
#################
build/

*.pbxuser
*.pbxtree
*.perspective
*.perspectivev3
*.mode1v3
*.mode2v3
```
# MISC #**

http://stackoverflow.com/questions/1847249/how-can-i-correct-corrupted-pythonpath

|djangoappengine - Django App Engine backends (DB, email, etc.) : | http://www.allbuttonspressed.com/projects/djangoappengine|
|:----------------------------------------------------------------|:---------------------------------------------------------|
|SSL issue:                                                       | http://nathanvan.wordpress.com/2011/01/26/fixing-appengine-ssl-error-on-ubuntu-10-04/|

example of good eclipse configuration : http://code.google.com/p/patajons/issues/detail?id=17&thanks=17&ts=1332169156

/!\ you need to replace the workspace\_loc with a proper path to your app directory (src in this case)

/!\² if using the project\_loc variable you must first select the proper project in the project explorer

# Legacy #
## Mercurial ##
| set environment for mercurial - /Library/Python/2.6/site-packages/ | http://www.astro.washington.edu/users/rowen/AquaEnvVar.html |
|:-------------------------------------------------------------------|:------------------------------------------------------------|