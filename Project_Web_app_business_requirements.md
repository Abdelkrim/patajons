The theory [How to write a Use Case?](Theory_HowToWriteAUseCase.md)

# Functional requirements #

## Roles ##
  1. Registered user
    1. Item Owner: a registered user who owns a selected item
    1. Item Receiver: a registered or not registered user who might become the owner of the item; he will receive the item
    1. Item Borrower: a registered user who borrows an item from an Item Owner; he will use the item for a limited period

  1. Non registered user
    1. Visitor

## Features ##
  1. Notification: Messages sent to the registered or not registered user; it can be an information, a message requiring an action (accept, reject, etc.)
    1. On-Site notification: a notification received on the website
    1. Email Notification: a notification received by email

## USE CASE "A owner 'GIVE's an item to a user" ##

  1. Brief description
    * The Owner of an item gives it to another registered user (item receiver).
    * The operation will change the ownership of the item between two registered users.

  1. Flow of events
    1. The Owner selects the item he wants to give
    1. Choice (either...or)
      1. The Owner inputs the first name and lastname of the registered user (Receiver)
      1. The Owner inputs the email address of the non registered person (Receiver)
    1. The Owner confirms the operation (giving the item to someone else)
    1. A Notification is sent to the Receiver
      1. if the Receiver is registered he might receive an email and/or a notification based on his settings
      1. if the Receiver is not registered, he will receive an email containing the goal of the email (to become the owner of an item given by a Registered User) and the possible actions (Accept, Refuse, Report a Spam)
    1. The person who receives the item becomes the owner of the item

  1. Basic flow
    1. Idem as Flow of events

  1. Alternative flows
    1. The owner wants to give an item to an unregistered user
      1. The owner inputs the email address of the person to whom he wants to give the object instead of his first name and lastname

  1. Special requirements
    1. None so far

  1. Preconditions
    1. The registered user owns the item

  1. Post conditions
    1. The new owner of the item is the registered user who has accepted to receive the item
    1. The registered user who has given the item is not the owner of the item anymore

  1. Extension points
    1. None so far

## USE CASE "A Borrower 'WANT's to borrow an item" ##

  1. Brief description
    * The Borrower wants to use the item of someone else (Item Owner)
    * The operation will impeach a registered user to borrow the same item from the Item Owner
    * The list of items borrowed by the Borrower will contain the new Borrowed Item
    * The list of items shared by the Item Owner will contain the new Shared Item

  1. Flow of events
    1. The Borrower selects the item he wants to borrow
    1. The Borrower clicks on the button "WANT"
    1. A popup window requests a confirmation: "Do you want to inform the [User](Registered.md) that you want to borrow the [Item](Item.md)"
    1. A Notification is sent to the Item Owner
    1. Choice (either..or)
      1. The Item Owner accepts to share the item to the Borrower
        1. The Borrower receives the feedback from the Item Owner
        1. The item is added into the list of items borrowed by the Borrower
        1. The item is added into the list of items shared by the Item Owner
      1. The Item Owner refuses to share the item to the Borrower with an explanation: "I won't share the [Item](Item.md) for the moment because (1) I am using you live too far (2) I don't old it for the moment (3) other"
        1. The explation is sent to the Borrower
      1. The Item Owner delays the sharing of the item with an explanation: "I can't share the [Item](Item.md) for the moment because (1) I am using it (2) I don't old it for the moment (3) other"
        1. The explanation is sent to the Borrower

  1. Special requirements
    1. None so far

  1. Preconditions
    1. None so far

  1. Post conditions
    1. The Borrower olds the item if the Owner has accepted to share the item
    1. The status of the item has not changed if the Owner has not accepted to share the item
    1. The status of the item has not changed if the Owner has not delayed the sharing of the item

  1. Extension points
    1. None so far

## USE CASE "A User 'OWN's an existing item and stores it into his list" ##
  1. Brief description
    * The User (registered or not) founds a description of an item that he owns, he decides to add the same item into his personal list of items
    * The selected item is added to the list of items owned by the User

  1. Flow of events
    1. The User has found a description of an item that he owns
    1. The User clicks on the button "WANT"
    1. A popup window requests a confirmation: "Do you own the same [Item](Item.md) and want to add it into your list?"
      1. The User confirm that he owns the item
        1. The item is added into his personal list of items
        1. The Item Owner edits the description of the item
        1. The Item Owner edit the images of the item
        1. The Item Owner submit his latest changes

  1. Special requirements
    1. None so far

  1. Preconditions
    1. None so far

  1. Post conditions
    1. The Borrower olds the item if the Owner has accepted to share the item
    1. The status of the item has not changed if the Owner has not accepted to share the item
    1. The status of the item has not changed if the Owner has not delayed the sharing of the item

  1. Extension points
    1. None so far

## The Borrower evaluates the item he has borrowed ##
To be defined

## The Item Owner evaluates the Borrower ##
To be defined


## The Borrower revises the quality of the object ##
To be defined

## USE CASE "what can people share close to me" ##

  * I am anywhere in the world (camping, holidays, etc.)
    * I want to know what people are willing to share
    * I need a lighter, a butagaz, etc.
  * don't forget to hide who is willing to share the item IF he/she is not in the list of friends

## USE CASE "I borrow an object " ##
  * I use the smartphone
  * I take a picture of the barcode
  * Paran Yo gives the list of friends who owns the item
  * the user can click on the person to whom he wants to borrow the item
  * or he clicks on "select all owners"
  * he confirms his choice

  1. borrower recognise the item through the barcode
  1. borrower selects the owner
  1. the owner accepts
  1. DONE!


# Facebook integration #

## Yannis ##

### Requirement ###
  1. To inform your friends that you are willing to share an object
    1. If a user has created a new object
      1. The system shares the link to the object into the wall of his friends

### Requirement analysis ###
  1. The system needs to allow the user to click on a button (e.g. like) linked to the item.

### System design ###
  1. Create a new read-only page giving the details of the object
  1. Show the "like" button from Facebook

TODO:
  1. to create one static page including 2 objects and two like buttons (see http://malik-esi-test.appspot.com/readobject)
  1. what happen if the page is not unique?
  1. what happen if the page is not public?

# Detailed scenario (to be ordered) #


## Person ##
  * login [TechnicalRequirementsWebApp](TechnicalRequirementsWebApp.md)
  * logout
  * create new user
  * edit profile
  * delete a user
  * invite friends
  * remove friends

## object ##
  * add object owned by the current user
  * remove an object owned by the current user
  * Share an object with a friend
  * share all objects with his/her partner


## event ##
  * create an event
  * edit an event
  * close an event
  * add a participant
  * remove a participant

## car sharing ##
  * new route
  * edit route
  * close route

## Jobs posting ##
  * add new job (e.g. cleaning lady, baby sitter)
  * close a job

## baby-sitting event ##
  * add a availability
  * close a availability

## To lend a house for holidays ##
  * owner point of view
    * edit the availability of the house
    * grant the lending of the house for specified dates

  * user point of view
    * search for availability based on many criteria
      * country
      * amount of rooms
      * etc.
    * ask to lend the house


## To organise an group event "...we go there..." "...Group price is..." ##
  * first mover family
    * select the event
    * inform friends that a family goes to an event
    * set the amount of seats available for poor children
    * deadline after which joining is impossible
  * Joiners
    * parents join the event
  * admin
    * event is automatically closed


## Parents can give unnecessary objects to non profit organisations ##
  * Select the object you plan to give
    * admin
      * non profit is informed that an object can be received


## Parents could bring poor children with them for activities ##
  * non profit proposes children who are free to participate to events with other families