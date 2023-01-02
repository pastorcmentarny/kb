Useful commands with pip

* pip3 install -r requirements.txt

An absolute path, which always begins with the root folder
A relative path, which is relative to the program’s current working directory
A single period (“dot”) for a folder name is shorthand for “this directory.”
Two periods (“dot-dot”) means “the parent folder.”
Plaintext files contain only basic text characters and do not include font, size, or color information.
Text files with the .txt extension
or Python script files with the .py extension are examples of plaintext files.

There are three steps to reading or writing files in Python.
Call the open() function to return a File object.
Call the read() or write() method on the File object.
Close the file by calling the close() method on the File object.

Pass 'w' as the second argument to open() to open the file in write mode.
Pass 'a' as the second argument to open() to open the file in append mode.
Pass 'r' as the second argument to open() to open the file in read mode.
You can save variables in your Python programs to binary shelf files using the shelve module.
Plaintext is useful for creating files that you’ll read in a text editor such as Notepad or TextEdit,
but if you want to save data from your Python programs, use the shelve module.
Plaintext is useful for creating files that you’ll read in a text editor such as Notepad or TextEdit,
but if you want to save data from your Python programs, use the shelve module.
What is difference between copy and copytree.
The shutil.copytree() call creates a new folder named bacon_backup with the same content as the original bacon folder.
move() can’t find a folder named eggs in the
and so assumes that destination must be specifying a filename, not a folder.
So the bacon.txt text file is renamed to eggs (a text file without the .txt file extension),
probably not what you wanted! This can be a tough-to-spot bug in your programs since the move()
call can happily do something that might be quite different from what you were expecting.
This is yet another reason to be careful when using move().


Delete a single file or a single empty folder with functions in the os module,
whereas to delete a folder and all of its contents, you use the shutil module.

previous examples worked under the assumption that there was a folder eggs in the
But if there is no eggs folder, then move() will rename bacon.txt to a file named eggs.
Here, move() can’t find a folder named eggs in the directory and
so assumes that destination must be specifying a filename, not a folder.

os.unlink(path) will delete the file at path.
os.walk() function will return three values on each iteration through the loop:
1. A string of the current folder’s name
2. A list of strings of the folders in the current folder
3. A list of strings of the files in the current folder
   shutil - shutil is a shell utilities
   The shutil (or shell utilities) module has functions to let you copy, move, rename, and delete files
   in your Python programs.
   There are also the dot (.) and dot-dot (..) folders.
   These are not real folders but special names that can be used in a path.
A single period (“dot”) for a folder name is shorthand for “this directory.”
Two periods (“dot-dot”) means “the parent folder.”
os.path.abspath(path)will return a string of the absolute path of the argument.
os.path.isabs(path) will return True if the argument is an absolute path and False if it is a relative path.
os.path.relpath(path, start) will return a string of a relative path from the start path to path.
If start is not provided, the current working directory is used as the start path.
os.path.dirname(path) will return a string of everything that comes before the last slash in the path argument.
os.path.basename(path) will return a string of everything that comes after the last slash in the path argument.
If you need a path’s dir name and base name together,
you can just call os.path.split() to get a tuple value with these two strings
os.path.getsize(path) will return the size in bytes of the file in the path argument.
os.path.exists(path) will return True if the file or folder referred to in the argument exists
os.path.isfile(path) will return True if the path argument exists and is a file
os.path.isdir(path) will return True if the path argument exists and is a folder
Shelf values don’t have to be opened in read or write mode—they can do both once opened.
just like dictionaries,
shelf values have keys() and values() methods that will return list-like values of the keys and values in the shelf.
The modules that an import statement imports are themselves just Python scripts.
When the string from pprint.pformat() is saved to a .py file,
the file is a module that can be imported just like any other.
For most applications, however, saving data using the shelve module is the preferred way to save variables to a file.
"""
   They allow you to create immutable groups of objects. This means that once a tuple is created, it can’t be modified. You can’t add or remove items.


:Dictionary
And another way is using the get() method, which has an option to add a default value:
he pop() method retrieves the value of a key, and subsequently deletes the item from the dictionary

dog.popitem()
Get a list with the keys in a dictionary using the keys() method, passing its result to the list() constructor:

