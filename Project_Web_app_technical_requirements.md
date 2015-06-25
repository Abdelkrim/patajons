# use case "log using social networks credentials #
  * facebook
  * twitter
  * google
  * linkedin
  * yahoo
  * windows live

## simpleauth autenthication ##

  * sample application: https://simpleauth.appspot.com/
  * library on python.org http://pypi.python.org/pypi/simpleauth
  * blog of alex vagin: http://alex.cloudware.it/2012/02/simple-auth-on-app-engine-without.html
  * github source code: https://github.com/crhym3/simpleauth


# Use Case « A Borrower ‘Wants’ to borrow an item » #
## Attributes ##
  * Item\_key : the key of the item

## Views ##
### item details - /item - items.html ###
  * add a button “Want” into the page: /item?ParanYoItem='item\_key'

### Share an item - /shareItem (TBR) - shareItm.html (TBR) ###
  * A radio button “I accept to Share”
  * A radio button “I won’t Share”
  * A radio button “I can’t Share”
  * A button “Ok”

### The list of items borrowed by the Borrower - ###
> TBR add the content of the page

  * Query for the list of borrowed items of the borrower:
```
SELECT *
FROM ShareLog
WHERE Borrower_email = 'current_user'
AND end_date IS NULL 
```

### The list of items shared by the Item Owner - ###
> TBR add the content of the page

  * Query for the list of shared items of the owner:
    * We are looking into the table the owner\_email and if the end\_date is empty.

## Models ##

### table name : "ShareLog"(TBR) ###

| Item\_key | The key to the shared object |
|:----------|:-----------------------------|
| Borrower\_email | The email of the borrower    |
| Owner\_email | The email of the owner       |
| Start\_date | the date when the owner accepts to share the item |
| End\_date | the date when the borrower gives back the item he has borrowed from the owner |

Sample:

| 'item\_key' | borrower@email.com | owner@email.com | 24/03/2012 | empty |
|:------------|:-------------------|:----------------|:-----------|:------|
| 'item\_key' | borrower@email.com | owner2@email.com | 24/03/2012 | 25/03/2012 |


## Controller ##
### items.html ###
#### Button "Want" ####
```javascript

onclick="confirm()"
confirm(“Are you sure to: inform the item Owner and borrow this item?”)
```

  * If borrower clicks on 'OK' then
    * a notification is sent to the item Owner.

### /notification ###
> TBD : create model for notification
  * method mail.send\_mail(sender\_address, borrower\_address, subject, body)
  * method onSiteNotif(sender\_address, borrower\_address, subject, body)

### Share an item - /shareItem (TBR) - shareItm.html (TBR) ###
  * Precondition :
    * The owner clicks on the link into the mail
  * Postcondition :
    * The response is send to the Borrower

# WebApp Technical requirements based on [BusinessRequirementsWebApp](BusinessRequirementsWebApp.md) #

## Person ##
| Function | Technology | Version |
|:---------|:-----------|:--------|
| Login / Sign in | Google Friend Connect | v0.8    |
| Logout / Sign out | Google Friend Connect | v0.8    |
| Create new user | none       | none    |
| edit profile | Google Friend Connect | v0.8    |
| delete a user | None       | None    |
| Invite friends | Google Friend Connect | v0.8    |
| Logout / Sign out | Google Friend Connect | v0.8    |
| Remove friends | None       | None    |


## object ##

| Function | Technology | Version |
|:---------|:-----------|:--------|
| Add object owned by the current user | XXXX       | vX.XX   |
| Remove an object owned by the current user | XXXX       | vX.XX   |
| Share an object with a friend | XXXX       | vX.XX   |
| Share all objects with his/her partner | XXXX       | vX.XX   |
| show and select a picture | jCaroussel/jCaroussel | v0.2.8  |


# template #
| Function | Technology | Version |
|:---------|:-----------|:--------|
| XXXX     | XXXX       | vX.XX   |

####  ####
cd /Applications/GoogleAppEngineLauncher.app/Contents/Resources/GoogleAppEngine-default.bundle/Contents/Resources/google\_appengine/lib/