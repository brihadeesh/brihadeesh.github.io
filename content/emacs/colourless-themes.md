+++
title = "Colourless themes for Emacs"
author = ["peregrinator"]
publishDate = 2023-03-19T00:00:00+05:30
lastmod = 2023-03-19T23:45:44+05:30
url = "/emacs/colourless_themes.html"
draft = false
autonumbering = true
+++

<div class="alert-info alert">

This is a work in progress. You can browse the code on my [sourcehut](https://git.sr.ht/~peregrinator/colourless-themes).

</div>


## <span class="section-num">1</span> Boring themes for the elitist {#boring-themes-for-the-elitist}

`colourless-themes` is a collection of “primarily colourless
themes". This was forked from Tomas Letan's macro of the same
name.[^fn:1]


### <span class="section-num">1.1</span> Installation {#installation}

Install this how you would install a package from github - this varies
with the flavour of Emacs or the setup in use. If you use a
Frankenstein's monster like I use, do:

```emacs-lisp
(use-package colourless-themes
  :straight (:host sourcehut
   :repo "~peregrinator/colourless-themes-el")

  :config
  ;;optionally loading a theme
  (load-theme 'einkless t)
```


### <span class="section-num">1.2</span> Usage {#usage}

Temporarily set it the `M-x load-theme` , or via `M-x
customize-themes`. To make it persistent, see [Installation](/emacs/colourless_themes.html#installation). Disable
any other themes to ensure a colourless experience.


## <span class="section-num">2</span> Featured themes {#featured-themes}

Themes offered besides those from upstream are

-   `mephistopheles` an original dark theme with yellow and green
    foreground, again inspired by Stanislav Karkavin's vim theme
    mentioned above.
-   `beelzebub` A dark, purplish colourscheme based on Stanislav
    Karkavin's vim theme: [vim-beelzebub](https://github.com/xdefrag/vim-beelzebub)
-   `nofrils`, Emacs ports _faithful_ to the [original nofrils
    themes](https://github.com/robertmeta/nofrils). These have a few more colours than the others.


### <span class="section-num">2.1</span> Screenshots {#screenshots}

WIP

[^fn:1]: The macro is a rework of theirs — an opinionated take
    perhaps? Find their source code at [~lthms/colorless-themes.el](https://git.sr.ht/~lthms/colorless-themes.el)