

# Yannis #
## February ##
### 27/02/2012 ###
#### Facebook: how the like button works? - UC: how could a user like an object? ####

  * http://thinkdiff.net/facebook/update-facebook-page-status-automatically/
  * http://www.testically.org/2011/09/27/5-steps-to-automatically-write-on-your-facebook-page-wall-using-the-graph-api-without-a-logged-in-user/
  * http://developers.facebook.com/docs/reference/api/permissions/
  * http://developers.facebook.com/docs/authentication/#app-login
  * https://developers.facebook.com/tools/explorer?method=GET&path=100003484107135
  * http://stackoverflow.com/questions/6156052/how-to-write-a-post-to-my-facebook-apps-wall-from-app-engine-using-python
  * http://www.guillaumevoisin.fr/facebook/tips-facebook-comment-recuperer-un-access_token-pour-acceder-a-la-graph-api
  * http://facebook.typepad.com/faceblog/2009/04/tutoriel-developper-une-application-facebook-en-10-etapes.html
  * http://blog.theunical.com/facebook-integration/5-steps-to-publish-on-a-facebook-wall-using-php/

> ### 28/02/2012 ###
> voir le fichier Like\_Button

> ### 29/02/2012 ###
    * installation de python, google app engine, etc...
    * lecture de la moitié de la partie Python du site du zéro

## March ##

> ### 01/03/2012 ###
    * suite étude de Python
    * toutes la mises en route de google appengine
    * début étude des détails sur google appengine

> ### 02/03/2012 ###
    * révision mise en route de google appengine
    * cours de git
    * installation et configuration de git et de egit
    * compréhension du code et réflexion pour l'insertion du bouton like

> ### 05/03/2012 ###
    * étude de google appengine et python
    * compréhension du code et commencement du codage du bouton like

> ### 06/03/2012 ###
    * étude "get", "post", etc...
    * codage du bouton like (pas encore fini)

> ### 07/03/2012 ###
    * codage du bouton like en html5 plutôt qu'en iFrame explication dans Like\_Button
    * commencement du codage d'une page par item
    * http://ydo-test-ipl.appspot.com/

> ### 12/03/2012 ###
    * installation de python, google app engine, etc...
    * design  de la page de détails.
    * insertion d'une galerie d'image dans la page détails.

> ### 13/03/2012 ###
    * finition de la page de détails avec la galerie d'image fonctionnelle
    * insertion d'une icône "share" à la place du bouton like

> ### 14/03/2012 & 15/03/2012 ###
    * pouvoir éditer la page de détails d'un objet nous appartenant

> ### 16/03/2012 ###
    * recherche sur la rapidité de chargement des pages css (faire un fichier unique ou non ?)
    * étude du fonctionnement du app.yaml
    * merge du code

> ### 19/03/2012 ###
    * correction de la méthode updateItem après merge du code
    * recherche sur la récupération des données d'une image pour récupérer la hauteur et la largeur en pixel (malheureusement, aucun résultat concluant)

> ### 20/03/2012 ###
    * design de la page de details
    * recherche sur le fonctionnement du bouton share avec google accounts

> ### 21/03/2012 ###
    * merge du code
    * redimensionnement et centrage des images

> ### 22/03/2012 ###
    * réunion de mise au point
    * recherche sur l'implémentation d'une application facebook
    * écriture de l'implémentation du use case Want (début)

> ### 23/03/2012 ###
    * écriture de l'implémentation du use case Want
    * lecture de la doc de google app engine

> ### 26/03/2012 ###
    * implémentation du use case 'Want'

> ### 27/03/2012 ###
    * implémentation des listes "SharedItems" et "BorrowedItems"

> ### 28-29-30/03/2012 ###
    * implémentation du use case 'Want'
    * merge du code avec Malik

## April ##

> ### 02-03-04-05/04/2012 ###
    * refactoring du code
    * ajout de la table ParanYoLogs
    * use case want totalement implémenté
    * amélioration de l'interface utilisateur
    * diagramme d'état pour le use case Want

> ### 10/04/2012 ###
    * grève Stib, lecture doc

> ### 11/04/2012 ###
    * malade

> ### 12/04/2012 ###
    * refactoring du code
    * merge avec maa

