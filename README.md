# gooey-dist

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
This will parse, interpret, and run all text currently in the run queue.
#### `gooey.read_lazy(input)`
Pass in a string of Gooey text to be run after initial inital definitions have been processed. (Will be parsed and run automatically. Primarily for user-defined functions). This should **never** be called from within the root scope. This function requires there to be an existing Gooey instance.
#### `gooey.register_function(f)`
Pass in a python function to be stored in the current Gooey interpretering instance.




## Gooey Syntax
http://gooey.readthedocs.org/en/latest/

## Example
```
from gooeydist import gooey

def set_window_color():
	gooey.read_lazy("set w color blue.")
	
def action_2():
	gooey.read_lazy('set b text "bye".')
	
gooey.register_function(set_window_color)
gooey.register_function(action_2)

gooey.read("input.txt")
gooey.read("make Button m with position center, action action_2.")

gooey.run()
```

## Notes

	






