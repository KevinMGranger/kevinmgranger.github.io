---
title: Where is webFS?
excerpt: On side projects and other people beating you to it.
---

[My last post]({% post_url 2015-03-02-curlfs-webfs %}) talked about my plans for webFS / curlFS.
So, where is it?

I looked to one of my favorite pieces of technology -- Plan 9 -- for inspiration.
Plan 9's commitment to simplicity and a full realization of everything-is-a-file is what I wanted to embody with this project.

**[So of *course* they'd already done it.](http://man.cat-v.org/plan_9/4/webfs)**

It's not exactly as easy as "just cat a url", but for good reason.
Plan 9 will not hide things you have to explicitly worry about, like holding open an HTTP connection,
or caching behavior when translated to a file!

Dismayed, I started looking into other side project ideas. I dabbled with some stuff, but now I come back to look at webfs with regret!

Someone has almost always done something in software before you. Truly original, novel ideas are rare. But you can't let that stop you! Side projects are about learning, and having fun.

Today, I resume work on webFS. Probably in Go instead, though. I value simpliciy, don't I?