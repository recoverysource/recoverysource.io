.. _aamod-update:

Update Website
==============

This document explains how a user can log in and create a new event or update a
meeting time. This is intended for users who have never worked with Github and
assumes a :ref:`aamod-newsite` has already been created.


Register an Account
-------------------

In order to be granted access to make any changes, you must create an account.

1. Open https://github.com and click ``Sign up``:

   |github_homepage|

2. Provide basic account information:

   |github_create|

3. Check email and provide the temporary token:

   |github_token|

4. Either provide demographic information or click ``Skip personalization``:

   |github_demographics|

At this point, your account has been created and is ready for use.

You can now contact anyone in charge of the website you would like to help with
and provide your account name with a request for access.

Pull Requests
-------------

If you have not been provided access to a project and attempt to make changes on
a website, Github will automatically create a `Fork`_. This simply means your
account now owns a copy of the project, which means you are free to make any
changes to your copy.

After making changes to this copy, you can create a `Pull Request`_, which just
means you would like the main project to "absorb" your changes. Github provides
a web interface for this which is documented on their website.

Responsibility
--------------

After a project (website) administrator has given you access to their ``Team``,
you will likely be able to make changes directly to the website repository.

**NOTICE:** Most websites will automatically "build and deploy" (or "publish
the changes") with all file changes. Various safeguards exist to prevent
impacting a live/production website--the best safeguard is small/trivial updates
that can be easily explained (in the commit title/description).

**REMEMBER:** We may make mistakes, but we will promptly admit when we become
aware of mistakes we have made. We will recognize the earnest effort of others
and guide them through mistakes. Open communication will enable us to reach the
newcomer.

The :ref:`Code of Conduct <code-of-conduct>` used by this project is offered as
a basic template that aims to embody A.A. principles, including respect for
others and anonymity.

To accept this responsibility ...

1. Open https://github.com, select your user icon, and select ``Your Organizations``:

   |github_menu_org|

2. Select ``Join`` next to the organization/team you have been invited to:

   |github_org_list|

3. Read through the disclaimer and choose the appropriate option.

Create an Event
---------------

To create an event:

1. Navigate to your project:

   |repo_front|

2. Select ``content``, then ``events``:

   |repo_content|

3. The easiest way to proceed is to copy/paste an existing or example document:

   |repo_events|

4. Select the chosen source document and click the ``Display the source blob`` button:

   |repo_examplefile|

5. Highlight the document and "copy". If this is challenging, the ``Raw`` button
   will provide a "plain text" version that is easier to use.

   |repo_exampleraw|

6. Back in the ``events`` directory, choose ``Add file > Create new file``:

   |repo_newfile|

7. Paste the starting file contents into the large box and provide a filename
   above.

.. note:: This filename should NOT include spaces, keep it simple with numbers,
   lowercase letters, hyphens, and underscores. The filename *MUST* end with
   ``.md``.

   |repo_newfile|

8. Update the content as appropriate and provide a short explanation of the
   change that is being made:

   |repo_editfile|

9. After clicking the ``commit`` button, you can click ``Actions`` to observe
   the website update "build" process:

   |actions_home|

10. Once complete, green checkmarks will be displayed:

   |actions_succeess|

11. Your changes will now be available for the world to view:

   |site_event|

Update a Meeting
----------------

The process to update meetings is very similar to the process required to
``Create an Event``. Meeting information is stored in the ``data`` folder, which
can either have a single ``meetings.yaml`` file, or a directory named
``meetings/`` with any number of ``____.yaml`` files within, each one
representing a meeting.

**Geo Coords:** Although the ``longitude`` and ``latitude`` fields are not
required, adding them significantly increases the build time and accuracy of
your website. If you locate the correct address in Google Maps, you can "right
click" the "red pin" and then click the coordinates provided to "copy" them into
your clipboard.

**Address:** When presented with a poorly-formatted or incomplete address
without geo coordinates provided, a best-effort guess will be made as to what
the correct address is. More accurate addresses will produce more accurate
results.

**Spaces:** These `yaml`_ files are a special format that functions very similar
to a serverless database. Spaces (**NOT TABS**) and colons are very important.

..
  _links
.. _Fork: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks
.. _Pull Request: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests
.. _yaml: https://www.redhat.com/en/topics/automation/what-is-yaml

..
  _images
.. |github_homepage| image:: /static/images/updatesite/1_github_homepage.png
.. |github_create| image:: /static/images/updatesite/2_github_create.png
.. |github_token| image:: /static/images/updatesite/3_github_token.png
.. |github_demographics| image:: /static/images/updatesite/4_github_demographics.png
.. |github_menu_org| image:: /static/images/updatesite/5_github_menu_org.png
.. |github_org_list| image:: /static/images/updatesite/6_github_org_list.png
.. |repo_front| image:: /static/images/updatesite/7_repo_front.png
.. |repo_content| image:: /static/images/updatesite/8_repo_content.png
.. |repo_events| image:: /static/images/updatesite/9_repo_events.png
.. |repo_examplefile| image:: /static/images/updatesite/10_repo_examplefile.png
.. |repo_exampleraw| image:: /static/images/updatesite/11_repo_exampleraw.png
.. |repo_newfile| image:: /static/images/updatesite/12_repo_newfile.png
.. |repo_newfilename| image:: /static/images/updatesite/13_repo_newfilename.png
.. |repo_editfile| image:: /static/images/updatesite/14_repo_editfile.png
.. |actions_home| image:: /static/images/updatesite/15_actions_home.png
.. |actions_succeess| image:: /static/images/updatesite/16_actions_succeess.png
.. |site_event| image:: /static/images/updatesite/17_site_event.png
