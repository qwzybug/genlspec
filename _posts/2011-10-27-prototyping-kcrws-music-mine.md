---
layout: post
title: Sweet Grid o' Mine
blurb: Prototyping KCRW's Music Mine
background: "#222"
title_color: "#f00"
body_color: "#888"
link_color: "#fff"
visited_link_color: "#ddd"
faded_background: "#f00"
faded_title_color: "#fff"
splash_background: red
splash_color: white
splash_link_color: white
---

Last month [PRX](http://prx.org/) and [KCRW](http://kcrw.org/) launched the [Music Mine](http://www.kcrw.com/about/musicmine-for-ipad), an iPad app for exploring the musical space of KCRW and its DJ's. I wrote quite a bit of it, and it's one of the projects I've worked on that I'm proudest of. We did some really nifty, innovative things, especially in the prototype phase, and I'm looking forward to documenting some of them here.

I feel very strongly about functional prototypes: especially on touch devices like the iPad, getting your hands on a proposed interface and feeling the interactions and navigation concepts viscerally is extremely important. "Getting the interface under one's thumb," so to speak. Today I'll focus on some of our prototypes for the app's main navigation feature: the grid.

[Matt MacDonald](http://www.mattmacdonald.com/) and [Rebecca Nesson](http://www.eecs.harvard.edu/~nesson/), two of the staff geniuses at PRX and my main collaborators on the code side, have [already written up a bit of the Music Mine prototyping process](http://labs.prx.org/2011/09/19/exploring-the-depths-of-kcrw-music-mine-part-one/) and how those prototypes, paper or code, evolved into the app as we now know it.

Here I'll focus on just showing some of the historical interactive sketches we made for KCRW; later this week, I'll write up some more specifics on the (remarkably simple) techniques we used to dress up the scrolling interactions.

Let's begin at the end: if you haven't yet, [download the KCRW Music Mine app from the App Store](http://itunes.apple.com/us/app/kcrw-music-mine/id451823339?mt=8)—it's free, and actually pretty good. (I still use it every morning.) I'll wait.

Failing that, you can check out this nifty video PRX produced. Note especially the scrolling elements.

<iframe width="830" height="467" src="http://www.youtube.com/embed/yYvcSGMX1D4" frameborder="0" allowfullscreen></iframe>

### Transformationers 2: the Dark of the Mine

The earliest concept sketches for the then-untitled KCRW project this spring were focused on largely textual lists of songs oriented around DJs. Now, iOS is great at lists: the table view is perhaps the single most important interface element.

But table views have been done, and done a thousand times. Their usability is well-demonstrated, but their panache is a little lacking. Why not play with them a bit?

<iframe width="830" height="467" src="http://www.youtube.com/embed/JW_mlEqzEro" frameborder="0" allowfullscreen></iframe>

(Soundtrack courtesy the [Larry Sanders Show](http://en.wikipedia.org/wiki/The_Larry_Sanders_Showw).)

Here, you can see a few examples of CoreAnimation spice thrown into the table view pot: a Jacob's Ladder animation to update a list from the top, and a few spatial transformations applied to scrolling contents in an interactive way. These are especially fun to get your fingers on.

We didn't end up using a lot of this in the app itself, though the general technique was applied on the grid, but I did throw in a bit of the 3D transform to scroll items on and off the list of artist audio. (We ended up capping the length of that list, so you'll probably never see it, but it's still fun to fiddle with.)

### Cell-o-phone

As the designs evolved, we started to settle more on the idea that we'd want to use album art to visually mark songs. Here are a few directions we toyed with.

<iframe width="830" height="467" src="http://www.youtube.com/embed/thEM0reaoh0" frameborder="0" allowfullscreen></iframe>

First: a fullscreen video idles by in the background while you explore KCRW's musical space—we envisioned bleached California vistas, Venice Beach, the rolling sunbaked Los Angeles hills, the Sunset strip, all constantly rolling past while you jam to the sweet, sweet sounds of adult contemporary indie rock. Think the Californication credits sequence in app form. Would that be fun? Only one way to find out.

The second clip is getting closer to the Music Mine: the basic design of the cells is in place, though here still arrayed in a 1-dimensional track, transformed along a path to give a sort of 1-and-a-half-dimensionality. (When Matt proposed this, I was lucky to be sitting in my friend Will's living room; Will is a Ph. D. student of mathematics at UCLA, and he graciously fit the curve and expressed it as a parametrization of _t_. Thanks, Will!)

Note here: a common theme amongst these prototypes is to try, whenever possible, to take advantage of the physics and behaviors of the built-in system classes. As I'll talk about more in a future post, we leverage conventional scroll views to drive all these transformations, which makes them (despite their 3D trappings) feel very much like native controls, especially in their acceleration and deceleration curves and edge behavior. This is extremely important in making an app feel native, even when you're getting fancy.

We ended up using the 1-and-a-little-dimensional scroll technique several places in the app, most notably in the DJ set view.

### On the Grid

Closing in on the Music Mine, we had settled roughly on the grid as it now stands. But the flat grid felt very static and boring, in a way; we tried applying some of the basic techniques of the self-transforming-scroll-views to give it some flair.

<iframe width="830" height="467" src="http://www.youtube.com/embed/xhsALzpJT78" frameborder="0" allowfullscreen></iframe>

The basic techniques, mixed-and-matched here in various ways, are:

1. The grid slide: instead of remaining fixed, the cells move more quickly as they approach the edges of the screen. (The effect is especially striking when turned way up: cells whizzing all willy-nilly. It was easy to get lost.) This basic technique, with the knobs adjusted fairly low, is what used in the final Music Mine.
2. The "sticky" grid: to attempt to allieve some of the navigational concerns with the large grid (which we ended up dealing with with the "Mall Map" mode), I tried augmenting the sliding scroll in (1) with a "stickiness": once you'd seen a cell in its proper position, it would stick there, giving you a sort of visceral sense of what you'd explored and what was new. We didn't go with this, either.
3. 3D transformations: content rotates away from the camera on a sort of saddle shape as it moves. It has visual flair, but wasn't really germane to this project.

The prototyping phase for the app was remarkably rapid, and, I feel, very enlightening and useful. Having live interaction prototypes to experiment with ideas while we were having them helped us keep from getting locked in too early to a first idea. Paper can only take you so far, when you're trying to get a design under your thumb.

I also want to give a special mention to all parties involved in this project: [RoundArch](http://roundarch.com/), [PRX](http://prx.org/), and [KCRW itself](http://kcrw.org/), for being so open to experimentation and new ideas. I've done a lot of client work, and it's exciting and fairly unique to work with people who are interested in making something interesting, even if you don't know what that is yet. I think we pulled it off.

Next time: I'll show you how to play with some of this magic in just a few lines of code. I bet we can do it in a dozen or so.
