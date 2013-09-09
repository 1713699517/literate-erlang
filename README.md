<img src='https://raw.github.com/hypernumbers/literate-erlang/master/priv/images/literate-erlang.png' />

Literate Erlang
===============

A compiler for Literate Erlang - inspired by Literate CoffeeScript.

Why?
----

The purpose of this compiler is to help new users unfamiliar with Erlang to more easily understand Erlang code on GitHub by supporting a literate style.

This is intended to reduce the barriers to new users joining the community.

Implementation
--------------

The Literate Erlang, like Literate CoffeeScript is blocks of Markdown interpolated with indented blocks of Erlang. This particular dialect is aimed at GitHub-flavoured Markdown.

The Literate Erlang compiler is implemented as a ``rebar`` plugin. For more details of ``rebar`` and its role in Erlang development are available here. (FIX).

Literate Erlang files end with ``.erl.md`` and are stored in the ``/md`` directory as part of a normal Erlang/OTP file structure (FIX).

The compiler is implemented as a rebar pluging - the source code for it is in the directory ``/priv/rebar_plugins``. (HOW DO WE USE IT AS rebar dependency?)

The compiler works by transforming the Literate Erlang to plain erlang (it stashes the generated Erlang module in the ``md/.erl`` directory - and then compiling that.

Reverse Compiler
================

Why?
---

The tooling for literate Erlang is immature and will likely to remain that way for a long term. The reverse compiler enables authors of Erlang to write using their normal tools - but publish the results to the communities as Literate Erlang.

Implementation
--------------

The reverse compiler implmented as a ``rebar`` plugin called ``markup``.

This turns all files ending ``.erl`` in the ``src/`` into markdown files which are placed in an `md/` directory.

Baby Steps
==========

This is the simplest possible implementation of a Literate Erlang compiler designed to establish the idea and **get it working on GitHub**. There are plenty of ways it could be improved.

* It has bugs - for instance (at the moment) you can't embed blocks of other code in the Erlang file (an example would be a javascript example in a module that parses JSON).
* it has no tooling - no SublimeText plugins or Emacs major modes - they would be nice
* it has no native Erlang markup compiler to turn it into html. There is an Erlang Markdown compiler (REF) which could be used to do that. It currently supports normal Markdown and not GitHub-flavoured markdown (or Markup, whatever happened to that?).

The markdown emacs mode results in code that looks like this:
<img src='https://raw.github.com/hypernumbers/literate-erlang/master/priv/images/emacs-tooling-literate-erlang.png' />

Sublime Text has a markdown mode which allows you to preview your markdown in a brower:
<img src='https://raw.github.com/hypernumbers/literate-erlang/master/priv/images/sublime-text-3-python-preview.png' />

Users on Windows/Macs can have this preview rendered by GitHub for a higher level of fidelity.

Contributing
------------

Contributing is easy, fork and fire away.

All contributors whose patches are accepted will receive one of these handsome T-shirts.