---
layout: post
title: "Two New Emacs24 Themes"
description: "A pair of Emacs24 themes, and a bit of discussion on the deftheme format"
category: Emacs
tags: [emacs, deftheme, emacs24]
---
{% include JB/setup %}

[Jump directly to the new themes...](#newthemes)

I have a number of Emacs color themes that were built a few years ago, they use the old `color-theme.el` system, I'd also adapted a web-based theme creator, so that it could load existing themes, as long as they were in a fixed format, the same as used by [http://themes.sweyla.com/](http://themes.sweyla.com/) 

Anyway, I've begun to convert some of my regular themes over to the new `deftheme` format. The main advangatge is there's no reliance on `color-theme` anymore. The only drawback for me is that I will need to update my existing theme-editor.

But in the meantime, it's possible to create `deftheme` style themes with `customize-create-theme` but it's not the best way to to it, frankly, even if I converted my existing theme tool, it would still be very limited.

The best thing to do is learn how to work with theme source code, which like everything that extends Emacs, is written in emacs lisp.

The basic template for making a theme is as follows:

    ;;; Filename: name-theme.el 
    (deftheme name
      "DOCSTRING")
     
    ;; Not a bad idea to define a palette...
    (let (
          (color-1 "#ffffff") 
          (color-2 "#ff0000") 
          (color-3 "#00ff00")
          (color-4 "#0000ff"))
     
      ;; Set faces
      (custom-theme-set-faces
       'name ;; you must use the same theme name here...
       '(default ((t (:foreground ,color-1 :background black))))
       '(cursor  ((t (:background ,color-4))))
       '(fringe  ((t (:background ,color-3))))
       ;;; etc... 
       ;;; don't use these settings of course, 
       ;;; they're horrible.
       )
     
      ;; Set variables
      (custom-theme-set-variables
       'name ;; again specify the same theme name...
       '(any-variable EXPR)
     
    (provide-theme 'name)
    ;;; name-theme.el ends here
     
For a more advanced example to work from, look at the new built in themes, I'd recommend `tango-theme.el` which you'll be able to find using, `M-x describe-theme` and then type `tango`.

The help buffer will give you a link to the source code, and you can study it further, (if you have questions, I'm very happy to answer them in the comments.)

<a name="newthemes" />

* * * * *

## Two new themes... 

![]({{ ASSET_PATH }}/emacs24.themes.vol1.png)

<p class=""><a href="{{ ASSET_PATH }}/DeepBlueDay-theme.el" class="btn btn-primary btn-large">DeepBlueDay-theme.el</a></p>

<p class=""><a href="{{ ASSET_PATH }}/MechanicalTurq-theme.el" class="btn btn-primary btn-large">MechanicalTurq-theme.el</a></p>

Save them to your emacs custom theme folder, `~/.emacs.d/` by default, and in Emacs use `M-x enable-theme` to load and enable them (TAB completion will be available there, to make your life easier.)

If you have questions, let me know. 