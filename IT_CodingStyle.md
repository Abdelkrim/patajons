# Introduction #

  * TBR: to be revised

  * Coding guidelines: http://pycogent.sourceforge.net/coding_guidelines.html

  * naming and indentation conventions : http://www.python.org/dev/peps/pep-0008/
    * we use 4 spaces-tabs
    * Camel Style naming for classes
    * all-lowercase packages and modules names
    * using a `__all__` list to avoid exporting globals in modules

  * code source structure based on **rietveld** example : [Rietveld source code](http://code.google.com/p/rietveld/source/browse/#hg%2Fcodereview)
    * one package paranyo
      * one models module
      * one views module
    * one main module at the root

  * No spaces or accents in project names , files or folders (believed to make appengine launcher crash at startup)

**-=TBR=-** delete/edit ~/google/google\_appengine\_projects.ini (replace ~ with %HOMEDIR% on window$) in case of problems

# iOS #
  * doc: http://techbus.safaribooksonline.com/9780132978767/

## iOS conventions ##
  * Views are usually standard **UIView** subclasses (UIButton, UISlider)
  * Models use standard collection classes (NSArray, NSDictionary, NSSet) and standard value types (NSString, NSDate, NSNumber)
  * Controller
    * Every iOS application has an “app delegate” object, and it is the primary controller of the application.

  * connections between the controller and the view
    * e.g., IBOutlet and IBAction (.h)

## iOS declarations ##
  * Controller needs instance variables and methods: you need to declare them in the Controller header file, <controller type>Controller.h

## naming convention ##
  * Views
    * <object type>View e.g., DangerMeterView or IncomeGraphView
  * Models
    * <data-bearing objects> e.g. InsurancePolicy or PlayerHistory
  * Controllers
    * <controller type>Controller e.g., ScheduleController and ScoreViewController

  * there is no name space then:
    * Stylish Objective-C programmers always prefix their model and view classes. The prefix is typically related to the name of the application you are developing or the library it belongs to.
    * controller are local to the application, they don't need to be prefixed
    * Apple classes are prefixed by framework
## Files types ##
  * .h
    * Define controller needs in term of variables and methods
    * Best practice:
      * Class methods come first, followed by initializers, followed by any other methods.
  * .xib
  * .m
    * he implementation file e.g., <project name>ViewController.m

## object types ##
  * NSMutableArray (fig. 1.10)
    * a single array can contain objects of different types.
    * Arrays hold references to Objective-C objects
    * Arrays **cannot** hold C structures nor primitives e.g., you can' have an array of ints
    * NSNull add "holes" to an array (you can't add nil to an array)
      * ​e.g., [​a​r​r​a​y​ ​a​d​d​O​b​j​e​c​t​:​[​N​S​N​u​l​l​ ​n​u​l​l​]​]​;​
  * IBOutlet and IBAction (.h) allow you to connect your controller and your view objects in the XIB file.
  * NSDictionary
  * NSSet
  * NSString
  * NSNull represents nil and used in NAMutableArray

## Name space ##
  * Objective-C has no notion of namespaces. Instead, we prefix class names with two or three letters to keep them distinct

## Load of an application ##
  * When the application launches, the <project name>ViewController will be sent the message initWithNibName:bundle:

# Objective C #

## String ##
  * hard-coded string, you prefix a character string with an @ symbol
    * NSLog(@"hello world");

```
N​S​S​t​r​i​n​g​ ​*​m​y​S​t​r​i​n​g​ ​=​ ​@​"​H​e​l​l​o​,​ ​W​o​r​l​d​!​"​;​
i​n​t​ ​l​e​n​ ​=​ ​[​m​y​S​t​r​i​n​g​ ​l​e​n​g​t​h​]​;​

l​e​n​ ​=​ ​[​@​"​H​e​l​l​o​,​ ​W​o​r​l​d​!​"​ ​l​e​n​g​t​h​]​;​

m​y​S​t​r​i​n​g​ ​=​ ​[​[​N​S​S​t​r​i​n​g​ ​a​l​l​o​c​]​ ​i​n​i​t​W​i​t​h​S​t​r​i​n​g​:​@​"​H​e​l​l​o​,​ ​W​o​r​l​d​!​"​]​;​
l​e​n​ ​=​ ​[​m​y​S​t​r​i​n​g​ ​l​e​n​g​t​h​]​;​
```

## format string ##
```
i​n​t​ ​a​ ​=​ ​1​;​
f​l​o​a​t​ ​b​ ​=​ ​2​.​5​;​
c​h​a​r​ ​c​ ​=​ ​'​A​'​;​
N​S​L​o​g​(​@​"​I​n​t​e​g​e​r​:​ ​%​d​ ​F​l​o​a​t​:​ ​%​f​ ​C​h​a​r​:​ ​%​c​"​,​ ​a​,​ ​b​,​ ​c​)​;​
```

## %@ token ##
  * When %@ is encountered in the format string, instead of the token being replaced by the corresponding argument, that argument is sent the message description.

## Class / Objects ##

### methods ###
#### instance methods ####
  * Instance methods (like init) are sent to instances of the class
  * Syntactically: a class method uses the **+** character just before the return type
```
+ (id)randomItem;
```

#### class methods ####
  * class methods (like alloc) are sent to the class itself
  * Class methods typically either create new instances of the class or retrieve some global property of the class.
  * Class methods do not operate on an instance or have any access to instance variables
  * Common use: to provide convenient ways to create instances of that class
  * class methods that return an object of their type (like stringWithFormat: and
> > randomItem) are called **convenience methods**

  * Syntactically: An instance method uses the **-** character just before the return type,
```
- (id)initWithItemName: (NSString *)name
        valueInDollars:(int)value
          serialNumber:(NSString *)sNumber;
```

### Create object ###
  * "P​a​r​t​y​ ​`*`p​a​r​t​y​I​n​s​t​a​n​c​e​ ​=​ ​[​[​P​a​r​t​y​ ​a​l​l​o​c​]​ ​i​n​i​t​]​;​" //Party is a class, **you must call init method before using the instance**

### init ###
  * init methods are always declared to return id

### isa or "is a" ###
  * The object itself also knows its type – thanks to its isa pointer (read "is a")
  * The isa pointer is where Objective-C gets much of its power. At runtime, when a message is sent to an object, that object goes to the class named in its isa pointer and says, “I was sent this message. Run the code for the matching method.” This is different than most compiled languages, where the method to be executed is determined at compile time.

### self ###
  * self is an implicit local variable
```
-​ ​(​v​o​i​d​)​c​h​i​c​k​e​n​D​a​n​c​e​
{​
 ​ ​ ​ ​[​s​e​l​f​ ​p​r​e​t​e​n​d​H​a​n​d​s​A​r​e​B​e​a​k​s​]​;​
}
```

### super ###
  * run the superclass method
```
-​ ​(​v​o​i​d​)​s​o​m​e​M​e​t​h​o​d​
{​
 ​ ​ ​ ​[​s​e​l​f​ ​d​o​M​o​r​e​S​t​u​f​f​]​;​
 ​ ​ ​ ​[​s​u​p​e​r​ ​s​o​m​e​M​e​t​h​o​d​]​;​
}​
```
### Destroy an object ###
  * e.g., p​a​r​t​y​I​n​s​t​a​n​c​e​ ​=​ ​n​i​l​;​

### Sending messages ###
  * a class cannot have two methods with the same name
  * a message sent to nil is ignored.
    * e.g.,
      * partyInstance = nil;
      * [sendConfirmation](partyInstance.md); //you can send a message without a nil-check
  * message anatomy.
    * a message is always contained in square brackets.
    * Within a pair of square brackets, a message has three parts:
      * receiver: a pointer to the object being asked to execute a method
      * selector: the name of the method to be executed
      * arguments: the values to be supplied as the parameters to the method
    * e.g.,
      * [​p​a​r​t​y​I​n​s​t​a​n​c​e​ ​a​d​d​A​t​t​e​n​d​e​e​:​s​o​m​e​P​e​r​s​o​n​]​;​
      * [​p​a​r​t​y​I​n​s​t​a​n​c​e​ ​a​d​d​A​t​t​e​n​d​e​e​:​s​o​m​e​P​e​r​s​o​n​ ​w​i​t​h​D​i​s​h​:​d​e​v​i​l​e​d​E​g​g​s​]​;​


### properties ###

  * There are three attribute of a property
    * **nonatomic or atomic**. This attribute has to do with multi-threaded applications and is outside the scope of this book. Most Objective-C programmers typically use nonatomic: we do at Big Nerd Ranch, and so does Apple.
  * **readwrite or readonly**. A readwrite property declares both a setter and getter, and a readonly property just declares a getter
  * **strong or work or copy**. assign for properties like int\*eger**that do not point to an object
    * copy: when you have a property that points to an instance of a class that has a mutable subclass (like NSString or NSArray), it is safer to make a copy of the object to point to rather than pointing to an existing object that could have other owners**

```
@​p​r​o​p​e​r​t​y​ ​N​S​S​t​r​i​n​g​ ​*​i​t​e​m​N​a​m​e​;​
```
When you declare a property, you are implicitly declaring a setter and a getter for the instance variable of the same name. So the above line of code is equivalent to the following:
```
-​ ​(​v​o​i​d​)​s​e​t​I​t​e​m​N​a​m​e​:​(​N​S​S​t​r​i​n​g​ ​*​)​s​t​r​;​
-​ ​(​N​S​S​t​r​i​n​g​ ​*​)​i​t​e​m​N​a​m​e​;
```

  * Copy
```
@​p​r​o​p​e​r​t​y​ ​(​n​o​n​a​t​o​m​i​c​,​ ​c​o​p​y​)​ ​N​S​S​t​r​i​n​g​ ​*​i​t​e​m​N​a​m​e​;​
@​p​r​o​p​e​r​t​y​ ​(​n​o​n​a​t​o​m​i​c​,​ ​c​o​p​y​)​ ​N​S​S​t​r​i​n​g​ ​*​s​e​r​i​a​l​N​u​m​b​e​r​;​
```
    * Now the generated setter method for the synthesized itemName property looks like this:
```
-​ ​(​v​o​i​d​)​s​e​t​I​t​e​m​N​a​m​e​:​(​N​S​S​t​r​i​n​g​ ​*​)​s​t​r​
{​
 ​ ​ ​ ​i​t​e​m​N​a​m​e​ ​=​ ​[​s​t​r​ ​c​o​p​y​]​;​
}​
```

  * property with all its attributes
```
@​p​r​o​p​e​r​t​y​ ​(​n​o​n​a​t​o​m​i​c/atomic​,​ ​r​e​a​d​o​n​l​y/readwrite​,​ ​s​t​r​o​n​g/weak​/copy)​ ​N​S​D​a​t​e​ ​*​d​a​t​e​C​r​e​a​t​e​d​;​
```

#### synthesise properties ####
```
@​s​y​n​t​h​e​s​i​z​e​ ​i​t​e​m​N​a​m​e​;​
```
is equivalent to
```
-​ ​(​v​o​i​d​)​s​e​t​I​t​e​m​N​a​m​e​:​(​N​S​S​t​r​i​n​g​ ​*​)​s​t​r​
{​
 ​ ​ ​ ​i​t​e​m​N​a​m​e​ ​=​ ​s​t​r​;​
}​
-​ ​(​N​S​S​t​r​i​n​g​ ​*​)​i​t​e​m​N​a​m​e​
{​
 ​ ​ ​ ​r​e​t​u​r​n​ ​i​t​e​m​N​a​m​e​;​
}​
```

## Dot Syntax ##
  * An alternative syntax for sending accessor messages to an object called dot syntax:
```
/​/​ ​F​o​l​l​o​w​i​n​g​ ​t​w​o​ ​l​i​n​e​s​ ​a​r​e​ ​e​x​a​c​t​l​y​ ​e​q​u​i​v​a​l​e​n​t​
i​n​t​ ​v​a​l​u​e​ ​=​ ​[​i​t​e​m​ ​v​a​l​u​e​I​n​D​o​l​l​a​r​s​]​;​
i​n​t​ ​v​a​l​u​e​ ​=​ ​i​t​e​m​.​v​a​l​u​e​I​n​D​o​l​l​a​r​s​;​

/​/​ ​F​o​l​l​o​w​i​n​g​ ​t​w​o​ ​l​i​n​e​s​ ​a​r​e​ ​e​x​a​c​t​l​y​ ​e​q​u​i​v​a​l​e​n​t​
[​i​t​e​m​ ​s​e​t​V​a​l​u​e​I​n​D​o​l​l​a​r​s​:​5​]​;​
i​t​e​m​.​v​a​l​u​e​I​n​D​o​l​l​a​r​s​ ​=​ ​5​;​
```

## Managing memory with ARC Automatic Reference Counting ##

### the Heap ###
  * All Objective-C objects are stored in a part of memory called the heap

### the stack ###

### strong reference ###
  * anytime a pointer variable stores the address of an object, that object has an owner and will stay alive

### weak reference ###
  * A weak reference is useful for an unusual situation called a retain cycle. A retain cycle occurs when two or more objects have strong references to each other.
  * To declare a variable as a weak reference, we use the `__weak` attribute.
```
_​_​w​e​a​k​ ​B​N​R​I​t​e​m​ ​*​c​o​n​t​a​i​n​e​r​;​
```

## Delegate design pattern ##
### Protocols ###
  * For every object that can have a delegate, there is a corresponding protocol that declares the messages that the object can send its delegate. The delegate implements methods from the protocol for events it is interested in. When a class implements methods from a protocol, it is said to conform to the protocol.

### declaration ###
  * In `<objectname>`ViewController.h, declare that `<objectname>`ViewController conforms to the CLLocationManagerDelegate protocol.
```
@​i​n​t​e​r​f​a​c​e​ ​<objectname>V​i​e​w​C​o​n​t​r​o​l​l​e​r​ ​:​ ​U​I​V​i​e​w​C​o​n​t​r​o​l​l​e​r​ ​<​C​L​L​o​c​a​t​i​o​n​M​a​n​a​g​e​r​D​e​l​e​g​a​t​e​>​
```

## Responder ##
  * A responder is responsible for receiving and handling events that are associated with it