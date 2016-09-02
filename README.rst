
=========================
Pygments TypoScript Lexer
=========================

This is the Pygments lexer used for syntax checking
and code highlighting of TYPO3 TypoScript code.

The purpose of this repository is to have a safe place
where the lexer can be copied from when setting up servers.

**Use the file** in `bitbucket-org-birkenfeld-pygments-main/typoscript.py`
for setting up servers.

:Author:          Michiel Roos <michiel.roos@typo3.org>
:Available from:  An official version comes `bundled with Pygments <https://bitbucket.org/birkenfeld/pygments-main/>`__
:Compare with:    https://github.com/Tuurlijk/Pygments-TypoScript-Lexer

The version(s) in this repository may contain bugfixes
or further developments that have not yet found their way
into the official releases.


Installation
============

Hopefully the TypoScript lexer is shipped with the official Pygments installation.
If not, you can copy it from here and follow this instruction.
Install Pygments first. Afterwards:

.. highlight:: shell

1. Pick the file `bitbucket-org-birkenfeld-pygments-main/typoscript.py`

2. You may need 'sudo' rights for the following.

3. Find out, where the Python module *Pygments* is installed on your machine::

      # run Python, import Pygments, print file location, exit
      python -c "import pygments; print pygments.__file__"

      # for example this line will be shown:
      /usr/lib/python2.7/dist-packages/pygments/__init__.pyc

   This means that in our case *Pygments* resides in
   `/usr/lib/python2.7/dist-packages/pygments/`.

4. Copy the TypoScript lexer `typoscript.py` into the `lexers/` folder,
   for example into `/usr/lib/python2.7/dist-packages/pygments/lexers/`.

5. Go to that directory::

      cd  /usr/lib/python2.7/dist-packages/pygments/lexers/

6. Update the mapping of known lexers. By running `_mapping.py`.
   It will create a new and updated version of itself::

      cd /usr/lib/python2.7/dist-packages/pygments/lexers/
      (sudo) python _mapping.py

7. **Done!**

8. *Verify:*

       pygmentize -L

   you should see *typoscript* somewhere in the list.

It may be necessary to repeat this procedure if new versions of *Pygments*
are being installed. This may happen indirectly for example when you
upgrade some other package like Sphinx (`sudo pip install --upgrade sphinx`).
