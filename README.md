Tern for CoffeeScript plugins
=============================

Use a work around way to let tern.js play with CoffeeScript.

Requirement
-----------

Tern.js 0.6 and node environment.

Installation
------------

Use npm to install this plugin in tern's directory.

    npm install tern-coffee

For example, vim user:

    cd ~/.vim/bundle/tern_for_vim
    npm install tern-coffee

Then you must let your editor enable tern for CoffeeScript files. Vim user
can install [tern_for_vim_coffee][2]. This is very simple plugin. You must install
both **tern_for_vim** and **tern_for_vim_coffee**

Last part is [.tern-project][3] file. It's required to use a plugin. Remember 
to add `coffee` to plugin list.

[2]:https://github.com/othree/tern_for_vim_coffee
[3]:http://ternjs.net/doc/manual.html#configuration

How
---

Marijn [describes][1] how difficult to let tern support a new language. CoffeeScript only have source map support. There is no error tolerance CoffeeScript compiler available. So this is not a perfect solution.

The walk around solution is try to fix the editing CoffeeScript file before compile to JavaScript. Ex:

    obj.

Will change to

    obj.__fake__

Before compile. There are more fix rules. Not perfect but should ok for normal editing.

The base of source mapping logic is by [mntmn][4].

[1]:https://groups.google.com/d/msg/tern-dev/EQo8zJy4rXM/LCG7p1K3yg0J
[4]:https://github.com/mntmn/tern-coffeescript/blob/master/cs/coffee-reverse.js
