# phpcommunity/github-pages Docker Image

[![Docker Automated Build](https://img.shields.io/docker/automated/phpcommunity/github-pages.svg?style=flat-square)](https://hub.docker.com/r/phpcommunity/github-pages/) [![Apache-2.0 License](https://img.shields.io/github/license/phpcommunity/docker-github-pages.svg?style=flat-square)](https://github.com/phpcommunity/docker-github-pages/blob/master/LICENSE) [![Docker Build Status](https://img.shields.io/docker/build/phpcommunity/github-pages.svg?style=flat-square)](https://hub.docker.com/r/phpcommunity/github-pages/builds/)

This is a basic Docker image for building and locally previewing [GitHub Pages](https://pages.github.com/) sites. The image is available for public use on Docker Hub at [phpcommunity/github-pages](https://hub.docker.com/r/phpcommunity/github-pages/).

## Usage

To use this image, run the following command, replacing `/path/to/jekyll/site` with the local path to the root of your GitHub Pages / Jekyll site (the directory that contains your `_config.yml` file).

``` bash
docker run -v /path/to/jekyll/site:/usr/src/app -p "4000:4000" phpcommunity/github-pages
```

Now, in a web browser, go to <http://localhost:4000> to view your site.

By default, Jekyll will watch for changes and rebuild your site for every change you save, so you can leave the container running while developing your GitHub Pages site, continuing to preview it in the browser.

## Gemfile

For best results, use the following `Gemfile` and do not commit `Gemfile.lock` to your repository:

``` ruby
source 'https://rubygems.org'
gem 'github-pages'
```

## Troubleshooting

You might run into errors similar to the following after you pull updates (`docker pull phpcommunity/github-pages`) to the phpcommunity/github-pages image:

``` bash
$ docker run --rm -v "$PWD":/usr/src/app -p "4000:4000" phpcommunity/github-pages
/usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/spec_set.rb:87:in `block in materialize': Could not find jekyll-3.4.3 in any of the sources (Bundler::GemNotFound)
	from /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/spec_set.rb:81:in `map!'
	from /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/spec_set.rb:81:in `materialize'
	from /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/definition.rb:159:in `specs'
	from /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/definition.rb:218:in `specs_for'
	from /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/definition.rb:207:in `requested_specs'
	from /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/runtime.rb:109:in `block in definition_method'
	from /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/runtime.rb:21:in `setup'
	from /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler.rb:101:in `setup'
	from /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/setup.rb:20:in `<top (required)>'
	from /usr/local/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:133:in `require'
	from /usr/local/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:133:in `rescue in require'
	from /usr/local/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:40:in `require'
	from /usr/local/bundle/bin/jekyll:15:in `<main>'
```

These errors are normal and occur because there is a conflict in your local `Gemfile.lock` lockfile with a newer version of the github-pages gem. Simply remove `Gemfile.lock` and run the `docker` command again.

## Docker Image Tags

* `latest` ➜ `v155` ([github-pages v155][])
* `v143` ([github-pages v143][])
* `v142` ([github-pages v142][])
* `v141` ([github-pages v141][])


[github-pages v155]: https://github.com/github/pages-gem/releases/tag/v155
[github-pages v143]: https://github.com/github/pages-gem/releases/tag/v143
[github-pages v142]: https://github.com/github/pages-gem/releases/tag/v142
[github-pages v141]: https://github.com/github/pages-gem/releases/tag/v141
