# phpcommunity/github-pages Docker Image

[![Docker Automated Build](https://img.shields.io/docker/automated/phpcommunity/github-pages.svg?style=flat-square)](https://hub.docker.com/r/phpcommunity/github-pages/)
[![Apache-2.0 License](https://img.shields.io/github/license/phpcommunity/docker-github-pages.svg?style=flat-square)](https://github.com/phpcommunity/docker-github-pages/blob/master/LICENSE)
[![Docker Build Status](https://img.shields.io/docker/build/phpcommunity/github-pages.svg?style=flat-square)](https://hub.docker.com/r/phpcommunity/github-pages/builds/)

This is a basic Docker image for building and locally previewing GitHub Pages sites. The image is available for public use on Docker Hub at [phpcommunity/github-pages](https://hub.docker.com/r/phpcommunity/github-pages/).

## Usage

To use this image, run the following command, replacing `/path/to/jekyll/site` with the local path to the root of your GitHub Pages / Jekyll site (the directory that contains your `_config.yml` file).

    docker run -v /path/to/jekyll/site:/usr/src/app -p "4000:4000" phpcommunity/github-pages

Now, in a web browser, go to <http://localhost:4000> to view your site.

By default, Jekyll will watch for changes and rebuild your site for every change you save, so you can leave the container running while developing your GitHub Pages site, continuing to preview it in the browser.

## Docker Image Tags

* `latest` ➜ `v141` (github-pages v141)
