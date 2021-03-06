# java9-repl
Discovering the REPL features for the Java Guild

## What does this new feature do?
Introduces a _Read Eval Print Loop_ with the `jshell` command, runnable from your favorite shell.

A _REPL_ is usually considered to be on the same _level_ as _TDD_: as a learning and experimentation instrument.


## What are the advantages and disadvantages?
### Advantages
* It provides a helpful `/help` command, allowing one to learn _on demand_ about all of the features `jshell` offers.
* Instead of debugging, get quick feedback on small pieces of code.
* No need to deal with _Checked Exceptions_.
* Excellent tool for beginners to start learning immediately without having to install IDE's, dependency management tools, etc. Then again, we don't recommend using it without an IDE.
* Statements in the `jshell` get tagged with _id's_, allowing statements to be recalled on demand.
* IntelliJ has support for an embedded REPL, with all of the features (compile errors, auto-completion, templates, using module classpath, ...).

### Disadvantages
* Java, the language, doesn't exactly lend itself for small snippets, because of its verbosity.
* Usually experiments for small bits of code are done in Unit Tests, providing a consistent, rerunnable history of _experiments_ that document how our code works.
* There is no auto-indentation in `jshell`.
* When a statement is performed in `jshell` that has syntax errors, **sometimes** some of your state gets lost.
* Unable to dynamically extend your classpath (e.g. adding external libraries on the fly). You'll need to restart your `jshell` for that.

## Do you like the feature?
Not recommended without using IntelliJ.


## Will you use it on your project?
Naah. 

Maybe using IntelliJ snippets it might be handy to quickly test a library/framework.

Maybe also a good tool for teachers to show to their students how code works and what the output of certain code snippets is.

## What are the reasons you won’t be using it?
Most developers will tend to use IntelliJ's 'evaluate expression' if one quickly wants to see the result of some statement.

Because you need Java 9 and our projects aren't yet on Java 9.


## /help
```
jshell> /help
|  Type a Java language expression, statement, or declaration.
|  Or type one of the following commands:
|  /list [<name or id>|-all|-start]
|  	list the source you have typed
|  /edit <name or id>
|  	edit a source entry referenced by name or id
|  /drop <name or id>
|  	delete a source entry referenced by name or id
|  /save [-all|-history|-start] <file>
|  	Save snippet source to a file.
|  /open <file>
|  	open a file as source input
|  /vars [<name or id>|-all|-start]
|  	list the declared variables and their values
|  /methods [<name or id>|-all|-start]
|  	list the declared methods and their signatures
|  /types [<name or id>|-all|-start]
|  	list the declared types
|  /imports
|  	list the imported items
|  /exit
|  	exit jshell
|  /env [-class-path <path>] [-module-path <path>] [-add-modules <modules>] ...
|  	view or change the evaluation context
|  /reset [-class-path <path>] [-module-path <path>] [-add-modules <modules>]...
|  	reset jshell
|  /reload [-restore] [-quiet] [-class-path <path>] [-module-path <path>]...
|  	reset and replay relevant history -- current or previous (-restore)
|  /history
|  	history of what you have typed
|  /help [<command>|<subject>]
|  	get information about jshell
|  /set editor|start|feedback|mode|prompt|truncation|format ...
|  	set jshell configuration information
|  /? [<command>|<subject>]
|  	get information about jshell
|  /!
|  	re-run last snippet
|  /<id>
|  	re-run snippet by id
|  /-<n>
|  	re-run n-th previous snippet
|
|  For more information type '/help' followed by the name of a
|  command or a subject.
|  For example '/help /list' or '/help intro'.
|
|  Subjects:
|
|  intro
|  	an introduction to the jshell tool
|  shortcuts
|  	a description of keystrokes for snippet and command completion,
|  	information access, and automatic code generation
|  context
|  	the evaluation context options for /env /reload and /reset
```