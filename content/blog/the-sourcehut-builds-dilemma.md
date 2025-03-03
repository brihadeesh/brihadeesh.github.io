+++
title = "The Sourcehut builds dilemma"
author = ["peregrinator"]
date = 2025-02-15T14:32:00+05:30
draft = false
series = "Blogging with Emacs"
bsky = "https://bsky.app/profile/peregrinator.site/post/3li7fx3v4m22d"
+++

I've been deploying this blog using Sourcehut builds from my Sourcehut
repo for some time now but I've started to have doubts about whether I
want to stick to this given the [limitations](https://srht.site/limitations) on Sourcehut pages. I've
not had to thing about this a lot until recently since I also switched
up my Hugo theme to [Congo](https://github.com/jpanther/congo), which has a few additional features. These
in turn inspired me to incorporate comments from Bluesky too but this
didn't work on the version of this site deployed from my [Sourcehut
repo](https://git.sr.ht/~peregrinator/peregrinator.site). I've anyway been working on other things on the blog so I
decided to fix this and rearrange how I present the blog a little
while at it.

So now the blog is split into two parts: the main blog, of which you
can see articles like this one, and the [Emacs blog](https://emacs.peregrinator.site/) on a
subdomain. This part of the blog is hosted on my Github and deploys
with Github Pages to allow Bluesky comments adopted from [Kaushik
Gopal's blog post](https://kau.sh/blog/bluesky-comments-for-hugo/).


## Comments from Bluesky {#comments-from-bluesky}

It has a very basic setup. There is a [`comments.html`](https://github.com/brihadeesh/peregrinator.site/blob/main/layouts/partials/comments.html) partial in
`~/layouts/partials/` that basically just references a JavaScript script
at `~/assets/js/bsky-comments.js`. The comments partial is as displayed
below. It is a very basic HTML script with Tailwind CSS built in.

```html

<div
  id="comments-bsky"
  data-bsky-uri="{{ .Params.bsky }}"
  class="group-dark:hover:text-primary-400 transition-colors group-hover:text-primary-600"
>
  <div id="comment-post">
    <h2 class="comment-post-header font-semibold">
      Comments via Bluesky
    </h2>

    <div class="comment-post-meta text-sm">
      <a
        class="comment-post-meta-actions text-neutral-700 transition-transform hover:-translate-x-[2px] hover:text-primary-600 dark:text-neutral dark:hover:text-primary-400"
        href="#"
        target="_blank"
      >
        <span id="likeCount">0</span> likes |
        <span id="repostCount">0</span> reposts |
        <span id="replyCount">0</span> replies
      </a>

      <p class="block">Join the conversation on
        <a
          id="comment-post-meta-reply"
          class="font-semibold text-neutral-700 transition-transform hover:-translate-x-[2px] hover:text-primary-600 dark:text-neutral dark:hover:text-primary-400 hover:underline hover:decoration-primary-500"
          href="#"
          target="_blank"
          >Bluesky</a>
      </p>
    </div>
  </div>

  <div id="comments-container"></div>

  <template id="comment-template">
    <div class="comment flex items-start space-x-2 m-20 my-10">
      <div class="avatar pt-2 w-[50px] h-[50px] flex-none">
        <a class="avatar-link w-full" href="" target="_blank">
          <img
            class="avatar-img rounded-full overflow-hidden w-[50px] h-[50px] object-cover"
            src=""
            alt="avatar"
          />
        </a>
      </div>

      <div class="comment-body text-sm m-20 p-10">
        <a class="author-link font-semibold text-neutral-700 transition-transform hover:-translate-x-[2px] hover:text-primary-600 dark:text-neutral dark:hover:text-primary-400 hover:underline hover:decoration-primary-500" href="#" target="_blank">
          <span class="author-name" title=""></span>
        </a>

        <p class="comment-text text-primary"></p>

        <div class="comment-actions text-xs text-neutral-500 transition-transform hover:-translate-x-[2px] hover:text-primary-600 dark:text-neutral dark:hover:text-primary-400">
          <a class="actions-link" href="#" target="_blank"></a>
        </div>
      </div>
    </div>
  </template>
</div>

{{ $comments := resources.Get "js/bsky-comments.js" }}
<script src="{{ $comments.RelPermalink }}"></script>
```

It has a very simple working principle. It gathers comments using the
JS script from a regular Bluesky post that references the article at
hand, the link to which is provided in the Org metadata for the
article as

```yaml

:bsky "https://bsky.app/profile/peregrinator.site/post/3li7fx3v4m22d"
```

for example for this page.

The [`bsky-comments.js`](https://github.com/brihadeesh/peregrinator.site/blob/main/assets/js/bsky-comments.js) script is a little longer so I won't be
displaying it here. It is more or less unmodified from that provided
on Kaushik Gopal's Github.

The comments partial is called from the [`single.html`](https://github.com/brihadeesh/peregrinator.site/blob/main/layouts/_default/single.html) template in
`~/layouts/_default`.


## Other changes, and those planned {#other-changes-and-those-planned}

I've updated my [about page](/about.md) with a little more about myself and my
publications. There are now photos of Goose, my cat, too. I am
considering putting up a gallery of some of my photos on this
site. Perhaps as a subdomain like with my Emacs blog. There's
hopefully a lot more to come!

{{< figure src="/images/bougainvillea_night.jpg" alt="a blooming Bougainvillea tree at night" caption="A blooming bougainvillea tree at night. Photo by Brihadeesh S, April 2023" >}}

In other news, I've moved to a new theme for the blog. I now use a
fully personalised version of the [Congo](https://github.com/jpanther/congo) theme. So now there's an
optional dark theme too. The blog also uses a new typeface: [Monorale](https://github.com/samvk/monorale-raleway-sober),
a font based on [Raleway](https://github.com/impallari/Raleway). I find it a lot more comfortable for reading
online.
