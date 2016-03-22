---
layout: post
title: "JS1k 2016: Elemental Forest - Part 1"
description: The first part of my post-mortem blog post about my 2016 JS1k entry 'Elemental Forest'
comments: true
---

This year is my third year participating in [JS1k](http://js1k.com/), a contest about making something cool using Javascript in 1 kilobyte or less. After submitting two [text based](http://js1k.com/2014-dragons/demo/1649) [demos](http://js1k.com/2015-hypetrain/demo/2118) (those are two links, btw), this year I submitted a more pleasing to the eye demo and I called it "Elemental Forest".

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">⚛ Elemental Forest is a <a href="https://twitter.com/hashtag/js1k?src=hash">#js1k</a> demo by Richard Sudaryono (<a href="https://twitter.com/gamehelp16">@gamehelp16</a>) <a href="https://t.co/lU2HABTCET">https://t.co/lU2HABTCET</a> <a href="https://t.co/6FtaPd5LQg">pic.twitter.com/6FtaPd5LQg</a></p>&mdash; JS1K (@js1k) <a href="https://twitter.com/js1k/status/700049453919637504">February 17, 2016</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

This demo was inspired by [Grove](https://www.androidexperiments.com/experiment/grove), an Android Experiment by Simon Geilfus. Also, I would like to thank [Coding Math](https://www.youtube.com/user/codingmath) YouTube channel for the awesome tutorials. Without it my submission this year probably would just be another text based one.

---

In this and the next post I will explain the code that works behind the demo, but before that let's look at the 'original' source of the demo! (You will know why the word 'original' is quoted)

{% gist d4f7260c31d98261ccbb %}

The code was then passed through [Closure Compiler](https://closure-compiler.appspot.com/) and [RegPack](http://siorki.github.io/regPack.html), which is a little improvement from the past years because I haven't discovered RegPack yet and used [JS Crush](http://www.iteral.com/jscrush/) instead which is pretty good already. Also, if you're wondering, the original original source was 1688 bytes long and then crushed into 1004 bytes (-684B, -40.52%). Yes, I copied that data and that's how I knew that I didn't recover the whole original source successfully.

## The Trees

I decided to talk about these first and in a separate section because let's face it, most of the things you see in the demo are just trees. If you watched the demo long enough, you will discover that there are two types of trees, the 'normal trees', and the 'triangle trees'. I will only cover the normal ones because the triangle trees literally are just triangles.

The function that draws trees is named `T()` and could be found on lines 91-122 of the gist. The parameters `x` and `y` contain the x and y positions of the tree, and the parameter `z` is used only to determine whether to show the normal or triangle trees.

The trunk of the normal trees are made of two lines with the line width of `r()*12+28` (`r()` is a seeded random number generator function). The leaves are a little bit more complex, and I recommend you to watch the [4th episode](https://www.youtube.com/watch?v=SoYnZHBP-6M) of Coding Math first. In the end of the video you could see circles that are drawn in a circle shape using simple trigonometry, and that's almost exactly how the leaves are drawn. But instead of drawing circles, the position is used for the `lineTo` (or `moveTo`) function and then `fill` will be called. To make the trees look a little bit different for each of them, the radius of the 
'big circle' and the angle between each points are a little bit randomized.

In the next part I will cover about the rest of the stuff in the code, thank you for reading!