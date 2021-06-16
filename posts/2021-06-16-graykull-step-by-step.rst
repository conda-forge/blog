.. post:: 2021-06-16
   :tags: Grayskull
   :author: ForgottenProgramme
   :redirect: 2021/06/16/grayskull-step-by-step

Contributing Packages To conda-forge Using Grayskull
====================================================

When contributing packages to conda-forge, Grayskull can make your life much easier.
Grayskull generates recipes for Python packages hosted on PyPI.

As the `introduction <https://github.com/conda-incubator/grayskull#introduction>`__ for Grayskull reads; “The main goal of this project is to generate concise recipes for conda-forge.”
In this tutorial we learn how to contribute a Python package to the conda-forge channel using Grayskull to generate the recipe.

Let us get started.

1. Install ``grayskull`` using ``conda`` through the ``conda-forge`` channel:
    ``conda install -c conda-forge grayskull``
2. Fork and clone the conda-forge `staged-recipes repository<https://github.com/conda-forge/staged-recipes>`__ from GitHub.
3. Fetch a new branch from the ``master branch``.
4. Through CLI enter inside the ‘staged-recipes’ directory.
5. Call ``grayskull`` and pass the ``pypi`` repository, followed by the name of the package you want to contribute to conda-forge. For example:
   ``grayskull pypi abc``
   Grayskull will create a folder with the same name as the package (in this case: ‘abc’) in the ‘recipes’ folder of the ‘staged-recipes’ directory.
   This folder will contain the ``meta.yaml`` file and also the license file if the package includes a license in the PyPI distribution.
6. Go through the generated ``meta.yaml`` file.
   For simpler packages, the generated recipes are nearly perfect, but for some packages you might need to make certain tweaks.
7. Commit and push the changes.
   ``git add.``
   ``git commit -m “add a commit message”``
   ``git push``
8. Create a PR. Dropping a message in the conda-forge public `Gitter channel<https://gitter.im/conda-forge/conda-forge.github.io>`__ and a link to your PR might be a good idea to get your PR reviewed and merged.

Once the PR gets merged, your package will be available on the conda-forge channel.
Tada! It’s that easy.