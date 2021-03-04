# pyHeat  simulates heat transfer in a 1D column of soil under steady state conditions.

__author: Nicolas Flipo__

__date: February 2021__

__repository: [https://github.com/flipoyo/pyHeat.git]__


Run the code with the main.py.

Configurates the case study with the .json files

The main class, and the only one used in the main.py, is Column.

It is possible to run multiple simulation with various parameter values (see main.py)

For sensitivity analysis it would be wise to create a class Parameter, with on top of value and unit, a range and a pdf law

## structure of the project

* all code files except main are in codepyheat

* all test files (codes) are in unittests
 
* all JSON files are in codepyheat/json, except the JSON files used by unittest that are in unittests
 
 added __init__.py to codepyheat directory, initialize the module, nice way to set provide interesting information in the module: set location for JSON files, applied in all .py files that read a JSON file. The best way for setting it up is to declare the master folder of codepyheat in the environment variable PYTHONPATH (for instance in the .bashrc in linux-based os)
 
within the codepyheat/*py files, addressing another code file with 'from codepyheat.xxx import ...'



## Testing the code

The testing procedure uses unittest.

All the test code are in unittests

until now, there is a shell runAllTest.sh for running all tests at once.

The procedure to run a test (from main directory):
```
$ python3 -m unittest unittests/testGeom.py
```

Run all tests (from main diretory)

```
$ python3 -m unittest
```

## I/O

The input files are read using the decorator @classmethod in the class FactoryClass which inherites from   metaclass=ABCMeta