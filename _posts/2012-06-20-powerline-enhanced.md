---
layout: post
title: "Powerline.el enhanced"
description: "poweline.el for emacs, modeline beautified"
category: emacs
tags: [emacs]
---
{% include JB/setup %}

I've added a few different xpm shapes as alternatives to the arrows or
flatshapes, a rounded or folded corner, and a set of diagonals. 

Grab powerline from here:
[<span class="icon-download icon-white"></span> https://gist.github.com/2945235](https://gist.github.com/2945235)

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

![](http://ocodo.info/powerline/arrow.png)

    (setq powerline-arrow-shape 'arrow14)     ;; 14px high arrows

![](http://ocodo.info/powerline/arrow14.png)

    (setq powerline-arrow-shape 'half)        ;; flat

![](http://ocodo.info/powerline/half.png)

    (setq powerline-arrow-shape 'percent)     ;; ...? (I have no idea)

![](http://ocodo.info/powerline/percent.png)

    (setq powerline-arrow-shape 'curve)       ;; scallop curve

![](http://ocodo.info/powerline/curve.png)

## New shapes in this version

    (setq powerline-arrow-shape 'rounded)     ;; new, round corner

![](http://ocodo.info/powerline/rounded.png)

    (setq powerline-arrow-shape 'chamfer)     ;; new, folded corner

![](http://ocodo.info/powerline/chamfer.png)

    (setq powerline-arrow-shape 'slant-left)  ;; new, diagonal from left

![](http://ocodo.info/powerline/slant-left.png)

    (setq powerline-arrow-shape 'slant-right) ;; new, diagonal from right

![](http://ocodo.info/powerline/slant-right.png)

    (setq powerline-arrow-shape 'slant)       ;; mirrored diagonals

![](http://ocodo.info/powerline/slant.png)

ps. color theme here is called `color-theme-turquoise` it's available
here:

* [color-theme-turquoise] (https://github.com/ocodo/emacs.d/blob/master/dropins/color-theme-turquoise.el)
