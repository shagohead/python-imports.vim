TODO
--------
- fix line placement (sometimes it inserts line in wrong tab page with wrong opened buffer)
- replace Ale calling with optional callbacks (that can runs isort, black, coc commands...)

Overview
--------
Vim script to help adding import statements in Python modules.

You need to have a tags file built (``:!ctags -R .``, be sure to use
`exuberant-ctags <http://ctags.sourceforge.net/>`_ or `Universal
Ctags <https://ctags.io/>`_). You can use `Gutentags
<https://github.com/ludovicchabant/vim-gutentags>`__ plugin for
automatic tags management.

Type ``:ImportName [<name>]`` to add an import statement at the top of the file.

Type ``:ImportNameHere [<name>]`` to add an import statement above the current
line.

I use the following mappings to import the name under cursor with a single
keystroke::

  map <F5>    :ImportName<CR>
  map <C-F5>  :ImportNameHere<CR>

Needs Vim 7.0, preferably built with Python support.

Tested on Linux only.


Installation
------------

I recommend `Vundle <https://github.com/gmarik/vundle>`_, `pathogen
<https://github.com/tpope/vim-pathogen>`_ or `Vim Addon Manager
<https://github.com/MarcWeber/vim-addon-manager>`_.  E.g. with Vundle do ::

  :BundleInstall "mgedmin/python-imports.vim"

Manual installation: copy ``plugin/python-imports.vim`` to ``~/.vim/plugin/``.


Configuration
-------------

In addition to the ``tags`` file (and builtin logic for recognizing standard
library modules), you can define your favourite imports in a file called
``~/.vim/python-imports.cfg``.  That file should contain Python import
statements like ::

    import module1, module2
    from package.module import name1, name2

Continuation lines are not supported.  Parenthesized name lists are partially
supported, if you use one name per line, i.e. ::

    from package.module import (
        name1,
        name2,
    )


Copyright
---------

``python-imports.vim`` was written by Marius Gedminas <marius@gedmin.as>.
Licence: MIT.
