---
title: "Invidious embed instead of Youtube's"
date: 2020-07-26T03:49:20+05:30
tags: ["invidious", "privacy", "youtube", "interlink"]
---

When I thought about writing my blog post titled _[To Zinda Ho 
Tum](https://blog.sahilister.tech/2020/07/to-zinda-ho-tum/)_, I was dilemma. 
Situation being, I couldn't simply copy the poem in my blog. A simple attribution 
wouldn't be enough. Then I remembered about Farhan Akhar's 
[narration](https://www.youtube.com/watch?v=Lni3YbDRmpY) of the poem for the movie 
[_ZKMD_](https://en.wikipedia.org/wiki/Zindagi_Na_Milegi_Dobara). I thought about embedding this video along with my thoughts on it.

Now another dilemma arouse as YouTube even in it's "_Privacy-Enhanced mode_" embed states:

> When you turn on privacy-enhanced mode, YouTube won't store information about visitors on your website unless they play the video.

> — _YouTube[^1]_

[^1]: Text taken from YouTube's embed section. Can be viewed by clicking on video share button, then embed and hovering over **i** icon.

The last part troubled me. If a visitor on my blog views the video, he would be unknowingly feeding their information to YouTube and Google service for ad tracking.

Then I remembered about [Invidious](https://github.com/iv-org/invidious), an open 
source, alternate privacy centric front to YouTube which doesn't track. Delighted, I 
searched how to embed video using Invidious's official instance 
[invidio.us](https://www.invidio.us/) but to no avail. A reply in the forum post finally helped. It said to replace YouTube's URL in the embed code with invidio.us's. Tried and it worked. Now I could embed any YouTube video without Google's tracking.

#### About Invidious

Invidious is an alternative front-end to YouTube licensed under AGPLv3+. Other than 
privacy feature, it supports Audio-only mode, Onion support, Dark mode, doesn't require JavaScript to 
play video, doesn't require Google account to save subscriptions and absolutely no 
ads.

[invidio.us](https://www.invidio.us/) is the official instance. 
List of other public instances can be found [here](https://github.com/iv-org/invidious/wiki/Invidious-Instances). 
Some instances offer downloads too.


#### For Hugo users

Hugo provides shortcodes for 
[Vimeo](https://gohugo.io/content-management/shortcodes/#vimeo), 
[YouTube](https://gohugo.io/content-management/shortcodes/#youtube) and a bunch 
of 
[services](https://gohugo.io/templates/shortcode-templates/#more-shortcode-examples). 
A [shortcode](https://gohugo.io/content-management/shortcodes/) is a simple HTML 
snippet inside a content file that Hugo will render using predefined template. It can 
accept arguments too. For example in our case the link of the video.

Invidious doesn't have a predefined shortcode in Hugo, so we'll go into how I created 
one for this [post](https://blog.sahilister.tech/2020/07/to-zinda-ho-tum/). Let's create:

1. Make a new sub-directory inside `layouts`. Name it `shortcodes`.
2. Inside `shortcodes`, create a file named `invidious.html`. 
3. Define your shortcode HTML inside it.

```html
<div class='embed-container'>
 _ <iframe src='https://invidio.us/embed/{{ index .Params 0 }}'
	 frameborder='0' allowfullscreen>
  _</iframe>
</div>
```
_Notice the_ `{{ index .Params 0}}` . _This accepts the link argument from content file._

Now let's use the shortcode:
1. Inside you're content file, write 
```html
{{ < invidious LINK > }}
```

_Link here only means the alphanumeric text after **"="** in video URL like 
**Lni3YbDRmpY** in <https://invidio.us/watch?v=Lni3YbDRmpY>._

_**Note** — To use above shortcode, there is no space between the curly brackets and side 
arrows like shown [here](https://paste.debian.net/plain/1157847). Writing shortcode triggered my 
shortcode implementation, so had to resort to putting a link._

Learn more about creating your shortcode [here](https://gohugo.io/templates/shortcode-templates/) or see a 
list of codes for some other shortcodes 
[here](https://github.com/spf13/spf13.com/tree/master/layouts/shortcodes) and [here](https://github.com/gohugoio/hugo/tree/master/docs/layouts/shortcodes).

_PS: Now that invidio.us is no longer available, try 
[invidious.snopyta.org](https://invidious.snopyta.org/) or one from the list of [public 
instances](https://github.com/iv-org/invidious/wiki/Invidious-Instances) for the embed._

_PSS: I wrote a The creator of Invidious, Omar Roth stepped away from the project, my thoughts 
about it can be found 
[here](https://blog.sahilister.tech/2020/08/invidious-creator-steps-away-from-open-source/)._
