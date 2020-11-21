.. post:: 2020-11-20
   :tags: conda-forge
   :author: Core

.. role:: raw-html(raw)
   :format: html


Various members of the community have raise questions publicly and privately about the implications of Anaconda's new Terms of Service (TOS) for conda-forge. First of all, we understand your concerns. We would like to explain a bit how conda-forge works and how the TOS affects us and the users, and what are our plans as a community for the future.

What makes it non-surprising is that, at the moment, any third party channel like conda-forge is free. The TOS does not apply to conda-forge, nor to other channels hosted on anaconda.org; the TOS in question applies only to the "defaults" channel and other software hosted on repo.anaconda.com.

While having alternative hosting is in our plans, we cannot afford the costs. We are just a community of volunteers. We have experimented with uploading the conda-forge artifacts to GitHub and continue to do so (see regro/releases). We also have put those artifacts behind an experimental repodata server. One of our core devs (@wolfv) is working to setup quetz with conda-forge artifacts as well.

It is very important to recognize that Anaconda Inc kindly donates use of their hosting and employee time to us and absorbs all of these costs. They host about 1.8 TB of our data and serve over 100 million downloads of artifacts from that data each month. This is a highly significant donation and conda-forge would not exist without it. Anaconda Inc employees also provide help with maintaining some of the most complex packages recipes in conda-forge.

Note that the TOS also says that part of the revenue will be donated to OSS projects. (See this blog post: https://www.anaconda.com/blog/sustaining-our-stewardship-of-the-open-source-data-science-community). You should be aware that conda-forge is a part of NumFOCUS, and so it stands to benefit from the change in TOS, as do many other OSS projects.

We absolutely welcome help from the community to move our efforts on building out more hosting infrastructure for conda-forge forward. This could be anything from spending time developing quetz to providing hosting/mirroring for our data. Please do get in contact with us if you'd like to help out!

