---
layout: post
title: Flickity vs Slick / Jquery carousel plugins comparison
published: true
---

### The 2 carousel components

* [Flickity](https://flickity.metafizzy.co) is a good carousel component made by the same developer that made Jquery masonry

* [Slick](http://kenwheeler.github.io/slick/)  is a famous carousel component that brand as "the last carousel you'll ever need

### Angular integration 

Flickity has an angular ngx wrapper [ngx-flickity](https://github.com/geex-arts/ngx-flickity). But the author precised "not ready for production".

Slick has a stable angular wrapper [ngx-slick](https://github.com/devmark/ngx-slick) 

### Features only in flickity 

[All flickity options](https://flickity.metafizzy.co/options.html)

**Options specific to flickity (not in slick)**

* **freeScroll** / Allow to scroll not on a complete slide, but manually so you can stop where you want

* **groupCells** / Group cells allow to advance slide groups by slide group (3 by 3 for example)

* **asNavFro** / Double carousel sync to make a nav bar from one to control the larger one.
<img src="./images/carousel-sync.png">

### Features in slick carousel 

[Slick options page](http://kenwheeler.github.io/slick/)