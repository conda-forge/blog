.. post:: 2020-12-22
   :tags: conda-forge
   :author: conda-forge/core

.. role:: raw-html(raw)
   :format: html

2020 in Review
==============

As 2020 winds down, the Core team thought it'd be fun to review some of the big accomplishments our community has made this year.


Strong Growth
-------------

The ``conda-forge`` community has grown immensely this year. Here are some numbers to help give you an idea of the
scale of our growth

- The community has added 3751 new, unique ``conda`` packages this year, along with a corresponding number of new feedstocks.
- For the majority of 2020, the ``conda-forge`` channel on ``anaconda.org`` exceeded 100 million downloads per month.
- In July of 2020, the ``conda-forge`` channel passed 2 billion total, all-time downloads.
- We've grown our active community, adding seven new members to the ``conda-forge`` Core team and at least two members to
  the ``staged-recipes`` team.
- We now have over 2,500 recipe maintainers in the ``conda-forge`` GitHub organization.


Big New Features
----------------

We've also shipped a ton of big updates to our core infrastructure this year. These updates include

- **pypy support**: We added support for ``PyPy`` 3.6 and now supply one of the biggest stacks of
  ``PyPy``-enabled packages in the ``PyPy`` ecosystem.
- **automerge**: We now support the automatic merging of PRs on feedstocks using the ``automerge`` label or through
  an opt-in setting in the ``conda-forge.yml``.
- **``R`` 4.0 migration**: This migration was the first one to use our ``automerge`` infrastructure at scale. With it, we
  completed a complete rebuild/upgrade of the ``R`` ecosystem in about a week.
- **Python**: We deprecated ``Python`` 2.7, completed the ``Python`` 3.8 migration, and got about 75% of the way through the
  ``Python`` 3.9 migration.
- **compiler upgrades**: We upgraded our compiler infrastructure to ``GCC`` 9 and ``clang`` 11.
- **CentOS 7 and CentOS 6 EOL**: We shipped an option to enable our compilers to use the CentOS 7 ``sysroot`` in preparation
  for the CentOS 6 EOL.
- **miniforge**: We built our own standalone, ``miniconda``-like installers. These support a broad range of platforms, including
  ``osx-arm64`` and ``linux-aarch64``.
- **standalone Windows stack**: We fully decoupled our Windows recipes from the ``defaults`` channel by rebuilding the ``msys2``
  recipes.
- **Apple silicon support**: We added support for Apple silicon with our ``osx-arm64`` platform. This platform is our first
  one to use a fully cross-compiled infrastructure.

It's been a busy year!

----

We know this year has been extremely difficult for so many of our community members. Our growth and expanded feature set
would not have been possible without the active participation and support of our community. **Thank you everyone
so much for the work you put in this year into making ``conda-forge`` the wonderful, community-led resource it is.**

We wish everyone a happy, healthy, equitable, and peaceful new year!
