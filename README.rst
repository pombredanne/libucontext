========================
 README for libucontext
========================
:Authors:
 * **A. Wilcox**, maintainer
 * **William Pitcock**, former maintainer, initial implementation
 * **Adélie Linux and its contributors**, development
:Status:
 Production
:Copyright:
 © 2019 Adélie Linux and contributors.  MIT open source license.


.. image:: https://img.shields.io/badge/chat-on%20IRC-blue.svg
   :target: ircs://irc.interlinked.me:6697/#Adelie-Support

.. image:: https://img.shields.io/codacy/grade/3461d72e15e9467eba024e789347fa50.svg
   :target: https://app.codacy.com/project/awilfox/libucontext/dashboard

.. image:: https://img.shields.io/coverity/scan/18279.svg
   :target: https://scan.coverity.com/projects/adelielinux-libucontext

.. image:: https://img.shields.io/badge/license-MIT-lightgrey.svg
   :target: LICENSE

.. image:: https://repology.org/badge/vertical-allrepos/libucontext.svg
   :target: https://repology.org/project/libucontext/versions

.. image:: https://travis-ci.org/AdelieLinux/libucontext.svg?branch=master
   :target: https://travis-ci.org/AdelieLinux/libucontext



Introduction
============

This distribution contains the implementation of **libucontext**, a library
which provides the `\<ucontext.h>`_ API from older POSIX revisions.  Unlike
other implementations, it faithfully follows the kernel process ABI when
performing context swaps.

When combined with `gcompat`_, it provides a full implementation of the
*<ucontext.h>* functions that are ABI compatible with glibc.


.. _`\<ucontext.h>`: https://pubs.opengroup.org/onlinepubs/7908799/xsh/ucontext.h.html
.. _`gcompat`: https://code.foxkit.us/adelie/gcompat/


License
```````
This library is provided under the MIT open source license.


Changes
```````
Any changes to this repository must be reviewed before being pushed to the
master branch.  There are no exceptions to this rule.  For security-sensitive
updates, contact the Security Team at sec-bugs@adelielinux.org.



Background
==========

The ``<ucontext.h>`` functions are deprecated in POSIX, and therefore are not
implemented in the `musl libc`_.  However, these functions are still used in
some legacy packages.  They are also notably used by GCC's implementation of
the Go programming language.  Therefore, it is desireable for us to be able to
support the execution of software that utilises this deprecated API.

.. _`musl libc`: http://www.musl-libc.org/



Supported Environments
======================
The following architectures are supported:

* x86 (32-bit)

  This is a Tier 1 architecture in the Adélie Linux system, as *pmmx*.

* x86_64

  This is a Tier 1 architecture in the Adélie Linux system.

* armv6+ (as ``arm``)

  This is a Tier 2 architecture in the Adélie Linux system, as *armv6* and
  *armv7*.  As such, it may not receive thorough testing.

* aarch64

  This is a Tier 1 architecture in the Adélie Linux system.

* s390x

  This architecture is **not supported** by the Adélie Linux system.  It is
  *untested* by the release team and may not be functional.

The following architectures utilise a Linux kernel syscall:

* ppc (32-bit)

  This is a Tier 1 architecture in the Adélie Linux system.

* ppc64

  This is a Tier 1 architecture in the Adélie Linux system.  Only the ELFv2 ABI
  is supported, and only Big Endian modes of operation are tested by the
  release team.



Building
========

libucontext uses a Makefile-based build system.  The build system will attempt
to determine your current architecture using `uname -m`; you may override this
by setting the ``ARCH`` variable.

::

  $ make ARCH=ppc64
  $ make ARCH=ppc64 check
  $ make ARCH=ppc64 DESTDIR=$HOME/prefix install



Reporting Issues
================

libucontext is released by the Adélie Linux project in the hopes that it is
useful to the community.  Current issues may be found at our BTS_; you may also
`submit an issue`_ there.

For general discussion, questions, or to submit a patch, please use the
`gcompat mailing list`_.

.. _BTS: https://bts.adelielinux.org/buglist.cgi?product=libucontext&resolution=---
.. _`submit an issue`: https://bts.adelielinux.org/enter_bug.cgi?product=libucontext&component=Library
.. _`gcompat mailing list`: https://lists.adelielinux.org/postorius/lists/gcompat.lists.adelielinux.org/
