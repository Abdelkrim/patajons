# Introduction #
List of todo's we should implement befor end of May 2012

# Roadmap #

## for Yannis ##
  1. toutes les popup doivent s'ouvrir de la même manière
  1. pourquoi items.html s'affiche mal uniquement avec firefox
  1. check the application with W3C validators et corriger ce qui est possible:
    1. http://validator.w3.org/check?uri=http%3A%2F%2Fparan-yo-dev-maa.appspot.com%2Fitems&charset=%28detect+automatically%29&doctype=Inline&group=0&user-agent=W3C_Validator%2F1.3
    1. ne pas corriger cette erreur:  “Bad value X-UA-Compatible for attribute http-equiv on element meta"
    1. mettre un tag alt sur chacune des images : name + description of the item

  1. revoir le design de tes derniers travaux:le design n'est pas 'beau'
  1. email: s'assurer que l'on a un design propre, des emails ne sont pas envoyés en HTML
  1. retirer les tableaux dans les écrans notifications et essayer de réutiliser
  1. carrousel montre en premier l'image qui a été sélectionnée
  1. revoir la couleur des boutons pour avoir moins de couleurs - en vert les boutons submit et laisser les autres en gris


## v0.1 ##
  * Login page using several providers: facebook, linkedin, twitter, etc.
  * Facebook supports (April 2012): [theory\_websites\_specifications](theory_websites_specifications.md)
  * Marketing
    * Start a Survey (abo)

  * Marketing
    * Integrate Google Analytics on each page of the website (abo)

  * Review of the borrower
    * the owner should review a borrower when he/she gives back an item to the owner (maa)
    * see http://ui-patterns.com/patterns/RateContent

  * Controller
    * check whether we use correctly the memcache  (maa - ydo - abo)
    * Mobile  (abo)
      * iOS integration: check how to develop the json integration

  * Legal constraints
    * Email: check the law and add all the mandatory requirements required by law (e.g. unsubscribe) (abo)
    * http://business.ftc.gov/documents/bus61-can-spam-act-compliance-guide-business

  * Documentation
    * write technical documentation for each use case (maa - ydo - abo)
    * write each use case (maa - ydo - ago)

  * home page: update the text from the home page  (maa - ydo - abo)

  * Settings page  -- Done
    * can we send a notification by email to the user? -- Done
    * can we send newsletters containing the latest info from your friends (add item, borrow, give actions) ?
    * newsletters  (maa - ydo)
      * create a administration console for the administrator of the website



  * Screens update
    * use the carrousel of Twitter Bootstrap
    * teste avec le clavier seulement (utilise "tab") **done**
    * couleur des boutons pour que l'on comprenne ce que l'on fait
    * menu général
      * user settings: use the default menu "tab" and not a button **done**
      * lien vers les settings quand click sur bouton et mettre un menu dans la page settings avec settings et sign out comme http://twitter.github.com/bootstrap/scaffolding.html#gridSystem (fluid layout)
    * change the email address by first+lastname - NO MORE EMAIL IS SHOWN **done** except bug with give (http://code.google.com/p/patajons/issues/detail?id=46)
    * always use the popup of bootstrap
    * always show action button with DETAILS first

  * http://paran-yo-dev-ydo.appspot.com/items
    * http://www.tradeaway.com/
    * BUG: items disappear if they are not (at least) AVAILABLE - check the new structures
    * BUG: amount of notifications is incorrect

  * http://paran-yo-dev-ydo.appspot.com/_ah/login_required?continue=/
    * retirer les images/texte à partir de  "Additional images" **done**

  * http://paran-yo-dev-ydo.appspot.com/register?continue=http%3A%2F%2Fparan-yo-dev-ydo.appspot.com%2Fcheck_register%3Fcontinue%3D%2F
    * test avec mobile **Problem with the css**
    * revoir l'affichage du formulaire

  * http://paran-yo-dev-ydo.appspot.com/usersettings
    * put the text in the middle of the screen

  * http://paran-yo-dev-ydo.appspot.com/itmtx?cmd=new
    * put the text in the middle **done**
    * check the compliancy with bootstrap (change the form type) **done**
    * change the colour of the buttons (maybe add a glyph) **done**

  * http://paran-yo-dev-ydo.appspot.com/itmtx (upload the images)
    * move to carrousel of bootstrap (keep the same requirements-functionalities)

  * http://paran-yo-dev-ydo.appspot.com/itmtx (popup upload)
    * reduce the width of the table (check with mobile device)

  * http://paran-yo-dev-ydo.appspot.com/item?id=27027 (item page)
    * use the caroussel of bootstrap
    * mobile: ensure that the tables goes one after the one in one column
    * user informations
    * remove the "details of"
    * show the first name of the user and no more its email address
    * item status (same style-font as the other attributes)
    * do not show the actions if they are empty

  * http://paran-yo-dev-ydo.appspot.com/notify (notifications)
    * If they are no items at all, we need to show general message: "You have no transaction, Share or give items!"
    * do not show the items that are empty
    * when "cancel the gift" :
      * remove the line in the list only (using jquery - think about what can happen if javascript is disabled)

  * http://paran-yo-dev-ydo.appspot.com/sharedItems (shared items)
    * If they are no items at all, we need to show general message: "You have no transaction, Share or give items!"

  * item (facebook)
    * the share button doesn't work anymore
# MAA #
```
check threading python 2.7/webapp2
add simple auth
catch exemption in prefetch_refprops

add 25+ notify

fixed row heights in upload form
déactivate send after first click

check if submitted data to give is an email

update dynamicaly the upload form to show the status -> update only the numbers

gerer les erreurs 403 avec template

add facebook openid
handle email list for paranyo users

add floating alerts

add constants for actions
add transaction
```
## v0.2 ##

  * Sales
    * Integrate Google AdSense on some pages of the website (item details, readobject) (abo)

  * Application is multilingual
    * create the framework that can accept any language (maa - ydo)
      * French
      * English
      * Dutch

## v0.3 ##
  * provide means to share email between the users

  * shoptimate
    * implement a similar module and show the items that are shared by your friends
      * if you are on Sony, universal, etc. we should show the availability of the item by friends
    * http://www.shoptimate.com/

## v0.4 ##
  * Wish list
    * add a wish list allowing people to list the items they need or want in the future. can be items that are not available yet

# Road map technicalities #

  * Testing
    * write test cases to test the whole application (maa - ydo - abo)

  * Integration with API
    * Integrate the Amazon API on the details page (maa)
    * Integrate the Twitter API on the details page (maa)
    * Integrate the Facebook API on the details page (ydo)
    * integrate the iTunes API (if it has any sense)
    * Integrate the Google Android Marketplace (if it has any sense)
    * Integrate the Microsoft Windows Phone Marketplace (if it has any sense)

  * backend
    * find the exhaustive list of mime types we want to use for the pictures (jpg, jpeg, png, gif) -- Done

  * Items
    * divide the Items into ParanYoUser, ParanYoItem, ParanYoImage
    * move the from the main.py the objects defining the  -- done

  * Migrations
    * Migrate to Python 2.7 (maa - ydo - abo)
    * Migrate to Google App Engine Launcher 1.6.4 (maa - ydo - abo)

  * Source Quality assurance (use pylint)
    * review the source code (maa - ydo - abo)
      * refactor the code when necessary (Object Oriented code),
      * ensure coding style consistency,
      * rename the controller: itemtx => itmtx (remove the voyels) -- Done
      * review the database structure based on the GAE theory
      * review the database structure  based on the NoSQL theory
      * aggregate the perkins css into one single CSS - this might fasten the load of the CSS since the extension of the files are known and not .less anymore

  * Model - datastore structure
    * how to migrate the data? test the migration of data as well as the backup between two appengine applications
    * check the consistency of the data structure (models.py) against the best practices (NoSQL, google website)

  * View
    * should we implement backbone.js onto our website?  (abo - maa - ydo)
    * HTML5 check compliancy  (maa - ydo)
    * CSS3 check compliancy  (maa - ydo)
    * jQuery check compliancy  (maa - ydo)

# low priority #

  * View - User Interface of the application
    * Check the correct usage of the perkins css (legacy)
    * Ensure the User Interface is beautiful on each single page (maa - ydo - abo)
    * popup: develop a template for popup to ensure they look all the same (maa - ydo - abo)
    * Emailing: develop a template for sending emails, they should look all the same (maa - ydo - abo)

  * update the HTML5 boilerplate (if necessary)  (maa - ydo) (legacy)
  * update the perkins css (if necessary)  (maa - ydo)

  * Do we keep our fonts? it is a huge amount of data (±250 Kbytes per page if not cached)
  * check our user interfaces (html pages) against http://www.ui-patterns.com

  * update Registration page with new criteria to be defined (address: home, working, leisure)

  * add the OpenGraph to make the link between people (friend, coworker, etc.)

# Done #

## login ##
  * store the login credentials into our ParanYoUser object -- Done

## Facebook ##
  * implement the Like button (done)
  * send a customised message to the wall of someone (done)
  * create a Facebook APP if needed in order to address our needs

## EBay ##
  * How to sell an item (screenshots): http://alt-f1.be/paranyo/

## Give ##
  * ajax query to get first/lastname -- Done
  * move action buttons to the left in givelist -- Done
  * registration page with first/lastname -- Done
  * add timestamp to ParanYogiveLog -- Done
  * remove give after give -- Done
  * add cancel button -- Done

## mail ##
  * taskqueues for outgoing mail -- Done
  * check if mail exist before sending -- not to do


# News / documentation #

## google app engine ##
  * http://www.gaecupboard.com
  * http://activelearningblog.com/2010/10/why-we-switched-from-google-app-engine-to-ec2/
  * http://blog.gramfeed.com/post/18460554119/2-hour-side-project-to-2-million-visitors
  * http://blog.initlabs.com/post/16359268329/how-i-reduced-google-app-engine-costs-by-75
  * http://stackoverflow.com/search?q=user%3A130929+%5Bgoogle-app-engine%5D
  * http://stackoverflow.com/questions/565963/hidden-limitations-of-google-app-engine/3068371#3068371
  * http://code.google.com/p/googleappengine/issues/list
  * http://stackoverflow.com/questions/572780/cpython-internal-structures
  * http://stackoverflow.com/questions/3793860/how-to-set-up-a-staging-environment-on-google-app-engine
  * http://stackoverflow.com/questions/2919517/google-app-engine-and-git-best-practices
  * http://stackoverflow.com/questions/9429436/google-app-engine-prohibitively-slow-and-expensive-backup-and-restore

## jcarousel ##
  * add a border to the pictures -- Done
  * center the image -- Done
  * buttons aligned at the bottom -- Done
  * use jcaroussel  constructor to size jcaroussel-items
  * set a white background to the jcarousel -- Done

## optimization ##
  * split image data form image metatadata (best will be link image\_id with data entity key\_name) -- Done

## design ##
  * Logo en couleur avec des lanes like a painting

## business model ##
  * Creer une assurance pour le partage de voitures
  * Multiplier les sources de revenus, pas uniquement google

## advertising on our site ##
  * Create a tool as a web agency