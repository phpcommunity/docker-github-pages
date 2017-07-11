# phpcommunity/github-pages Docker Image

This is a basic Docker image for building and locally previewing GitHub Pages sites.

## Usage

To use this image, run the following command, replacing `/path/to/jekyll/site` with the local path to the root of your GitHub Pages / Jekyll site (the directory that contains your `_config.yml` file).

    docker run -v /path/to/jekyll/site:/usr/src/app -p "4000:4000" phpcommunity/github-pages

Now, in a web browser, go to <http://localhost:4000> to view your site.

By default, Jekyll will watch for changes and rebuild your site for every change you save, so you can leave the container running while developing your GitHub Pages site, continuing to preview it in the browser.

## Docker Image Tags

* `latest` ➜ `v141` (github-pages v141)
