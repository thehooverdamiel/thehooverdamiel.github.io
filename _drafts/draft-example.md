---
layout: post
title: Draft Example
---

## This is a draft!

When I run `bundle exec jekyll serve --drafts`, the site will display with these drafts, but the drafts don't get a date in their name until they become a page. ([source of that learned info](https://gist.github.com/benbalter/5555992))

So just to be very clear about it, when making a draft, it looks something like this:

`./_drafts/a-cool-draft.ext`

You can preview it locally by running `jekyll serve --drafts`.

When you want to publish the draft, you move it to your posts directory and give it a date, so it looks more like this:

`./_posts/2018-03-22-a-cool-draft.ext`

And that publishes your post. Hooray!