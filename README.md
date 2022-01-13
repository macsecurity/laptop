# Laptop

[![Build Status](https://travis-ci.org/monfresh/laptop.svg)](https://travis-ci.org/monfresh/laptop)

Laptop is a script that will set up a complete Ruby web development environment on your Mac, including Node, Postgres, Rails, and Jekyll. You also have the option to skip those web dev tools and only install the minimum required to use Ruby.

It can be run multiple times on the same machine safely. It installs,
upgrades, or skips packages based on what is already installed on the machine.

You can also easily [customize](#customize-in-laptoplocal-and-brewfilelocal)
the script to install additional tools.

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
- [Customize in `~/.laptop.local` and `~/Brewfile.local`](#customize-in-~laptoplocal-and-~brewfilelocal)
- [How to manage background services \(such as Postgres\)](#how-to-manage-background-services-such-as-postgres)
- [Note about the fish shell](#note-about-the-fish-shell)
- [What problem does this script solve?](#what-problem-does-this-script-solve)
- [Why chruby and not RVM or rbenv?](#why-chruby-and-not-rvm-or-rbenv)
- [Credits](#credits)

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
- fish (see the note at the bottom of this README)

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

It should take less than 15 minutes to install (depends on your machine and
internet connection).

## Install

**IMPORTANT! CHECK ALL OF THE ITEMS BELOW BEFORE AND AFTER RUNNING THE SCRIPT!** 

### Check prerequisites

Make sure your computer meets all [prerequisites](https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/#prerequisites?utm_source=laptop_repo) first.

### If you are on an M1 Mac, do not use Rosetta

Make sure that whatever terminal app you use is not in Rosetta mode. Read my guide on [installing Ruby on Apple Silicon](https://www.moncefbelyamani.com/how-to-install-homebrew-and-ruby-on-a-mac-with-the-m1-apple-silicon-chip/#how-to-tell-if-you-are-using-terminal-in-rosetta-mode?utm_source=laptop-repo) for more details.

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

**The premium version is guaranteed to end your Ruby troubles, or I will personally fix it for you.**

The premium script will be ready soon (most likely end of January 2022), but you can get early access to it at a 55% discount to help me test it.

**It will be priced at $37 when it's released, but you can get it for $17 today, which will give you lifetime access to the script, including updates.**

To get the premium script, [book a Zoom session with me](https://savvycal.com/monfresh/b12933f7) so we can test it together.

## How to tell if the script worked

If the last thing the script displayed was "All done!", then everything the script was meant to do worked. **Now make sure you quit and restart your terminal.**

To verify that the Ruby environment is properly configured, run these commands:

```shell
ruby -v
```

This should show `ruby 2.7.4` or `ruby 3.1.0`. If not, try switching manually to 2.7.4:

```shell
chruby 2.7.4
```

and check the version to double check:

```shell
ruby -v
```

Then check where Ruby is installed:

```shell
which ruby
```

This should point to the `.rubies` directory in your home folder. For example:

```
/Users/monfresh/.rubies/ruby-2.7.4/bin/ruby
```

## How to switch between Ruby versions and install different versions

The first time you run the script, it will install both the latest Ruby (currently 3.1.0) as well as Ruby 2.7.4, which is the version that is compatible with most gems at the moment. If you run the script again, it will check for newer 3.x versions, and if it finds one, it will install it. You will still have Ruby 2.7.4. That's the advantage of using version managers like `chruby`. You can have many different versions installed at the same time and you can switch between them.

**Ruby 3.1.0 is not yet fully compatible with the latest version of Jekyll. So, for now I recommend using Ruby 2.7.4. Keep reading for instructions.**

To check if you have Ruby 2.7.4 installed, run this command:

```shell
find "$HOME/.rubies" -maxdepth 1 -name 'ruby-2.7.4'
```
If nothing is returned, then you should install it:

```shell
ruby-install ruby-2.7.4
```

To switch to this newly-installed version, run `chruby` followed by the version. For example:

```shell
chruby 2.7.4
```
You should run `chruby 2.7.4` before you start any new project to make sure you are using the correct version of Ruby.

Another highly-recommended way to automatically switch between versions is to add a `.ruby-version` file in your Ruby project with the version number prefixed with `ruby-`, such as `ruby-2.7.4`. To test that this works:

1. `cd` into your Ruby project, such as your Rails app or Jekyll site
2. First, check to see if the file already exists: `cat .ruby-version`. If not, then create it in the next step.
2. Create a file called `.ruby-version` with `ruby-2.7.4` in it:
    ```shell
    echo 'ruby-2.7.4' >> .ruby-version
    ```
1. `cd` into a folder outside of your project, such as your home folder: `cd ~`
2. Run `ruby -v`. It will probably say `2.6.3p62`, which is the Ruby that came preinstalled on your Mac.
4. `cd` into your project
5. Verify that `ruby -v` shows `2.7.4p191`

Note that gems only get installed in a specific version of Ruby at a time. If you installed jekyll in 3.0.3, and then you install 2.7.4 later, you'll have to install jekyll again in 2.7.4.

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

## Customize in `~/.laptop.local` and `~/Brewfile.local`

```sh
# Go to your macOS user's root directory
cd ~

# Download the sample files to your computer
curl --remote-name https://raw.githubusercontent.com/monfresh/laptop/master/.laptop.local
curl --remote-name https://raw.githubusercontent.com/monfresh/laptop/master/Brewfile.local

# open the files in your text editor
open .laptop.local
open Brewfile.local
```

Your `~/.laptop.local` is run at the end of the `mac` script.
Put your customizations there. If you want to install additional
tools or Mac apps with Homebrew, add them to your `~/Brewfile.local`.
You can use the `.laptop.local` and `Brewfile.local` you downloaded
above to get started. It lets you install the following tools and Mac apps:

- [Firefox] for testing your Rails app on a browser other than Chrome or Safari
- [Flux] for adjusting your Mac's display color so you can sleep better
- [GitHub Desktop] for working with your repos using a GUI
- [iTerm2] - an awesome replacement for the macOS Terminal
- [Redis] for storing key-value data
- [Sublime Text 3] - a solid and fast code editor
- [Visual Studio Code] - Microsoft's popular code editor

[firefox]: https://www.mozilla.org/en-US/firefox/new/
[flux]: https://justgetflux.com/
[github desktop]: https://desktop.github.com/
[iterm2]: https://iterm2.com/
[redis]: https://redis.io/
[sublime text 3]: https://www.sublimetext.com/3
[visual studio code]: https://code.visualstudio.com/

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Laptop functions such as `fancy_echo`, and `gem_install_or_update` can be used
in your `~/.laptop.local`.

If you want to skip running `.laptop.local`, you can set the `SKIP_LOCAL` environment variable to `true` before running `laptop`:

```shell
SKIP_LOCAL=true laptop
```

## How to manage background services (such as Postgres)

The script does not automatically launch these services after installation
because you might not need or want them to be running. With Homebrew Services,
starting, stopping, or restarting these services is as easy as:

```
brew services start|stop|restart [name of service]
```

For example:

```
brew services start postgresql
```

To see a list of all installed services:

```
brew services list
```

To start all services at once:

```
brew services start --all
```

## Note about the fish shell

`chruby` does not support the fish shell out of the box. There is a `chruby-fish` tool, but it has bugs that manipulate the `PATH` in a way it shouldn't. This can prevent using Nodenv if Node is already installed with Homebrew. This is just one example of issues you might run into and not understand why things aren't working. Until the issues are fixed, here is a workaround you can use:

1. Uninstall chruby-fish if you have it: `brew uninstall chruby-fish`
1. Clone this fork of `chruby-fish` to your computer:
    ```shell
    git clone https://github.com/bouk/chruby-fish/
    ```
2. Check out the `rewrite-fish` branch:
    ```shell
    cd chruby-fish
    git checkout -b rewrite-fish origin/rewrite-fish
    ```
3. Run `make install`
4. Remove any lines from your fish config file that `source` chruby, such as:
    ```text
    source /usr/local/share/chruby/chruby.fish
    source /usr/local/share/chruby/auto.fish
    source /usr/local/share/chruby/chruby.sh
    source /usr/local/share/chruby/auto.sh
    ```
5. Quit and restart Terminal

See this pull request for more information: https://github.com/JeanMertz/chruby-fish/pull/39


## What problem does this script solve?

Installing Ruby and/or gems is a common source of confusion and frustration.
Search for `You don't have write permissions for the /Library/Ruby/Gems/2.3.0 directory` or "[command not found](https://www.moncefbelyamani.com/troubleshooting-command-not-found-in-the-terminal/?utm_source=laptop-repo)" in your favorite search engine, and you will see pages and pages of results.

To make matters worse, the vast majority of suggestions are bad advice and
incomplete. The reason for the error message above is because people are trying
to install gems using the version of Ruby that comes pre-installed by Apple.
That error message is there for a reason: you should not modify macOS system
files. A common suggestion is to bypass that security protection by using
`sudo`, which is [not safe](https://www.moncefbelyamani.com/why-you-should-never-use-sudo-to-install-ruby-gems/?utm_source=laptop-repo) and can cause issues down the line that are hard to undo.

The recommended way of using Ruby on a Mac is to install a newer (the
macOS version is often outdated and is only updated during a major release),
separate version in a different folder than the one that comes by default on
macOS. The best and most flexible way to do that is with a Ruby manager. The
most popular ones are: RVM, rbenv, chruby, and asdf. I have chosen `chruby` in this script. See [below](#Why-chruby-and-not-RVM-or-rbenv) for my reasons. There are different ways to
install these tools, and they all require additional configuration in your [shell startup file](https://www.moncefbelyamani.com/which-shell-am-i-using-how-can-i-switch/?utm_source=laptop-repo), such as `.bash_profile` or `.zshrc`.

When attempting to install and configure a Ruby manager manually, it's easy to
miss or fumble a step due to human error or incomplete or outdated instructions. 

Since all of the steps are automatable, **the best and most reliable way to set up Ruby on a Mac is to run this script**. I test it regularly on my spare laptop where I delete the hard drive and install fresh versions of macOS. 

**If you've already attempted to set up a development environment on your Mac, and you run into issues with my script that you can't figure out yourself, you can buy the premium version of my script. It detects all known issues and installs Ruby in a clean development environment.**

**The premium script is not quite ready yet, but you can get early access to it at a 55% discount to help me test it. It will be priced at $37 when it's released, but you can get it for $17 today, which will give you lifetime access to the script, including updates.**

 You can [book a Zoom session with me](https://savvycal.com/monfresh/b12933f7) to get access to the premium script and we can test it together.

## Why chruby and not RVM or rbenv?

This script used `RVM` at first, but it started causing problems, so I switched to `chruby`, and haven't had any issues since. `chruby` is also the simplest, most reliable, and easiest to understand. I like that it does not do some of the things that other Ruby managers do:

- Does not hook `cd`.
- Does not install executable shims.
- Does not require Rubies to be installed into your home directory.
- Does not automatically switch Rubies by default.
- Does not require write-access to the Ruby directory in order to install gems.

Other folks who prefer `chruby`:

- <https://kgrz.io/programmers-guide-to-choosing-ruby-version-manager.html>
- <https://stevemarshall.com/journal/why-i-use-chruby/>
- <https://linhmtran168.github.io/blog/2014/02/27/moving-from-rbenv-to-chruby/>


## Credits

This script was originally inspired by [thoughbot's laptop](https://github.com/thoughtbot/laptop) script, but
it works quite differently now.
