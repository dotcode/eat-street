eat-street noms
==========
eat-street noms prints out the names of the food stalls appearing today at [King's Cross Eat Street](http://www.eat.st/).
	
	
How it works
------------
It's a Python script that simply grabs the [Eat Street listings page](http://www.eat.st/kings-cross/) using urllib2, uses BeautifulSoup to scrape the relevant data, and spits back the names of the stalls.

It's fairly nasty source HTML, resulting in fairly nasty BeautifulSoup code. The info on Eat Street stalls is contained inside multiple div.altText. Each day is headed by a div.blue-heading and there is an hr inbetween all of these divs. There's no container around each day! Gah. There's almost undoubtedly a nicer way to do it, but I haven't found it (and, tbh, I haven't looked very hard ;)

The script only displays the info between 9am and 2pm cause I'm not interested in seeing it at other times (I'm not thinking about hotdogs at 7 in the morning, and the stalls shut at 2:30pm).

&lt;cough /&gt;
That's a total lie about me not thinking about hotdogs at 7 in the morning.
	
	
How does it look
----------------
Like this:

![the output of noms](https://github.com/downloads/dotcode/eat-street/noms.png)
	
Simple, huh?

Requirements
------------
Python, and it's reliant upon [BeautifulSoup](http://www.crummy.com/software/BeautifulSoup/) to parse the HTML … if you see the following error:

	ImportError: No module named BeautifulSoup

… then try installing BeautifulSoup:

	$ easy_install BeautifulSoup

(That's obviously the thing to do for the other modules as well, should they be missing)

Should you wish to display the information on your desktop, like me, then (on OS X) you'll be wanting to grab the fantastic [GeekTool](http://projects.tynsoe.org/en/geektool/). Grab it even if you couldn't care less about Eat Street. GeekTool is *brilliant*!
	
	
Installation
------------
	$ mkdir -p ~/bin
	$ curl -skL https://github.com/dotcode/eat-street/raw/master/noms >~/bin/noms
	$ chmod +x ~/bin/noms
	
Make sure `~/bin` is in your `$PATH` - or put the `noms` script somewhere else on your `$PATH`.
	
	
Usage
-----
	$ noms
	
I trigger the command using [GeekTool](http://projects.tynsoe.org/en/geektool/) so that I have the info displaying on my desktop. It's nice like that.
	
	
Author
------
Jude Robinson
-- dotcode at gmail dot com
-- @dotcode