# User-union

This is a clone of https://sourceforge.net/p/user-union/code/ci/master/tree/

This package contains the programs "user-union" and "run-redir-union"
as well as their documentation; see the documentation for more.
It implements union filesystems without requiring special permissions.

This is open source software, released under the MIT license.
See the file "LICENSE" for details.
It was created by David A. Wheeler.

## How to Install

If you got this from a downloaded "tarball", just unpack it, e.g.:

```
   tar xfzf user-union-0.12.tar.gz
```
If you're using a version straight from the git repository,
you need to use "autoconf" and friends to set it up (don't do this
if you got it from the tarball, it's unnecessary, and some people's
"autoconf" setup is too old):
```
autoreconf -i
```
To configure and build:
```
cd user-union*
 ./configure
 make
```
To test:
```
make test
```
 This runs "runtest", which in runs "testscript" under user-union.
 It then reports if there are any differences from the expected results.

To install those results:
```
make [DESTDIR=...] install
```

The configuration is implemented with the GNU autotools suite
(autoconf, etc.), so all the usual options are available.

It's only been tested on GNU/Linux.
However, it should work on other Unix-likes, including
the *BSDs.  I've put in some code to have it work for
Apple Mac OS X, but that's not complete.
I've put in code to get started; patches welcome.

## How to Modify

If you are modifying the program, you will probably want to edit
"user-union.c" (the underlying C library).  Other files you might want to
edit include:

* user-union.txt - the front-end shell script, source code.
* user-union - DO NOT EDIT THIS FILE, as it is generated from user-union.txt.
* user-union.1 - man page for user-union.
* run-redir-union - front-end shell script to easily redirect
* run-redir-union.1 - man page for run-redir-union
* testscript - shell script run when you invoke "make test"
  (which invokes runtest)
* fso_stat - reports statistics on the list of files given as arguments

See the NOTES file for more general background.

After modifying the program or test script, run "make test" again.
If you approve of the changes to the test results, run:
```
make accept
```

To create a tarball:
```
make tarball
```

Please submit patches!

For more information, see:
 http://www.dwheeler.com/user-union

David A. Wheeler
