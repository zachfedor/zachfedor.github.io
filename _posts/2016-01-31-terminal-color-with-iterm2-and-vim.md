---
title: "Terminal Color with Vim and Iterm2"
date: 2016-01-31
category: developer
excerpt: "How to make plain text sexy again"
---

_Or, How to Make Plain Text Sexy Again_


## The Problem

There wasn't much of a problem, but because I'm a hopeless yak-shaver I had to style everything to perfection before I get started on that actual project I've been dreaming up. The scene opens on a fairly rough vim config, a borderless iterm2 patch that I can't remember how to replicate, and a longing for greener pastures.

The first step is towards the excellent [base16 themes][base16-github]. I cloned a few of the repos and added a star for good measure. There are iterm2 and vim themes which are both required for my circumstances. Thre is also the base16 builder and a base16 shell repo, neither of which I understand yet. So I avoid them.


## Attempt #1

Within the iterm2 repo, there is a readme file and a whole bunch of `.plist` files. Each theme has four files: light and dark variants of 256-color and regular color schemes. There is a small note on the readme advising against the 256-color schemes if I don't know any better. I don't, but more sounds better. So I try an experiment.

I open iterm's preferences and import `base16-bespin.dark` in both regualar and 256 variants. I notice a small difference between the two as I switch back and forth between the two selections in the iterm profile color menu. The 256 variant falls in line with the 8-color and 8-bright-color labels. There is the theme's red plus a brighter version of the red. Probably for bold or something. But it looks like the colors are more correct than the regular variant. The roygbiv (of sorts) of term colors are only present on the normal side. The "bright" colors aren't bright at all. It looks like a very bland pallette of greys. 256 colors is definitely sounding better.

I try out a color testing bash script and things look alright. Alright, it's 256 colors from here on out. I selectively highlight the two dozen base16 256 color schemes and import them into the iterm preferences. Things are gonna look pretty for sure.

Then I follow the vim plugin's install guide in line with vim-plug and set the colorscheme in `.vimrc` appropriately and things look okay. The colors match up to what I expect, the profile is good, but it seems like only half of the picture. I add in linenumbers and a gitgutter and the cracks start to show. I'm only seeing 8ish colors. Even though the 256 scheme had 16  colors, it was really just 8 and a corresponding lighter shade for each. I start to think that there might be colors I'm missing.


## Attempt #2

I take a look at the issues and the maintainer points folks at a colortest in the base16-shel repo. Even though it looked scary, I cloned it and checked it out. The colortest show an output of 21 colors, 16 were the ones I was seeing in iterm's pregerences. The last 5 colors stick out like a sore thumb. They aren't `bespin`. I see a gaudy black and blue gradient.


## Moral of the story

Running the bash scripts in the Base16-Shell repo will change the color profile of iTerm2. Use this instead of the Preferences dropdown. This is only temporary though. To persist the color settings on new terminal windows, you need to call the Base16 script from within your `.bashrc` or `.zshrc` and then specify the colorscheme like so:

``` vimscript
export CLICOLOR=1
BASE16_SHELL="$HOME/code/base16-shell/base16-bespin.dark.sh"
[[ -s $BASE16_SHELL ]] && . $BASE16_SHELL
```

Then set the corresponding colorscheme in your `.vimrc` to match using your theme manager (e.g. [thematic][]) or with vanilla vimscript like so:

```
set background=dark
colorscheme base16-bespin
```


[base16-github]: https://github.com/chriskempson/base16
[thematic]: http://github.com/reedes/vim-thematic
