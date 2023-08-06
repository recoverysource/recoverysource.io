.. _aamod-newsite:

New Website
===========

These instructions are focused on deploying a `hugo-website`_ template and
hosting it on GitHub infrastructure. The process will be very similar for
different service providers.

Note: Documentation explaining how to :ref:`Update a Website <aamod-update>`
includes many images and is provided in a separate document.

Basic Steps
~~~~~~~~~~~

Follow these steps to deploy a brand new regional AA website:

0. Register a domain with one of the `common registrars`_

   - A good rule of thumb is to avoid any service that offers to build your website (i.e. BlueHost)

1. Create an account and log in to Github
2. Create a new free organization

   - GH Pages is restricted to one site per user/org)
   - You can alternatively register with a shared account (i.e. areaXweb) and skip this step

3. Set up DNS:
::

    A     @     185.199.108.153
                185.199.109.153
                185.199.110.153
                185.199.111.153
    AAAA  @     2606:50c0:8000::153
                2606:50c0:8001::153
                2606:50c0:8002::153
                2606:50c0:8003::153
    CNAME www   <username|project>.github.io.

4. Make a copy of `hugo-website`_, giving it a meaningful name and description

   - Choose ``Fork`` if you would like us to watch ``aamod`` for you (easier).
   - Choose ``Use this template`` to create a copy without the link (safer).

5. Go to the "Actions" tab in your new repository and enable workflows
6. Copy any example content (without ``example-``) and update as appropriate:

   - ``example-config.yaml`` (live `sample config`_)
   - ``content/example-contact.md``

7. Update ``static/CNAME`` with the domain you registered (step 0)
8. Update local meeting information in ``data/meetings.yaml``

   - This can optionally be broken into one meeting per file (see `Area 63 Meetings`_)

9. Wait for a successful build and deploy of your website
10. Open the ``Settings`` page of your repository then go to ``Pages`` and set ``Source`` to ``Branch[gh-pages]``
11. Wait for DNS to propagate and verify DNS check in ``Settings>Pages`` passes before checking ``Enforce HTTPS``
12. Introduce the website to your local groups!

Interactive Maps
~~~~~~~~~~~~~~~~

In order to display an interactive map along with meeting lists, a Google Maps
API Key is required. Google provides documentation to
`obtain this API Key <https://developers.google.com/maps/documentation/embed/get-api-key>`.

The two settings that matter are:

- Application restrictions: ``*<your-domain>/*`` (e.g. ``area63aa.org/*``)
- API restrictions: ``Maps Embed API``, ``Maps JavaScript API``, ``Places API``

Meeting Guide App
~~~~~~~~~~~~~~~~~

AAMod produces a JSON file that can be used by the `Meeting Guide`_ phone application.

This file will be available at: https://yourdomain.tld/meeting-times.json

Connecting your meeting information to this application requires filling out a
``connection form``_. Where it asks for ``Site Sharing Key``, the web address of
``meeting-times.json`` should be provided.

Security Updates
----------------

Most website vulnerabilities are around user authentication and authorization.
They attempt to find ways to act like an admin or bypass an admin check or
convince someone to share their password. Truly static websites do not suffer
these problems because there is no dynamic component to be exploited. You cannot
exploit that which is not present! (user authentication, file uploads, page
edits, etc.)

In other words ... there is nothing for you to be concerned about. A security
update for this project is currently inconceivable.

..
  _links
.. _common registrars: https://domains.google/
.. _hugo-website: https://github.com/recoverysource/hugo-website
.. _sample config: https://github.com/area63aa/area63aa.org/blob/master/config.yaml
.. _Area 63 Meetings: https://github.com/area63aa/area63aa.org/tree/master/data/meetings
.. _Meeting Guide: https://www.aa.org/meeting-guide-app
.. _connection form: https://meetingguide.helpdocs.io/article/jsydw3bxw8-connection-form