> ### 13/04/2012 ###
    * amélioration de l'interface utilisateur
    * amélioration du code

> ### 14/04/2012 ###
    * amélioration de l'interface utilisateur
    * amélioration du code
    * installation et utilisation de pylint

> ### 15/04/2012 ###
    * amélioration du code

> ### 16/04/2012 ###
    * refactoring et amélioration du code
> > (pour ne faire qu'un include avec tous les boutons)


> ### 17/04/2012 ###
    * refactoring et amélioration du code
> > (pour ne faire qu'un include avec tous les boutons)
    * ajout d'un format spécifique pour les dates


> ### 18/04/2012 ###
    * refactoring et améliration du code

> ### 19/04/2012 ###
    * merge et débogage du code

> ### 20/04/2012 ###
    * débogage du code
    * réflexion sur l'internationalisation

> ### 23/04/2012 ###
    * internationalisation

> ### 24/04/2012 ###
    * internationalisation

> ### 25/04/2012 ###
    * internationalisation
    * réflexion sur les reviews

> ### 26/04/2012 ###
    * implémentation des reviews

> ### 27/04/2012 ###
    * implémentation des reviews

# Malik #

## February ##

### 20/2/2012 ###
> étude du datastore et modification du modèle objectToShare et du formulaire de création d'objet pour afficher un bouton d'upload de fichier

### 21/2/2012 ###
> Récuperation et sauvegarde dans la db(datastore) de l'image envoyée

### 22/2/2012 ###
> affichage de l'image enregistrée

### 23/2/2012 ###
> création du lien parent enfant entre l'image(enfant) et l'objet(parent)

### 24/2/2012 ###
> test du code

### 27/2/2012 ###
  * recherche de solution au problème de popup
  * enregistrement des utilisateurs dans la db
  * création de la classe ParanyoUser

### 28/2/2012 ###
  * réorganisation du code et test
  * test de Git

### 29/2/2012 ###
  * étude des decorators en python
  * enregistrement des login et des visites des utilisateurs

## March ##

### 1/3/2012 ###
  * suivi des visites des utilisateurs
  * étude de jQuery

### 2/3/2012 ###
  * étude de jQuery
  * étude d'ajax

### 5/3/2012 ###
  * étude de jQuery
  * analyse des différentes implémentations de sessions pour GAE

### 6/3/2012 ###
  * étude de jQuery
  * analyse des différentes implémentations de sessions pour GAE
  * étude de gaeutils

### 7/3/2012 ###
  * formulaire multi fichier
  * formulaire multi etapes

### 8/3/2012 ###
  * formulaire multi fichier
  * formulaire multi etapes

### 9/3/2012 ###
  * formulaire multi fichier
  * formulaire multi etapes

### 12/3/2012 ###
  * absent pour cause de maladie

### 13/3/2012 ###
  * ajout du choix de thumbnail


### 14/3/2012 ###
  * finalisation de l'interface

### 15/3/2012 ###
  * finalisation de l'interface

### 16/3/2012 ###
  * optimisation du code
  * merge du code avec yannis doukidis

### 19/3/2012 ###
  * revision et correction du code

### 20/3/2012 ###
  * revision et correction du code
  * correction du bug de duplication d'image
  * correction du bug d'onglets/sessions

### 21/3/2012 ###
  * merge du code
  * refactoring

### 22/3/2012 ###
  * réunion de mise au point(?)
  * ecriture de l'implementtation de l'UC - Give
  * optimization des modeles/queries ParanYoImage par un split

### 23/3/2012 ###
  * optimization du code
  * implementation de l'UC- give

### 26/3/2012 ###
  * implementation de l'UC-give
    * ajout de notifications

### 27/3/2012 ###
  * implementation de l'UC-give
    * correction de bugs
    * support pour les dons externes au site

### 28/3/2012 ###
  * test et correction du code

### 29/3/2012 ###
  * give avec recherche dans la db

### 30/3/2012 ###
  * correction de bugs
    * la recherche de noms supporte les majuscules/minusculess
    * urlencode de la redirection apres enregistrement des ParanYoUser

## April ##

### 2/4/2012 ###
  * absent pour cause de maladie

### 3/4/2012 ###
  * orrect de bugs
  * ajout de task queues pour les mails
  * ajout de options utilisateurs (notification par email facultative)
  * refactoring du code

### 4/4/2012 ###
  * refactoring du code

### 11/4/2012 ###
  * suppression du champ image\_id de la db
  * migration du code vers bootstrap http://twitter.github.com/bootstrap

### 12/4/2012 ###
  * migration du code vers bootstrap http://twitter.github.com/bootstrap

### 13/4/2012 ###
  * migration vers bootstrap et revision du code

### 16/4/2012 ###
  * revision du code et mise en conformité avec pylint

### 17/4/2012 ###
  * Give maintenant utilise uniquement ajax
  * mails utilisent html au lieu de texte brut
  * Barre de navigation dispose d'un bouton «Compte»
  * correction de bugs mineurs
  * donner utilise Identifiant élément est la place des touches de poste
  * UserSettings sont maintenant correctement dispalyed
  * l'ensemble du site est passée de h5bp a bootstrap

### 18/04/2012 ###
  * implementation de openid pour l'authentification des utilisateurs

### 19/04/2012 ###
  * merge et dubogage du code

### 20/04/2012 ###
  * arrivée a 10:15
  * test du code
  * revision du datamodel


### 23/04/2012 ###
  * arrivée a 9:20
  * correction de bugs
  * revision du datamodel
  * pause de 13h a 14h
  * mise en cache de tous les compteurs
  * depart a 18:30

### 24/04/2012 ###
  * arrivée a 9:25
  * correction de bug
  * verification de la securité
  * pause de 13h10 a 14h20
  * correction de bugs
  * depart a 18:55

### 26/04/2012 ###
  * arrivée a 9h30
  * pas de pause
  * depart a 18:15

### 27/4/2012 ###
  * arrivée a 9h03


# Abdelkrim #
## April ##

### Fri 06/09/2012 ###
  * Google AdSense is printed inside the footer (correct a bug)

### Mo 09/04/2012 ###
  * create “launch soon" web app called paran-yo-launchsoon.appspot.com
    * it collects email address of people who will be beta testers of the application
  * SeleniumHQ - user testing framework
    * add /paranyo/test/selenium directory with testcase (early draft)
  * pylint
    * add usage samples for pylint from a piece of code rated 3.0/10 to 10.0/10
    * add /paranyo/test/pylint/ directory
  * local unit test using unittest2
    * add /paranyo/test/unittest2\_gae/ directory
    * add /paranyo/test/unittest2 directoy
  * Clean/remove directories
    * /paranyo/utilities/paulirish-html5-boilerplate-06dbc3e

### Wed 11/04/2012 ###
  * correct bug: button "go" is next to email input box
  * add low resolution back image
  * split the template index.html into base.html, google\_analytics.html, interested.html, navbar.html, opengraph.html, thank\_you.html
  * When user input an email address and clicks on "go" button, the email address is stored into Interested

### Thu 12/04/2012 ###
  * push the source code. 15 days since last time, it was too long

### Fri 13/04/2012 ###
  * Test the application since the push.
  * emphasize on the next challenges: pylint, bootstrap twitter

### Mon 16/04/2012 ###
  * Revise yannis' work

### Tue 17/04/2012 ###
  * start studying iOS
  * check status development with ydo and maa

### Wed 18/04/2012 ###

### Thu 18/04/2012 ###
  * Install Mac OS X Lion 17
  * Install Xcode 4.3.2

### Sat 21/04/2012 ###
  * apply chapter 1: http://techbus.safaribooksonline.com/9780132978767

### Sun 29/04/2012 ###
  * try zxing open source library to read QR code using an iphone ipad
    * http://code.google.com/p/zxing/
    * source code: https://bitbucket.org/abdelkrim/patajons.ios
    * build the project : OK
    * **todo**: code an application that read a code and store it
  * try zbar open source library to read QR and EAN-`*` codes
    * http://zbar.sourceforge.net/iphone/index.html
    * looks ok but the question is : which one is OK?

## May 2012 ##
### 14/05/2012 ###
  * index. html generates neither error nor warning with facebook linter
  * item.html generates only a warning with facebook linter:
    * the thumbnail of an item should be bigger than 200px
    * note that the thumbnails do not show several images anymore!
  * google analytics is set with `*`.appspot.com