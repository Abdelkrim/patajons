# Testcase #

## Create an object ##

### Form Data (1) ###
  * Object name: 

&lt;nickname&gt;

:

&lt;hh:mm&gt;

:

&lt;OS&gt;

:

&lt;Browser&gt;

 (e.g. abo:11:41:MacOSX:Chrome)
  * Object description
  * Year when you bought the object
  * Shop where you bought the object
  * Price you bought the object
  * Currency
  * Rating of the object

  1. Click Next

### Form Image (2) ###

  1. Click add picture
  * 

## Give an object ##

## check the email (give) ##

## Want an object ##

## Check the email (want) ##



# Some Theory - Django Unit Tests and Fixtures #

## unit test ##

Programming Google App Engine, page 324 - Chapter 14:
  * The Django Web Application Framework Each method of a test case class whose name begins with test is a separate test.
  * For each test,
    * the runner initializes the test environment,
    * instantiates the TestCase class,
    * and calls the method for the test.
  * If the class defines a setUp() method, it calls it before each test.
  * If the class defines a tear Down() method, it calls it after each test.
  * You can use setUp() and tearDown() to create and clean up test data and preparation for every test in a test case.

  * The TestCase class provides methods that cause the test to report failure if the conditions tested are not met.
    * self.assertEqual() takes two arguments, and causes the test to fail if the arguments are not equal.
    * self.assert_() takes one argument, and fails the test if the argument is a false value (False, None, 0, the empty string, and so forth).
    * self.assertRaises() takes an exception class, a callable object, and arguments for the callable object, calls the callable, then fails the test if the callable does not raise the given exception._

## Fixtures ##

  * A fixture is a set of test data that is imported into the datastore at the beginning of a test.The easiest way to create test data is with the Django command python manage.py dumpdata


# Details #