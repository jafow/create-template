A sample project demonstrating a trailing ; Syntax error in
[requirejs/requirejs#178](https://github.com/requirejs/requirejs/issues/178)

In Node **v6.5.0** with `requirejs` installed globally, running this:

    r.js -o tools/build_with_semis.js


throws this error:

    Error: Build file /Users/path/to/create-template/tools/build_with_semis.js
    is malformed: SyntaxError: Unexpected token ; at Function.build.createConfig
    (/Users/<my_user>/.nvm/versions/node/v6.5.0/lib/node_modules/requirejs/bin/r.js:14784:23)


Running the same command in Node **v4.5.0** builds as expected.

<hr>
This web project has the following setup:

* www/ - the web assets for the project
    * index.html - the entry point into the app.
    * app.js - the top-level config script used by index.html
    * app/ - the directory to store project-specific scripts.
    * lib/ - the directory to hold third party scripts.
* tools/ - the build tools to optimize the project.

To optimize, run:

    node tools/r.js -o tools/build.js

That build command creates an optimized version of the project in a
**www-built** directory. The app.js file will be optimized to include
all of its dependencies.

For more information on the optimizer:
http://requirejs.org/docs/optimization.html

For more information on using requirejs:
http://requirejs.org/docs/api.html
