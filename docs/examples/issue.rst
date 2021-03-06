Issue Code Examples
===================

Examples using ``Issue``\ s

Administrating Issues
---------------------

Let's assume you have your username and password stored in ``user`` and ``pw``
respectively, you have your repository name stored in ``repo``, and the number
of the issue you're concerned with in ``num``.

::

    from github3 import login

    gh = login(user, pw)
    issue = gh.issue(user, repo, num)
    if issue.is_closed():
        issue.reopen()

    issue.edit('New issue title', issue.body + '\n------\n**Update:** Text to append')

::

    # Assuming issue is the same as above ...
    issue.create_comment('This should be fixed in 6d4oe5. Closing as fixed.')
    issue.close()

The following shows how you could use github3.py to fetch and display your
issues in your own style and in your webbrowser.

.. include:: source/browser.py
    :code: python

Or how to do the same by wrapping the lines in your terminal.

.. include:: source/wrap_text.py
    :code: python
