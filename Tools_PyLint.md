### instalation ###

/!\ install dependencies first

included in eclipse with pydev
Download and extract : http://www.logilab.org/857

run
```
python /path/to/pylint/setup.py install
```

in eclipse go to window->prefences->pydev->pylint and check use pylint and browse to lint.py

more on : http://code.google.com/p/soc/wiki/SetUpPylint

# ID #
## Errors ##
  * E1101: read documentation of 'member' into dive into python
  * F0401: views.py: do nothing
  * E1103: session.py: do nothing
  * E0602: session.py: do nothing

## Warning ##
  * W0703: session.py: do nothing
  * W0702: session.py: do nothing
  * W0613: session.py: do nothing
  * W0612: session.py: do nothing
  * W0611: session.py: do nothing
  * W0401: views.py: do nothing, we import all models.py
  * W0232: read documentation on init (no init method)
  * W0201: read documentation on init (attribute defined outside init)

## Info ##
  * [R0915](https://code.google.com/p/patajons/source/detail?r=0915): split method
  * [R0914](https://code.google.com/p/patajons/source/detail?r=0914): decrease number of local variable
  * [R0912](https://code.google.com/p/patajons/source/detail?r=0912): descrease number of branches
  * [R0904](https://code.google.com/p/patajons/source/detail?r=0904): decrease number of public methods
  * [R0903](https://code.google.com/p/patajons/source/detail?r=0903): increase number of public methods
  * [R0201](https://code.google.com/p/patajons/source/detail?r=0201): read documentation on Methods and Functions
  * C0324: add space after a coma
  * C0323: add space after an operation
  * C0322: add space before an operation
  * C0302: decrease number of line into module
  * C0301: do nothing
  * C0111: add docstring
  * C0103: naming convention