+++
title = "Potentially returning to Sourcehut and my FOSS roots"
author = ["peregrinator"]
date = 2025-03-09T19:36:00+05:30
draft = false
series = "Blogging with Emacs"
bsky = "https://bsky.app/profile/peregrinator.site/post/3ljxapqi2j22q"
+++

I wrote about why I'd been considering [moving back to Github](/blog/2025/02/the-sourcehut-builds-dilemma/) to host
the source code for the blog last month and talked about why Sourcehut
builds and the [restrictions](https://srht.site/limitations) on content were my primary motive. I also
mentioned the changes I'd made to the website itself, including the
Bluesky comments section I'd added to posts. I, however, had second
thoughts about the whole move, what with the new theme and all its
fancy features, very few of which I actually used and how the shift
back to Github meant that I was giving up on the completely open
source services offered by Sourcehut for the not-very transparent
service offered by Github.

[The theme](https://github.com/jpanther/congo) looked nice, with all the soft pastel colours and the fancy
CSS but I had really not had a chance to go through most of the code
myself. Going back to the theme's repo, I see now that there is a
[little bit of JavaScript](https://github.com/search?q=repo%3Ajpanther%2Fcongo++language%3AJavaScript&type=code) too. Now, it's not that _all_ JS is bad but
when I'd started this website and blog, I'd decided that I wouldn't
use any of it, especially for wholly unnecessary things such as
appearances because I just am not familiar enough with it. I just
wanted a very basic, functional site which was lightweight and easy to
maintain. So I set out again, scouting for themes that seemed to offer
this — a minimal look and something very basic I could build on — and
came across a few.

[Mini](https://github.com/nodejh/hugo-theme-mini) seemed like something easy to work with and I gave it a shot but
it turned out to be really badly maintained and a lot of it wasn't
updated to work with newer Hugo versions. I saw that the repo had
multiple open pull requests for fixes that just hadn't been looked at
by the maintainer. And it just kept throwing errors every time I tried
to run a local Hugo server to see if it worked. I actually ended up
spending most of my time fixing them. It also didn't have a dark
theme, something which I would've liked.

[Etch](https://github.com/LukasJoswiak/etch/) was a theme I'd tried out when I initially started out with this
blog, after switching to Hugo and my whole Emacs-based setup. I had
discarded it for something based off [Drew's website](https://drewdevault.com/). But looking at
[Neil's blog](https://neilzone.co.uk/), which I'd come across while searching for something, I
realised that I could make this work. It was just after I'd put in the
final touches on the Congo theme setup that I got the pangs to go back
to a ridiculously simple theme such as this. I took a while to make up
my mind and then made the jump after showing it in action to a few
people.


## Changes to the theme {#changes-to-the-theme}

I had made a few changes to make the theme work for me. It had a
landing page that listed out all posts but it used a very odd set of
layouts for this. An `index.html` template that called the `posts.html`
partial which in turn used a ridiculously simple code that had `li.html`
from `/layouts/_defaults/` render a list of posts. I modified the
`posts.html` template such that the list generated would organise posts
by year of publishing, in an "archives" sort of fashion. I didn't like
how the article date was part of the link too so I moved it out of the
`<a>` tag.

```html

{{ range (.Paginate ((where .Site.RegularPages "Type" "in" .Site.MainSections).GroupByDate "2006")).PageGroups }}
<h2> {{ .Key }} </h2>

<ul id="posts">


  {{ range .Pages }}
  <li>
    <a href="{{ .Permalink }}"> {{ .Title }}</a>
    <small><time>{{ .Date | time.Format (i18n "posts.date") }}</time></small>
  </li>
  {{ end }}

</ul>
<br>
{{- end }}
```

I also didn't like the default date format so I changed it by added
`/i18n/en.toml` with dates formatted in my preferred style. This is
actually part of the theme's [wiki](https://github.com/LukasJoswiak/etch/wiki/i18n). I also added a layout for the
[fiction](/fiction) section that was more-or-less like the default but with the
date on the list outside the hyperlink tag like with the template for
the homepage.

I added a very basic "info" line indicating posts that were part of
series on the top of articles (it was called in the `single.html`
template). The series template I ended up using was ridiculously
simple unlike the ones I found online which had too many features like
those that listed out articles in the series, which I didn't feel like
I needed, considering that the theme already generated a list of these
in the taxonomies.

```html

{{ if .Params.series }}
<div class="info">

  <p>This article is part of the <a href="/series/{{ .Params.series | urlize }}">{{ .Params.series }}</a> series.</p>

</div>
{{ end }}
```

I was on the fence about comments, which was a crucial part of why I'd
moved to Github, but I settled for a very basic link to the Bluesky
post and a link to reply to the post to my public inbox which I'd set
up a while back on Sourcehut lists. I think I'm happy with how this
looks now.

I added the [openring](https://git.sr.ht/~sircmpwn/openring) template from earlier, making it very simple and
without almost any formatting (I even removed a bunch of styling
elements I'd worked on from the CSS). Finally, I added a header-like
footer menu to display important social links and added a link to my
newly created [privacy](/privacy) page that basically talks about how I respect
everyone's privacy and don't offer cookies and the like. The RSS link
is also down there now.

The font is as always, [Monorale](https://github.com/samvk/monorale-raleway-sober) and the code blocks have Prot's [Modus](https://protesilaos.com/emacs/modus-themes)
theme, like what I had on my own Emacs until recently.


## Issues with Sourcehut builds {#issues-with-sourcehut-builds}

I had initially tested this out on the Sourcehut page that I got with
my account and encountered a weird issue while building the
site. Sourcehut builds would get stuck at the same point every time I
pushed a commit to the repo — it was [while openring was being run](https://lists.sr.ht/~sircmpwn/sr.ht-discuss/%3CtMVFgp8GaDoesSDCvSDPa67dbKRxx-o-UWlVVDLBrMNkp3m-hGsMLU1bJ1wd4GE7rHjk8OzLU7Tex0Ko9e5jGM1Y5qu52Sb-ODc_drZDsXk=@protonmail.com%3E) —
and I testing a few things out with this. It looks like it's got to do
with feeds from WordPress blogs and I think it's because RSS feeds
from those aren't part of the blogs themselves and rather seem to be
files that are downloaded. This doesn't seem to be an issue if I run
the openring command from my terminal emulator or on Github and so I'm
sticking to it for now, atleast until we find a fix for this on
Sourcehut builds.

Well, that's it for now. I hope to get back to writing that article
I'd started on skramz last month but at this point, I have no idea
when that'll be ready.
