A Github Pages template for academic websites. This was forked (then detached) by [Stuart Geiger](https://github.com/staeiou) from the [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/), which is © 2016 Michael Rose and released under the MIT License. See LICENSE.md.

See more info at https://academicpages.github.io/

# Making it yours

Now that you’ve got all the files needed to build your website on your computer, it’s time to start personalizing this generic template!

## Editing pages

All of the actual content of your site is contained in `.md` files, which are Markdown files. Most of these files live in the `_pages` directory. The [documentation](https://academicpages.github.io/markdown/) that comes with the template is relatively straightforward, and does a pretty good job telling you how to customize your site. For example, the landing page can be changed by editing the `_pages/about.md` file and the sidebar information is controlled by the `_config.yml` file. Let’s start by editing `_config.yml` to rename put our name on the site and change the sidebar to reflect our information.

I’ve copied the first several lines of `_config.yml` below:

```
# Welcome to Jekyll!
#
# This config file is meant for settings that affect your entire site, values
# which you are expected to set up once and rarely need to edit after that.
# For technical reasons, this file is *NOT* reloaded automatically when you use
# `jekyll serve`. If you change this file, please restart the server process.

# Site Settings
locale                   : "en-US"
title                    : "Your Name / Site Title"
title_separator          : "-"
name                     : &name "Your Name"
description              : &description "personal description"
url                      : https://academicpages.github.io # the base hostname & protocol for your site e.g. "https://mmistakes.github.io"
baseurl                  : "" # the subpath of your site, e.g. "/blog"
repository               : "academicpages/academicpages.github.io"
teaser                   :  # filename of teaser fallback teaser image placed in /images/, .e.g. "500x300.png"
breadcrumbs              : false # true, false (default)
words_per_minute         : 160
future                   : true
read_more                : "disabled" # if enabled, adds "Read more" links to excerpts
talkmap_link             : false #change to true to add
```

You’ll want to change the following things:

-   `"Your Name / Site Title"` to your name
-   `&name "Your Name"` to your name
-   `https://academicpages.github.io` to the name of your repository (and also your github username) i.e., `https://<yourusername>.github.io`
-   `"academicpages/academicpages.github.io"` to your GitHub username and the repo name i.e., `"<yourusername>/<yourusername>.github.io"`

When you’re finished, it should look like this:

```
# Welcome to Jekyll!
#
# This config file is meant for settings that affect your entire site, values
# which you are expected to set up once and rarely need to edit after that.
# For technical reasons, this file is *NOT* reloaded automatically when you use
# `jekyll serve`. If you change this file, please restart the server process.

# Site Settings
locale                   : "en-US"
title                    : "<Your Name>"
title_separator          : "-"
name                     : &name "<Your Name>"
description              : &description "personal description"
url                      : https://<yourusername>.github.io # the base hostname & protocol for your site e.g. "https://mmistakes.github.io"
baseurl                  : "" # the subpath of your site, e.g. "/blog"
repository               : "<yourusername>/<yourusername>.github.io"
teaser                   :  # filename of teaser fallback teaser image placed in /images/, .e.g. "500x300.png"
breadcrumbs              : false # true, false (default)
words_per_minute         : 160
future                   : true
read_more                : "disabled" # if enabled, adds "Read more" links to excerpts
talkmap_link             : false #change to true to add
```

This will put your name on the website and tell GitHub where to look for the files that make up your site. Now let’s check out our changes and make sure everything’s working like it’s supposed to!

## Previewing your website

Once we upload our modified files to GitHub (and tell GitHub to turn them into a website, which we’ll cover below), they’re out there on the internet for everyone to see. If you’re like me, you’ll make a lot of mistakes when working on your website. There’s no need to broadcast all of those mistakes to the world, and we can avoid this very easily by previewing our website locally. What this means is building the site from the various `.md` files, rendering it to HTML, and then viewing it. We can do all of that on our computer without ever having to put it online.

To preview your website locally, you’ll need to install Jekyll on your computer. The easiest way to do this is with [Bundler](https://bundler.io/). Bundler is a package manager for Ruby, which is the programming language that Jekyll is written in. This means that we need a full Ruby development environment to get Jekyll working to run our website locally. If you’re on Windows, [RubyInstaller](https://rubyinstaller.org/) will give you everything you need. If you’re on MacOS, your computer comes with Ruby, but not the development headers required for Bundler to work. If you installed Git via the Xcode Command Line tools earlier, you’re good to go here. If not, you can install Ruby Ruby via [Homebrew](https://brew.sh) with

```
brew install ruby
```

If you’re on Linux, just install Ruby via your package manager. Once that’s taken care of, it’s time to install Bundler. Do so by running

```
gem install bundler
```

in a terminal. If you’ve navigated away from the directory where your website is located (which is `~/Dropbox/Website` for me), head back there now. Do this with

```
cd ~/Dropbox/Website
```

but replace `~/Dropbox/Website` with the path to your website’s repo. Next, we need to install any packages (called ‘gems’ in Ruby) that Jekyll depends on. This is where Bundler shines by taking care of this whole process for us; it reads the `Gemfile` included with the source code and installs all required gems

```
bundle install
```

If you want to see what’s been installed, run `gem list` before and after `bundle install`. If everything worked correctly, you can now launch your website! What we’re going to do is start a webserver on your computer, which will let you access your website locally without having to put it out on the internet. We do this with

```
bundle exec jekyll serve
```

The `bundle exec` command is just a prefix that lets ruby access all of the gems specified in the `gemfile`. The `jekyll serve` command builds your website and starts a webserver so that you can view it locally. To access your website, open a browser and go to `127.0.0.1:4000` or `localhost:4000`. It should look exactly like the [example](https://academicpages.github.io/) site.

This is a special version of your site that’s only accessible from your computer; no one else can see it! So this is the perfect place to play around, experiment, and see how to make your site do what you want it to. This process is surprisingly easy. Make a change to a file e.g., editing `_pages/about.md` to introduce yourself, and save the file. That’s all you have to do; Jekyll will notice the change to the file and automatically rebuild the site. All that’s left to do is refresh your browser so you can see the changes!

## Bring back TOC
[bring back right sidebar for toc](https://github.com/PinjiaHe/PinjiaHe.github.io/commit/4d0685a37c58b7b3d08c721f22795a66cbbc1141)