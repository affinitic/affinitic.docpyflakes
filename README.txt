Introduction
============

Check your doctest for various errors. Depends on pyflakes (http://pypi.python.org/pypi/pyflakes).

VIM
===

My vim configuration integration to run docpyflakes while I am working on my doctest and handle errors quickly::

    fun! PyflakesForDocTest()
        let tmpfile = tempname()
        execute "w" tmpfile
        execute "set makeprg=(docpyflakes\\ " . tmpfile . "\\\\\\|sed\\ s@" . tmpfile ."@%@)"
        make
        cw
        redraw!
    endfun

EMACS
=====

Learn VIM
