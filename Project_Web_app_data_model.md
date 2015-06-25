# Setup data model #
  * Items
    * list of items for children with pictures and description

# data model #
  * item (item a user is willing to share)
    * o\_id PK - id of the object that can be shared
    * descr - description of the object
    * buy\_year - year when the object was bought
    * Buy\_shop - where did you buy the object?
    * Price - at which price did you buy the object?
    * Usage\_Limitation - practical indication like limitation with regard to the age of the user of the toy, it can be a weight
    * Photo - picture of the object - this can be several pictures

  * user
    * p\_id PK (do we have to create m2n db link to show who does what?)
    * firstname
    * lastname
    * birthdate
    * email\_address
    * gender
    * baby sitter - Y/N   (is a baby sitter or not)

  * sharetx (keep track of the items that are shared)
    * o\_id FK  (object that is shared)
    * owner p\_id FK (person who share the object)
    * receiver p\_id FK (the person who is sharing the object for a limited period)

  * genealogy (link between people)
    * p\_id FK (one person)
    * p\_id FK (another person)
    * rt\_id FK (the relation between those persons)

  * relation\_type - between two persons
    * rt\_id PK - list of values
      * partner
      * child
      * friends (means that people can see each other objects)

  * car sharing
    * starting point
    * ending point
    * maximum amount of seats available
    * maximum amount of luggages
    * Smoke inside the car Y/N
    * children seats available - LIST
      * Amount of seats
      * Age of the seat
    * close the route if the car is full, no more interest

  * baby-sitter (schedule a baby sitting)
    * p\_id FK
    * Schedule
      * start
      * end
    * review rate - review of the baby sitting
    * Price per hour

  * lend a house for holidays
    * p\_id FK - owner of the house
    * description of the house
    * pictures of the house
    * schedule when the house is occupied

  * Facebook
    * id\_facebook (keep the id of people who agreed to connect to Paran yo)