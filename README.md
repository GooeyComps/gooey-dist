# gooey-dist
Inject Gooey directly into your existing Python code.
## Installing
This module has dependencies that require Python 3.
```
pip install gooeydist
```

## Usage
```
from gooeydist import gooey
```
```
gooey.read("input.txt")
```
```
gooey.run()
```

## Public Functions
#### `gooey.read(input)`
Pass in either a string of Gooey text or the name of the file where your Gooey definitions are located. This text will be added to the run queue.
#### `gooey.run()`
This will parse, interpret, and run all text currently in the run queue. Will not return until Tkinter window quits.
#### `gooey.update(input)`
Pass in a string of Gooey text to be run after initial definitions have been processed. Will return once definitions have been executed.
#### `gooey.register_function(f)`
Pass in a Python function to be stored in the current Gooey interpreting instance.
#### `gooey.get(varname)`
Pass in a Gooey variable name. Will return the Tkinter widget that was assigned to `varname` during the initial run() cycle.




## Gooey Syntax
http://gooey.readthedocs.org/en/latest/

## Example
```
from gooeydist import gooey

def foo():
	gooey.update("set w color blue.")
	button_b = gooey.get("button1")
	button_b.configure(text="Hello")
	
def foo2():
	gooey.update('set button1 text "Goodbye".')
	
gooey.register_function(foo)
gooey.register_function(foo2)

gooey.read("input.txt")
gooey.read("make Button button2 with position center, action foo2.")

gooey.run()
```

## Notes

	
