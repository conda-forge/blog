# the conda-forge blog
[![deploy](https://github.com/conda-forge/blog/workflows/deploy/badge.svg)](https://github.com/conda-forge/blog/actions?query=workflow%3Adeploy)

## How to Add a Blog Post

We are using the `ablog` sphinx extension to build our blog. See the docs here: https://ablog.readthedocs.io/.

To add your post, make a PR following these guidelines:

- Please put your posts in the `posts` directory.
- You will need to have the `.. post::` slug with details at the top. See the `ablog` docs for details.
- Write your post in ReST.
- If you need to, add your name to the authors list in `conf.py`.
- Examine your post locally by installing the packages in the `requirements.txt`
  file. Then run the following

  ```bash
  make clean
  ablog build
  ablog serve
  ```
  
  Note that `ablog` will not work without the exact env in the `requirements.txt` file.
  
When your PR is merged, the built site will be pushed to the `gh-pages`
branch.
