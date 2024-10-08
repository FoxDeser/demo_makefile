# demo_makefile
1. Basic points of make program which it can do:

- You need a file called a makefile to tell make what to do. Most often, the makefile tells make how to compile and link a program.
- To prepare to use make, you must write a file called the makefile that describes the relationships among files in your program and provides commands for updating each file.
- The make program uses the makefile data base and the last-modification times of the files to decide which of the files need to be updated.
- You can provide command line arguments to make to control which files should be recompiled.

2. Simple Makefile:

- A simple makefile consists of “rules” with the following shape:

target: prerequisites …
	recipe
…
…

which:
- target: examples of targets are executable or object files. A target can also be the name of an action to carry out, such as ‘clean’.
- prerequisite: A "prerequisite" is a file that is used as input to create the target. A target often depends on several files.
- recipe: A recipe is an action that make carries out. A recipe may have more than one command, either on the same line or each on its own line. Please note: you need to put a tab character at the beginning of every recipe line!

Notices:
- We split each long line into two lines using backslash/newline.

3. How "make" Processes a Makefile
By default, make starts with the first target (not targets whose names start with ‘.’). This is called the default goal. (Goals are the targets that make strives ultimately to update. You can override this behavior using the command line (see Arguments to Specify the Goals) or with the .DEFAULT_GOAL special variable (see Other Special Variables).

4. Variables
- Variables allow a text string to be defined once and substituted in multiple places later
- Need to refer section 6 to see more detail usage of variable in makefile
- learn to use "implicit rule" in makefile

5. What Makefiles Contain

Makefiles contain five kinds of things:
- Explicit rules: An explicit rule says when and how to remake one or more files, called the rule’s targets. It lists the other files that the targets depend on, called the prerequisites of the target, and may also give a recipe to use to create or update the targets.
- Implicit rules: An implicit rule says when and how to remake a class of files based on their names. It describes how a target may depend on a file with a name similar to the target and gives a recipe to create or update such a target.
- Variable definitions: A variable definition is a line that specifies a text string value for a variable that can be substituted into the text later.
- Directives: A directive is an instruction for make to do something special while reading the makefile. These include:
-> Reading another makefile
-> Deciding (based on the values of variables) whether to use or ignore a part of the makefile
-> Defining a variable from a verbatim string containing multiple lines
- Comments