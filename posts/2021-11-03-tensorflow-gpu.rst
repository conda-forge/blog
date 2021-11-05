.. post:: 2021-11-03
   :tags: conda-forge
   :author: wolfv

.. role:: raw-html(raw)
   :format: html

GPU enabled TensorFlow builds on conda-forge
============================================

.. image:: https://i.imgur.com/pRdJaYw.png
  :width: 400
  :alt: Tensorflow on Anvil

Recently we've been able to add gpu-enabled tensorflow builds to conda-forge! This was quite a journey, with multiple contributors trying different ways to convince the Bazel-based build system of TensorFlow to build CUDA enabled packages. But we managed, `and the pull request got merged <https://github.com/conda-forge/tensorflow-feedstock/pull/157>`_.

We now have a configuration in place that creates CUDA enabled TensorFlow builds for all conda-forge supported configurations (CUDA 10.2, 11.0, 11.1 and 11.2). Building out the cuda packages requires beefy machines – on a 32 core machine it still takes around 3 hours to build a single package. Our build matrix now includes 12 CUDA enabled packages & 3 CPU packages (because we need seperate packages per Python version). As one can imagine, this isn't easily possible on an average "home computer".

For this purpose we have written an Ansible playbook that lets us boot up cloud-machines which then build the feedstock (using the `build-locally.py` script). Thanks to the generous support of OVH we were able to boot multiple 32-core virtual machine simultanously to build the different TensorFlow variants.

We have open-sourced the `Ansible playbook in GitHub <https://github.com/mamba-org/build-locally-ansible>`_ and we're working towards making it (more) generally useful for other long-running builds!

.. image:: https://i.imgur.com/nvV6izV.jpg
  :width: 600
  :alt: Running 3 builds in parallel on 32 cores ... still takes around 3 hours to finish

With the TensorFlow builds in place, conda-forge now has CUDA enabled builds for Pytorch and Tensorflow, the two most popular deep learning libraries. 

We are still missing Windows builds for TensorFlow (CPU & CUDA, unfortunately) and would love the community to help us out with that. There is an open PR, but it probably needs some poking in Bazel to get it to pass: https://github.com/conda-forge/tensorflow-feedstock/pull/111.

We hope that these new GPU builds will enable many more packages to be added to the conda-forge channel! We are already looking forward to the 2.6.2 and 2.7 releases of TensorFlow and to adding Windows support in the future. We hope you enjoy this work.

Installation
------------

You can now select between GPU enabled (default) and CPU packages using the `tensorflow-gpu` and `tensorflow-cpu` packages. Just run

.. code-block:: bash

    mamba install tensorflow-gpu -c conda-forge
    # OR
    conda install tensorflow-gpu -c conda-forge

When installing the `tensorflow` package, the package resolution will now default to the `tensorflow-gpu` package (that will also work on CPU). If you want the slimmer "cpu-only" package, then you can install `tensorflow-cpu` directly.


Thanks to
---------

- Mark Harfouche (@hmaarrfk) & Ista Zahn (@izahn) for their initial work on the TensorFlow GPU builds, and all other TensorFlow maintainers. Uwe Korn (@xhochy) for his work on the Bazel scripts & TensorFlow -- and all the other maintainers of the `TensorFlow feedstock <https://github.com/conda-forge/tensorflow-feedstock>`_!
- NVidia for pushing cudatoolkit and cudnn on conda-forge that makes this possible
- OVH for their generous sponsoring of large build machines that we could use to build the recipes
- Bloomberg for their sponsorship of QuantStack's involvement with conda-forge
- Andreas Trawoger (@atrawog) for the Ansible scripts that this is based on
- Thorsten Beier (@derthorsten) and Adrien Delsalle (@adriendelsalle) for their contributions to the recipe