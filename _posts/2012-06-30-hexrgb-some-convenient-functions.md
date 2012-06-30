---
layout: post
title: "HexRGB.el with some extras"
description: "a few useful enhancements for hexrgb.el"
category: Emacs
tags: [emacs, color, hexcolor, hsv]
---

If you use a lot of CSS we have a number of useful CSS DSLs, like
[SASS](http://sass-lang.com) and [LESS](http://lesscss.org) both of
which give us a collection of color manipulation functions. 

Adding a few of these helpful color functions to Emacs is relatively
simple and the bulk of the work required is already done by Drew Adams
in his [hexrgb.el](http://www.emacswiki.org/cgi-bin/wiki/hexrgb.el)
extension. 

I've added a few small modifications in
[this version](https://gist.github.com/3022890), the
function: `hexrgb-hsv-to-hex` accepts an additional argument
`nb-digits` so that hex colors returned are with 2 digits per r,g,b
value. 

    (hexrgb-hsv-to-hex   0.05   0.7   0.4     2) 
    ;;------------------ ^ ---- ^ --- ^ ----- ^ -------
    ;;                   hue    sat   light   nb-digits 
                                                 
Which returns <span style="color: white; background-color:#6639B8;
padding:4px; border-radius: 3px;">#6639B8</span>
                                                 
Previously, **hexrgb.el** returned hex colors with 4 digits per
channel (r, g, b), I'm not sure why, but obviously for a large number
of people, this isn't all that useful.

I've also added a few convenience functions that provide color
manipulation direct from hex colors. Currently these just work in
eshell or ielm (interactive emacs lisp modes.)

For example:

    (hexrgb-hex-set-brightness "#ff0000" 0.3)
    
returns <span style="color:white;background-color:#4C0000; padding:4px; border-radius: 3px;">#4C0000</span>

    (hexrgb-hex-set-saturation "#ff0000" 0.5)

returns <span style="color:white;background-color:#FF7F7F; padding:4px; border-radius: 3px;">#FF7F7F</span>
     
    (hexrgb-hex-set-hue "#FF0000" 0.6)

returns <span style="color:white;background-color:#0066FF; padding:4px; border-radius: 3px;">#0066FF</span>

These functions aren't complicated, they use the hex-to-hsv existing
function, grab the h, s or v values and then convert back to a hex
color value.  This makes working with colors easier, for example, you
could add `(require 'hexrgb)` to a theme definition and use the
functions to manipulate theme colors, or just switch on
[*rainbow-mode*](https://github.com/emacsmirror/rainbow-mode) when
you're in eshell, and play.

Here's the function definitions:

    (defun hexrgb-hex-set-brightness
      (hex brightness)
      "set brightness of a hex color, amount values from 0-1
       returns a 6 digit hex color"
      (let* ((hsv (hexrgb-hex-to-hsv hex))
             (h (first hsv)) (s (second hsv)) (v (third hsv)))
        (hexrgb-hsv-to-hex h s (* v brightness) 2)))
     
    (defun hexrgb-hex-set-saturation
      (hex saturation)
      "set saturation of a hex color, amount values from 0-1
       returns a 6 digit hex color"
      (let* ((hsv (hexrgb-hex-to-hsv hex))
             (h (first hsv)) (s (second hsv)) (v (third hsv)))
        (hexrgb-hsv-to-hex h (* s saturation) v 2)))
     
    (defun hexrgb-hex-set-hue
      (hex hue)
      "set hue of a hex color, amount values from 0-1
       returns a 6 digit hex color"
      (let* ((hsv (hexrgb-hex-to-hsv hex))
             (s (second hsv)) (v (third hsv)))
        (hexrgb-hsv-to-hex hue s v 2)))
     


