---
layout: post
title:  "Welcome to Jekyll on brand new MacBook Pro (15-inch, 2016)!"
date:   2017-01-13 02:02:14 +0400
categories: jekyll update
---
Once you've got your new laptop it's time to set it up for Jekyll development as fast as you can.
Let's say you want to have a blog hosted on github.
You go to github and create new project with `<your-github-username>.github.io` name. In my case it's `palemium.github.io`.
As the next step you have to checkout your newly created project. But `git` command is not install on your fresh laptop OS.

Don't worry! If you open terminal app and enter `git` command MacOS Sierra will kindly ask you to install nessesary command line tools.
After installation completed you should finish setting up ssh keys following github guide to successfully checkout your new project using `git` command.

Now you are ready to install Jekyll. Jekyll uses ruby framework. Good news - MacOS Sierra has it already installed.
Bad news - MacOS Sierra will not allow you to install gem binaries to their default location.
You can fix this issue by specifing `~/bin` as default location for your gem binaries.
Just add `gem: --user-install -n~/bin` to `~/.gemrc`.

But also `PATH` enviroment variable should include this `~/bin`. You can add `~/bin` to `/etc/paths` at the top.

Then you can succesfully install jekyll and bunder gems: `gem install jekyll bundler`.

Then initialize new project with `jekyll new .`. This will generate also `Gemfile` with the list of gems needed for this particular project.

As next step you install gems listed in Gemfile: `bundle install --path vendor/bundle`. We use local `vendor/bundle` folder not to polute system gems namespace. Bundler will save this config information into `./bundle/config` and install gems into `vendor/bundle` folder - so let's ignore them in `.gitignore`. Also ignore vendor folder for Jekyll processing in `_config.yml`.

Now you are ready to verify that Jekyll can successfully process initially generated post: `bundle exec jekyll serve`.

Then you can go to `_posts` folder and edit your brand new post as I did!

Here we go!

