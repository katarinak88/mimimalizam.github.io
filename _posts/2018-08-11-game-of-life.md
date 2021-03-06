---
layout: post
title: "Game of Life"
date: 2018-08-11
excerpt: "A rather complex story"
project: true
tags: [ruby, p5js, jekyll]
---

A rather complex story about few tools with incredible documentation.
Basically, it started with a podcast, then I added a bit of
[p5js](https://p5js.org/), and then pack it in a gem-based [Jekyll](https://jekyllrb.com/) theme.
Finally, I spiced it up with the [Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life),
the best example in mathematics of how a few simple rules... could complicate a life.

```
I don't expect to find inspiration. It just sort of comes.
Sometimes you step on a bug and you get inspired
```

--- Iris Apfel

One of the podcasts I enjoyed listening to was Changelog's [Request For Commits](https://changelog.com/rfc).
[The particular episode](https://changelog.com/rfc/19) which inspired me this time,
tells a story about design and designing the p5js culture.

## p5js

p5js is a JavaScript library created by [Lauren McCarthy](http://lauren-mccarthy.com/about)
and developed by a community of collaborators.

```
p5.js is a community interested in exploring the creation of art and design with technology.

We like these hashtags: #noCodeSnobs (because we value community over efficiency),
#newKidLove (because we all started somewhere),
#unassumeCore (because we don't assume knowledge),
and #BlackLivesMatter (because of course).
```

I started by skimming through p5js docs - it felt great 👏!
On top of that - being able to create an interactive page in just a few minutes - made my day.
The rest is history - everything just clicked!
I was able to clearly imagine patterns of the Game and to quickly make it real.

If you are reading the web version of this post and you haven't already started the Game,
feel free to press key `e` from the comfort of your keyboard.
In all other cases, please click [here](https://mimimalizam.github.io/game-of-life/)
and continue from the previous sentence 😻.

## Theme features

Since p5js relies on events and callback functions, you can easily add a functionality
to your page. This made breaking the rule of Game quite plasant exprience.
Now, everyone can interact with an ongoing game with few `vim`-inspired commands.

For example, you can:
- press `e` to start and/or restart the Game
- if your eyes are a bit tired and you'd prefer to quietly read a page you can
 - type `q` to remove cells from the screen
 - type `p` to pause the Game (use `s` to resume the Game)
- type `i` to start the Insert Mode where you can create new cells
  - with a click of a mouse new cells will be randomily created around
  - if you are feeling happy, drag mouse to create some more
- press `ESC` to --- escape the Insert Mode
- use `j` and `k` to control the speed
- to change the cells' color press any additional key

## Jekyll

At this point, I wanted to pack it in a Ruby gem and decided to create a Jekyll theme.
Coming all the way back from 2008, Jekyll is static site generator
written in Ruby by [Tom Preston-Werner](http://tom.preston-werner.com/), Github's cofounder.

So, if you are reading this on my blog - it's a Jekyll generated one :)
All articles are written in plain [Markdown](https://daringfireball.net/projects/markdown/) and
template processing is handled by [Liquid](https://shopify.github.io/liquid/),
a templating language created by Shopify. This makes writing HTML much easier 😌.

### Packing Jekyll theme in a Ruby gem

This point went flawlessly as well. Basically, by following [these steps](https://jekyllrb.com/docs/themes/#creating-a-gem-based-theme) I:

- created a [RubyGems](https://rubygems.org/) account
- made sure that `bundler` and `jekyll` are in place

```
gem install bundler
gem install jekyll
```

- created a gem

```
jekyll new-theme jekyll-theme-name
gem build jekyll-theme-name.gemspec
```

- [and published it](https://guides.rubygems.org/publishing/)

Voila! Its code is available [here](https://github.com/mimimalizam/game-of-life-theme).
So after all it's `I-listened-to-a-podcast-and-this-is-what-happened-to-me` kind of a post.

## Game of life

The universe of the game is fairly simple. The two-dimensional grid containse cells that are
either alive or dead. Based on its eight neighbours,
games decides if a particular cell will be alive in the next generation.
This happens according to the following rules:

- **Loneliness:** any live cell with fewer than two live neighbours dies
- **Overpopulation:** a live cell with more than three live neighbours dies
- **Stasis:** a live cell with two or three live neighbours lives, unchanged, to the next generation
- **Reproduction:** a dead cell with exactly three live neighbours will come to life.

This might seem like a boring game at first, but one of many different beautiful
patterns might unexecpetedly pop up. Also, it is not easy to predict whether
the game will go on infinitely :)
These are classified according to their behavior - like [`spaceships`](https://en.wikipedia.org/wiki/Spaceship_(cellular_automaton)).
The most recently descovered spaceship is [`Sir Robin`](https://cp4space.wordpress.com/2018/03/11/a-rather-satisfying-winter/).
Its name is a reference to Monty Python's "Brave Sir Robin", who bravely runs away as fast as possible.

## Some ideas

As time allows, I'd like to make the creation of some famous cellular automatons way easier.
And to periodically update this story :)
