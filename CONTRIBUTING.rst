====================================
 Contribution Guide for libucontext
====================================
:Author:
  * **A. Wilcox**, documentation writer
:Copyright:
  © 2019 Adélie Linux.  MIT open source licence.




Contributing Changes
====================

This section describes the usual flows of contribution to this repository.


GitLab Pull Requests
````````````````````

#. If you do not already have a GitLab account, you must create one.

#. Create a *fork* of the libucontext repository.  For more information,
   consult the GitLab online documentation.

#. Clone your forked repository to your computer.

#. Make your changes.

#. Test your changes to ensure they are correct.

#. Add (or remove) changed files using ``git add`` and ``git rm``.

#. Commit your changes to the tree using the command ``git commit`` and
   ``git push``.

#. Visit your forked repository in a Web browser.

#. Choose the *Create Pull Request* button.

#. Review your changes to ensure they are correct, and then submit the form.


Mailing List
````````````

#. Clone the packages repository to your computer.

#. Make your changes.

#. Test your changes to ensure they are correct.

#. Add (or remove) changed files using ``git add`` and ``git rm``.

#. Commit your changes to the tree using the command ``git commit``.

#. Use the command ``git format-patch HEAD^`` to create a patch file for your
   commit.

   .. note:: If you have made multiple commits to the tree, you will need to
             add an additional ^ for each commit you have made.  For example,
             if you have made three commits, you will use the command
             ``git format-patch HEAD^^^``.

#. Email the resulting patch to the `gcompat mailing list`_.

.. _`gcompat mailing list`: https://lists.adelielinux.org/postorius/lists/gcompat.lists.adelielinux.org/

