========================
 README for libucontext
========================
:Status:
 Superseded


.. image:: https://img.shields.io/codacy/grade/3461d72e15e9467eba024e789347fa50.svg
   :target: https://app.codacy.com/project/awilfox/libucontext/dashboard

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


Repository Superceded
=====================

This repository has been superseded.  ``libucontext`` is no longer a component
of the gcompat system, but is `maintained separately`_ at
https://github.com/kaniini/libucontext – we'll see you there!

.. _`maintained separately`: https://github.com/kaniini/libucontext
