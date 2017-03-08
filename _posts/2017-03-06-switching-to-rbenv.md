---
title: "Switching to rbenv"
date: 2017-03-06
category: dev
---

My company just switched from `rvm` to `rbenv` and I had some issues in transit. I figured I'd add my setup here just in case, and I might as well do some research while I was at it.

## Why rbenv?

First and foremost, we needed a way to control Ruby versions between all of our active projects. We're an agency, we need to juggle projects at various ages without conflicting environments. But why switch from `rvm`, the Ruby Version Manager? Because `rvm` does a lot more than handle versions. We want to follow the Unix philosophy of doing one thing well.


## How does it work?

All of this version management is handled with path shims. When you enter a command into your terminal, your shell looks through a series of directories to find the correct program to run. Those directories are in an environment variable called `$PATH`. The shell runs the first program to match the command.

`rbenv` intercepts this sequence by prepending it's own directory at the front of your path. Your ruby-based command will hit a shim instead of the actual command. This shim looks up which version of ruby to use and runs the real command with that version of ruby. It will look in the following places for that version:

- the `RBENV_VERSION` environment variable (could be set via `rbenv shell` command)
- a `.ruby-version` file in the directory of the script you are running, or in any of it's parent directories until it hits `/`
- a `.ruby-version` file in the project directory, or parent directories to `/`
- the global version kept in `~/.rbenv/version`

The appropriate ruby version is kept in `~/.rbenv/versions/`.


## Install on MacOS

Assuming you use `homebrew` and **no other ruby version manager is installed**:

{% highlight shell %}
$ brew update
$ brew install rbenv ruby-build
$ rbenv init
{% endhighlight %}

To avoid the `rbenv init` command every time you login to your shell, add the following lines to your `.zshrc` or `.bashrc`:

{% highlight shell %}
echo 'eval "$(rbenv init -)"' >> ~/.zlogin
source ~/.zlogin
{% endhighlight %}

** I forgot to install a new version of ruby and that caused some problems **
# TODO: add steps to find new stable version, install it, and use it globally


## Usage

- Install a new version with `rbenv install <version_number>`
- Check your current version with `rbenv version`.
- Install gems as usual, but only for a given ruby version, with `gem install <gem_name>`.
- Remove ruby versions by `rm -rf`ing the version directory or use the `rbenv uninstall <version_number>` command.
- Use the `rbenv local` sub-commands to get, set, or unset an app-specific version.
- Use the `rbenv global` sub-commands for the system default.


---

**Sources:**

- [rbenv docs](https://github.com/rbenv/rbenv)
- [thoughtbot tutorial](https://robots.thoughtbot.com/using-rbenv-to-manage-rubies-and-gems)

