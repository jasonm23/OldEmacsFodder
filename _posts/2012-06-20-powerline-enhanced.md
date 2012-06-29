---
layout: post
title: "Powerline.el enhanced"
description: "poweline.el for emacs, modeline beautified"
category: emacs
tags: [emacs]
---
{% include JB/setup %}

Powerline is an awesome little enhancement for Emacs, by an original
author unknown, you can find the original version at [http://emacswiki.org/emacs/powerline.el](http://emacswiki.org/emacs/powerline.el)

I've added a few different xpm shapes as alternatives to the arrows or
flatshapes, a rounded or folded corner, and a set of diagonals. 

Grab the updated powerline from here: [https://gist.github.com/2945235](https://gist.github.com/2945235) <span class="icon-download icon-white"></span>

Put it somewhere in your Emacs load path (e.g. `~/.emacs.d`) and add
the following lines to the end of your `.emacs` / `init.el` - to load
it, set the colors and graphic shape:

    (require 'powerline)
    ;; colors...
    (setq powerline-color1 "#222")      ;; dark grey; 
    (setq powerline-color2 "#444")      ;; slightly lighter grey
    ;; shape...
    (setq powerline-arrow-shape 'arrow) ;; mirrored arrows, 
    ;; see below for the shape options
    
## Shapes

    (setq powerline-arrow-shape 'arrow)       ;; 18px high arrows  

![]({{ ASSET_PATH }}/arrow.png)

    (setq powerline-arrow-shape 'arrow14)     ;; 14px high arrows

![]({{ ASSET_PATH }}/arrow14.png)

    (setq powerline-arrow-shape 'half)        ;; flat

![]({{ ASSET_PATH }}/half.png)

    (setq powerline-arrow-shape 'percent)     ;; ...? (I have no idea)

![]({{ ASSET_PATH }}/percent.png)

    (setq powerline-arrow-shape 'curve)       ;; scallop curve

![]({{ ASSET_PATH }}/curve.png)

## New shapes in this version

    (setq powerline-arrow-shape 'rounded)     ;; new, round corner

![]({{ ASSET_PATH }}/rounded.png)

    (setq powerline-arrow-shape 'chamfer)     ;; new, folded corner

![]({{ ASSET_PATH }}/chamfer.png)

    (setq powerline-arrow-shape 'slant-left)  ;; new, diagonal from left

![]({{ ASSET_PATH }}/slant-left.png)

    (setq powerline-arrow-shape 'slant-right) ;; new, diagonal from right

![]({{ ASSET_PATH }}/slant-right.png)

    (setq powerline-arrow-shape 'slant)       ;; mirrored diagonals

![]({{ ASSET_PATH }}/slant.png)

