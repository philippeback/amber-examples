amber-examples
==============

This project contains various [Amber Smalltalk](http://amber-lang.net/)  examples. Amber may run in a web browser or as a command line program.


Tools needed
=============

1. A web browser with reasonably good support for HTML5 canvas.
2. git, on Windows [Git for Windows](http://msysgit.github.com/)
3. [nodejs](http://www.nodejs.org/). This will give you the node package manager `npm` as well.
4. A global install of the [`amber-cli`](http://amber-lang.net/) [npm](http://npmjs.org/) package
5. A global install of the [`bower`](http://bower.io/) client side package manager in order to install the dependencies
6. A global install of the [`grunt-cli`](http://gruntjs.com/) task runner which is used as the command line build system 

The `amber`, `bower` and `grunt-cli` packages can be installed with the following command (In some cases you have to call `npm` with `sudo npm`):

    npm install --global amber-cli bower grunt-cli

or as short form:

    npm i -g amber-cli bower grunt-cli
    

Reference: http://docs.amber-lang.net/js-glossary.html


Setting up amber-examples 
==========================

Clone the repository 

    git clone https://github.com/amber-smalltalk/amber-examples.git

Get dependencies of this project:

    cd amber-examples 
    git submodule update --init --recursive
    npm install
    bower install


Amber in the browser  
==========================

Amber runs in the browser and this includes an IDE. The ``amber`` subdirectory of ``bower_components`` is used.

To have access to this start a small web server:

`amber serve`

and point your browser to

`http://localhost:4000/`


How to recompile code if needed
-------------------------------

Invoke the compiler in the Amber workspace.

e.g. Recompile the ProcessingClock example

    Compiler new recompile: ProcessingClock

Amber on the command line 
====================================================


Build or recompile a command line example  (e.g. nodejs) by executing 

`grunt`

in the subdirectory.

The subdirectories might contain additional README files which might contain additional information. Here the ``amber-dev`` subdirectory of ``node_modules`` is used.


Notes
=====

- Since Amber version 0.10.0 [`grunt`](http://gruntjs.com/) is used as commandline build system.
- For the global and local installation of the `amber-cli` and `bower` command line tools: The recommendation is to install them with the `-g` or `--global` option to be globally accessible. For some uses of these tools it is  taken it for granted they are installed globally.  So if you use a restricted environment where you  cannot install the command line tools globally, try do it locally and some tools might still work. There will be feedback messages if there are problems with this. For a local installation use your home directory or a subdirectory ~/bin of it. Run the  `npm` install commands without without the `-g` option, and you will find all the commands in the `dir_used/node_modules/.bin` subdirectory. Generally a local installation is not recommended.


Troubleshooting
===============

**SayHello example (Web) does not work**
:    check in the web console which files cannot be loaded. Does the folder ``bower_components`` contain subfolders?
     Maybe the ``bower install`` command did not run fully? Or there was a problem with ``npm install``?
     Sometimes internet connection is slow and you have to re-run these commands.
     


Status
======

- Loads fine with [Amber](https://github.com/amber-smalltalk) version 0.12.6
