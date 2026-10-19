# Contributing to Full Python family of projects

## Style

Our code style is loosely based on PEP-8 which differs on several aspects:
  - we use tabs, no X number of spaces
  - no max line length, formatting shouldn't be written on the code, use your editor's soft-wrapping instead.
  - Never EVER split a function signature in different lines. Same goes for calls: if a call is so complex and dynamic that requires such format, you should then build a parameter list/dict first (which is fair game for the line splitting thing) and use unpacking for the call. Same applies to return instructions. There's a single exception: defining "constants" or initial values in a class (on the class definition, not in `__new__` or `__init__`).
  - Don't hide defaults for "single type" parameters. The type `None` should only be used as a default in the case that is treated differently than the empty value (`""`, `[]`, `{}`, etc). Keep in mind that for mutable types you should never modify them in place unless you know what you're doing (create a copy first, if you need to act on them).
  - Avoid full module imports: use targeted imports instead; Ex: `from logging import getLogger` instead of `import logging`. Arrange the imports in sections, each section separated by a blank line, each section sorted by module name (num<alpha, .<alphanum):
```
 standard library imports

 1a. framework modules (applicable for Django, Flask, FastAPI, etc)

 3rd party modules (PYPI & Co)

 local modules
 ```
  - Spaces around the equal sign are expected on an assignment line. Parameter definitions and argument definitions shouldn't have them. Each parameter/argument (including the default values or argument values) should be easily identifiable by the use of spaces.
  - We use Sphinx reST docstrings that should be written EVERYWHERE it is possible. Docstrings should use double quotes (opposed to single quotes).
  - We don't use annotations. The way to do type hinting would be through the docstrings.