+++
title = "Should I still be using Firefox?"
author = ["peregrinator"]
date = 2025-03-09T22:22:00+05:30
draft = false
bsky = ""
+++

I've been using Firefox ever since I got my first laptop back in 2017,
mostly since it comes with most Linux distributions' own package
repositories. It was around the same time that I decided that I
wouldn't use Chrome because of all the ways in which it collects and
abuses personal data[^fn:1]. Recent events with Mozilla that have changed the way Firefox
handles data have left me concerned about whether the browser is still
"better" than Chrome in that regard. My doubts started with actually a
meme that was circling around on Twitter that a friend had retweeted
about a diff in the source code for Firefox.

{{< x user="theo" id="1895630175939019125" >}}

{{< figure src="/images/firefox_diff.jpg" alt="a diff showing the removal of an FAQ item regarding whether personal data is sold by Firefox" caption="a screenshot of a diff from the source code of Firefox, from the tweet above" >}}

This was followed by allegedly, various changes in their terms of use
regarding how they use personal data entered on websites while using
the browser amongst which they basically admit to selling personal
data in some form or the other[^fn:2]
which is something I could never stand for. This, along with a bunch
of features I don't really use — their obsession with AI, which is
quite obvious in their release notes with recent releases — have made
me increasingly uncomfortable with the whole idea of continuing to use
Firefox. I don't actually know what changes they've made off-late and
I obviously don't have the time to go through the changes at the
source level (if I could even understand what was happening.)

I've basically gotten so used to using most of the other features on
the browser such as syncing and migrating to a new device by just
logging into the browser that I'm not sure I can find a new browser
that will really work for me the same way.


## Firefox forks? Chrome forks? {#firefox-forks-chrome-forks}

I have no qualms using forks of Firefox itself that have better
privacy. [Librewolf](https://librewolf.net) is a privacy focused fork that I've seen mentioned
in a lot of places. Void Linux doesn't offer a package for this
although there is a repo with a [build template](https://github.com/index-0/librewolf-void) for it. I actually
tried to run this build on my laptop but it ended up freezing up
everything. It has sync disabled by default which I think I'm okay
with anyway since it's a Firefox service, although they apparently
encrypt data. But then I'm not sure whether it's really any better
than Firefox. I'm sure there are more such forks for both Android (I
remember using [Mull](https://github.com/Divested-Mobile/Mull-Fenix) which is apparently orphaned now, there was also
Fennec and some others I tried) and Linux.

[Arc Browser](https://arc.net/) seems like a good choice for Windows and I've been using
it instead of Chrome for various work-related stuff. It's not a
Firefox fork, clearly, and they don't have Linux packages either and I
believe this is a fork of Chrome.

Are there really any alternatives that work as well as Firefox did,
without the AI bloat and everything else that's wrong with it?

[^fn:1]: I'm sure there are adequate articles about
    this
[^fn:2]: <https://blog.mozilla.org/en/products/firefox/update-on-terms-of-use/>
