.. _aamod-usage:

Using AAMod
===========

This page is primarily intended for website editors who are comfortable `working
with Hugo`_ websites and covers all "features" provided by ``AAMod``.

Feature Types
-------------

- `Shortcodes`_ allow website editors to add content inside of markdown files.
- `Partials`_ are similar to ``Shortcodes``, but used inside of template files.
- Layouts are "top-level templates" that link content to template.

generate_content.py
-------------------

This is a "legacy" script that should be retired (eventually):

- https://github.com/recoverysource/aamod/issues/4
- https://github.com/gohugoio/hugo/issues/5074

Report List
-----------

*Generates a list of links from a directory of files.*

**Type:** ``Shortcode``

**Usage:**

.. code-block:: golang

    Recent Reports:

    {{< reportlist path="content/treasury/area_51/" >}}

**Result:**

.. code-block:: text

    Recent Reports:

    * 2022-03.txt
    * 2022-02.txt
    * 2022-01.txt

Live Demonstration: `Input <https://raw.githubusercontent.com/recoverysource/aamod/master/exampleSite/content/treasury/area_51/index.md>`_ -> `Output <https://aamod-demo.area63aa.org/treasury/area_51/>`_

.. _working with Hugo: https://gohugo.io/getting-started/quick-start/
.. _AAMod: https://github.com/recoverysource/aamod
.. _Shortcodes: https://jpdroege.com/blog/hugo-shortcodes-partials/
.. _Partials: https://gohugo.io/templates/partials/
