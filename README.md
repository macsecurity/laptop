# Laptop

[![Build Status](https://travis-ci.org/monfresh/laptop.svg)](https://travis-ci.org/monfresh/laptop)

Laptop is a script that will set up a complete Ruby web development environment on your Mac, including Node, Postgres, Rails, and Jekyll. You also have the option to skip those web dev tools and only install the minimum required to use Ruby.

You can safely run it over and over on the same computer. And because it only installs what's not already there, it runs quickly once everything is installed. The best part is that it will automatically upgrade tools if it finds a newer version.

That's why I recommend running the script about once a week, which is what I do to keep my development environment up to date and secure.

## Table of Contents

<!-- MarkdownTOC autolink="true" -->

- [More goodies](#more-goodies)
- [What's supported](#whats-supported)
- [What it sets up](#what-it-sets-up)
- [Install](#install)
    - [Check prerequisites](#check-prerequisites)
    - [If you are on an M1 Mac, do not use Rosetta](#if-you-are-on-an-m1-mac-do-not-use-rosetta)
    - [Quit and relaunch Terminal after running my script](#quit-and-relaunch-terminal-after-running-my-script)
    - [Now on to the installation](#now-on-to-the-installation)
        - [The recommended default installation for most people](#the-recommended-default-installation-for-most-people)
        - [The minimal installation for those that only want Ruby and nothing else](#the-minimal-installation-for-those-that-only-want-ruby-and-nothing-else)
- [Debugging script failures](#debugging-script-failures)
- [How to tell if the script worked](#how-to-tell-if-the-script-worked)
- [How to switch between Ruby versions and install different versions](#how-to-switch-between-ruby-versions-and-install-different-versions)
- [Check the Node installation](#check-the-node-installation)
- [Why chruby and not RVM, rbenv, or asdf?](#why-chruby-and-not-rvm-rbenv-or-asdf)

<!-- /MarkdownTOC -->

## More goodies

- Join the 2800+ readers of my [newsletter](https://www.moncefbelyamani.com/newsletter?utm_source=laptop-repo) who are learning something new in every issue. I write actionable guides about coding, and my favorite **mental models, books, tools, and life hacks** that I use to improve continuously. I focus on topics such as **automation, productivity, behavorial science, writing, and marketing**.

## What's supported

Supported chips:

- Apple Silicon M1
- Intel

Supported macOS versions:

- Monterey
- Big Sur
- Catalina

Unsupported operating systems. Give it a shot, but I can't guarantee it will work.

- macOS Mojave (10.14)
- macOS High Sierra (10.13)
- macOS Sierra (10.12)
- OS X El Capitan (10.11)
- OS X Yosemite (10.10)
- OS X Mavericks (10.9)

Supported shells:

- bash
- zsh

## What it sets up

- [Bundler] for managing Ruby gems
- [chruby] for managing [Ruby] versions (recommended over RVM and rbenv)
- [GitHub CLI] brings GitHub to your terminal.
- [Heroku Toolbelt] for deploying and managing Heroku apps
- [Homebrew] for managing operating system libraries
- [Homebrew Cask] for quickly installing Mac apps from the command line
- [Homebrew Services] so you can easily stop, start, and restart services
- [Jekyll] for creating static sites
- [Nodenv] to easily install and manage Node versions
- [Rails] for creating modern web apps
- [Postgres] for storing relational data
- [ruby-install] for installing different versions of Ruby
- [Yarn] to manage JS dependencies

[bundler]: http://bundler.io/
[chruby]: https://github.com/postmodern/chruby
[github cli]: https://cli.github.com
[heroku toolbelt]: https://toolbelt.heroku.com/
[homebrew]: http://brew.sh/
[homebrew cask]: http://caskroom.io/
[homebrew services]: https://github.com/Homebrew/homebrew-services
[jekyll]: https://jekyllrb.com
[Nodenv]: https://github.com/nodenv/nodenv
[postgres]: http://www.postgresql.org/
[rails]: https://rubyonrails.org
[ruby]: https://www.ruby-lang.org/en/
[ruby-install]: https://github.com/postmodern/ruby-install
[yarn]: https://yarnpkg.com

## Install

**IMPORTANT! CHECK ALL OF THE ITEMS BELOW BEFORE AND AFTER RUNNING THE SCRIPT!** 

### Check prerequisites

Make sure your computer meets all [prerequisites](https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/?utm_source=laptop-repo#prerequisites) first.

### If you are on an M1 Mac, do not use Rosetta

Make sure that whatever terminal app you use is not in Rosetta mode. Read my guide on [installing Ruby on Apple Silicon](https://www.moncefbelyamani.com/how-to-install-homebrew-and-ruby-on-a-mac-with-the-m1-apple-silicon-chip/?utm_source=laptop-repo#how-to-tell-if-you-are-using-terminal-in-rosetta-mode) for more details.

### Quit and relaunch Terminal after running my script

I mention this several times in this README, as well as when the script finishes successfully, but I'll say it again. For the changes to take effect, you have to "refresh" your terminal. The best way is to quit and relaunch it.

### Now on to the installation

Begin by opening the Terminal application on your Mac. The easiest way to open
an application in macOS is to search for it via [Spotlight]. The default
keyboard shortcut for invoking Spotlight is `command-Space`. Once Spotlight
is up, just start typing the first few letters of the app you are looking for,
and once it appears, press `return` to launch it.

In your Terminal window, choose **ONE** of the options below, and copy and paste the command, then press `return`.

#### The recommended default installation for most people

```sh
bash <(curl -s https://raw.githubusercontent.com/monfresh/laptop/master/laptop)
```

#### The minimal installation for those that only want Ruby and nothing else

```sh
ONLY_RUBY=true bash <(curl -s https://raw.githubusercontent.com/monfresh/laptop/master/laptop)
```

The [script](https://github.com/monfresh/laptop/blob/master/mac) itself is
available in this repo for you to review if you want to see what it does
and how it works.

Note that the script might ask you to enter your macOS password at various
points. This is the same password that you use to log in to your Mac. The
prompt comes from Homebrew, because it needs permissions to write to the
`/usr/local` (or `/opt/homebrew` on M1 Macs) directory.

**Once the script is done, quit and relaunch Terminal.**

I recommend running the script regularly to keep your computer up
to date. Once the script has been installed, you'll be able to run it at your
convenience by typing `laptop` and pressing `return` in your Terminal.

[spotlight]: https://support.apple.com/en-us/HT204014

## Debugging script failures

Your last `laptop` run will be saved to a file called `laptop.log` in your home
folder. Read through it to see if you can debug the issue yourself.

**Note that this free script does not include support.**

If you get errors that you can't fix on your own, you can try my premium script.

My premium script includes the following features:

- guaranteed successful installation or I'll fix it for you personally over Zoom
- installs everything needed for Rails
- installs everything needed for Jekyll
- speeds up gem installation
- support for the fish shell
- customizable so you can add your own tools and Mac apps that you can automatically keep updated with the script
- detailed video walkthrough
- comprehensive troubleshooting guide to fix the most common issues with Homebrew and Ruby
- includes support from me 

If you're interested, [sign up for my waiting list](https://www.moncefbelyamani.com/ruby-script/?utm_source=laptop-repo) to get a 55% discount, and I'll let you know when it's ready. I'm shooting for the end of January.

## How to tell if the script worked

If the last thing the script displayed was "All done!", then everything the script was meant to do worked. **Now make sure you quit and restart your terminal.**

To verify that the Ruby environment is properly configured, run these commands:

```shell
ruby -v
```

This should show `ruby 3.1.0` or later. **If not, try quitting and relaunching Terminal.** Then try switching manually to 3.1.0 (or the latest version that was installed):

```shell
chruby 3.1.0
```

and check the version to double check:

```shell
ruby -v
```

To list all ruby versions currently installed:

```shell
chruby
```

## How to switch between Ruby versions and install different versions

To install an additional version,
run `ruby-install` followed by `ruby-` and the desired version. For example:

```shell
ruby-install ruby-2.7.5
```

To switch to this newly-installed version, run `chruby` followed by the version. For example:

```shell
chruby 2.7.5
```

Then verify the version:

```shell
ruby -v
```

**If this doesn't work, try quitting and restarting your terminal, then run chruby 2.7.5 again.**

You should switch to the desired version before you start any new project to make sure you are using the correct version of Ruby.

Note that gems only get installed separately in each version of Ruby. If you installed jekyll in 3.1.0, and then you install 2.7.5 later, you'll have to install jekyll again in 2.7.5.

## Check the Node installation

To verify if Node was installed and configured:

```shell
nodenv versions
```
You should see `v16.13.0` or later listed

```shell
nodenv help
```
You should see various commands you can run with `nodenv`.

## Why chruby and not RVM, rbenv, or asdf?

This script used `RVM` at first, back in 2015, but it started causing problems, so I switched to `chruby`, and haven't had any issues since. `chruby` is also the simplest, most reliable, and easiest to understand. I like that it does not do some of the things that other Ruby managers do:

- Does not hook `cd`.
- Does not install executable shims.
- Does not require Rubies to be installed into your home directory.
- Does not automatically switch Rubies by default.
- Does not require write-access to the Ruby directory in order to install gems.

Other folks who prefer `chruby`:

- <https://kgrz.io/programmers-guide-to-choosing-ruby-version-manager.html>
- <https://stevemarshall.com/journal/why-i-use-chruby/>
- <https://linhmtran168.github.io/blog/2014/02/27/moving-from-rbenv-to-chruby/>
