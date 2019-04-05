This is a dirty POC that allows you to call every function of a python file
directly from the shell.

It's a bit like a python-shell bridge.

Example
-------

```
$ cat example.py
def one_function():
    print("I've been called!")


def with_arguments(x, y=2):
    print(f"x: {x}, y: {y}")


# won't be exposed for now
class MyClass:
    pass

$ ./py2sh example.py 
usage: py2sh [-h] {one-function,with-arguments} ...

$ ./py2sh example.py one-function 
I've been called!

$ ./py2sh example.py with-arguments this-is-x -y 42
x: this-is-x, y: 42
```

Installation (python3)
----------------------

It's written for python3 for now.

```
pip install git+https://github.com/psycojoker/py2sh
```
