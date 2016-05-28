---
layout: post
title: The Gold Factory Cipher Answers
description: The answers and explanation to my game 'The Gold Factory'
comments: true
---

<script>
window.onload = function() {
	var gold = 0;
	update();
	setInterval(function() {
		gold++;
		update();
	}, 1000)
	function update() {
		document.getElementById("gb").innerHTML = gold;
		document.getElementById("gb-200").innerHTML = gold + 200;
		document.getElementById("gb-1200").innerHTML = gold + 1200;
		document.getElementById("gb-3200").innerHTML = gold + 3200;
		document.getElementById("gb-5700").innerHTML = gold + 5700;
		document.getElementById("gb-13200").innerHTML = gold + 13200;
	}
};
</script>

This post is about my first incremental game [The Gold Factory](http://gamehelp16.github.io/thegoldfactory/). If you haven't played it yet then probably you want to play it first before reading this post.

***WARNING:*** *As the title says, this post contains answers to the cipher codes in the game. If you want to try solving them first then please stop reading.*

Now you have <span id="gb">0</span> gold bars.

In the early game, you can solve some codes to earn some extra gold bars to save some waiting time. Apparently some of the codes are pretty hard to solve (especially the last one). Even though there are already many answers floating around the internet, I decided to make this post to tell you the answers and the steps to do that.

## The First Code

> 13-1-19-20-5-18 2-18-1-14-3-8

This one is a very simple one, each number represents a letter where 1 = A, 2 = B, 3 = C and so on. The answer to this code is `master branch`.

Great! You have earned yourself 200 gold bars! Now you have <span id="gb-200">200</span> gold bars.

## The Second Code

> Lzwjw ak s ljwskmjw zavvwf kgewozwjw, al ak dguslwv sl s kwujwl hdsuw af lzw Hsuaxau Guwsf

For the second code, I used a technique called "[Caesarian Shift](http://rumkin.com/tools/cipher/caesar.php)". To solve it you need to replace each letter with the Nth letter after it. For example, if N = 1 then you need to replace A with B, B with C, C with D and so on. If N = 2, then A = C, B = D, and so on. Using the tool linked above, you can do this faster than using hand. Just enter the code in the text box and change the N values until you get a sentence that makes sense.

**Tip:** The N value is 8 and the answer is `There is a treasure hidden somewhere, it is located at a secret place in the Pacific Ocean` (This sentence has nothing to do with the game anyway, I just made it up).

Now you have earned another 1000 gold bars! You have <span id="gb-1200">1200</span> gold bars.

## The Third Code

> Om s ept;f gi;; pg n;pvld

For this one you will need to look at your keyboard (a [US standard QWERTY keyboard](https://upload.wikimedia.org/wikipedia/commons/3/3a/Qwerty.svg), specifically). Simply replace each character with the letter on the left side of that character on your keyboard. The answer is `In a world full of blocks`.

2000 gold bars has been earned! Now you have <span id="gb-3200">3200</span> gold bars.

## The Fourth Code

> VGhlIHBsYW50IGlzIGZhbW91cyBiZWNhdXNlIG9mIHRoZSBhYmlsaXR5IHRvIGN1cmUgc29tZSBkaXNlYXNlcw==

This one is a base64 encoded message. To decode it, you need to use a tool like this one: [base64decode.org](https://www.base64decode.org/). Alternatively, you could use your browser to decode the message. To do this, open your browser's developer console (By pressing F12 or Ctrl+Shift+J. If it doesn't work try searching the keyboard shortcut for your browser) then type in this code `atob('<insert the code here>')` and you get the answer (don't forget to remove the quotes first!)

The answer is: `The plant is famous because of the ability to cure some diseases`.

Great! 2500 more gold bars! Now you have <span id="gb-5700">5700</span> of them!

## The Fifth Code

> towiiag g se&nbsp;&nbsp;&nbsp;rir,oaoan&nbsp;&nbsp;&nbsp;ft ofo srtod tddyi ot mdy lugelelmwon foemsthiuaa ttclntclga&nbsp;&nbsp;bhhs

*After around 2 years I just realized that there is a mistake on this code in the game. I didn't change those multiple spaces to `&nbsp;`, and therefore the multiple spaces in the code are shown as just one space only, thus the code can't be decrypted. The code in the game has been fixed, I'm really really sorry for this.*

The fifth code is the hardest one of them all (please don't hate me for this). People seem to not be able to solve this without looking at the source code. Well, now I'm gonna tell you how to properly solve the code (I have told this on Reddit before in the comments section. But not many people seem to saw it).

The past me a few years ago wants to make a really hard code to solve, and while browsing [Rumkin's Cipher Tools](http://rumkin.com/tools/cipher/) I found a cipher called '[Railfence](http://rumkin.com/tools/cipher/railfence.php)' (for more info about the cipher just click the link). Anyways, since past me wanted to make a hard one, I decided to railfence encode it 3 times (with the default parameters), and thus the code is born.

To solve this code, open the railfence cipher tool linked earlier, put in the code, make sure you select 'decrypt' instead of 'encrypt' and enter the code. Copy the result and put it again in the text box, repeat until you got the answer.

The answer to this code is `the gold factory was built long time ago, and it is the most famous gold factory in the world`.

Congratulations! Now you have solved the final ultimate code and earned a nice amount of 7500 gold bars! You have <span id="gb-13200">13200</span> gold bars now!

And that's it guys, the guide to solve those 5 codes. Now go buy some pizzas! :)
