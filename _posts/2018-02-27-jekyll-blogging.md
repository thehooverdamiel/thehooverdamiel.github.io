---
layout: post
title: Blogging with Jekyll
---

## While a tumblr blog may be 

adequate for some, it's a lot more satisfying as a developer to have the added control and the lower-level system interaction offered by Jekyll. It's shockingly easy to get started with, and it's summarized very well in the [documentation](https://jekyllrb.com/docs/quickstart/), but I want to go through a little of what makes it so easy to use. 

<br>

### 1. Easy to get started-
-provided you're working on a mac. With the ruby infrastructure I've already got from working with Rails, this is total cake. 

From the [quickstart page](https://jekyllrb.com/docs/quickstart/):
```
# Install Jekyll and Bundler gems through RubyGems
gem install jekyll bundler

# Create a new Jekyll site at ./myblog
jekyll new myblog

# Change into your new directory
cd myblog

# Build the site on the preview server
bundle exec jekyll serve

# Now browse to http://localhost:4000
```

A default theme is already in place, and you can begin adding posts and pages immediately. Automatic regeneration of the compiled `./_site` directory will kick on if you add `--watch` at the end of your serve command, updating your local site automatically with any changes (except in your `_config.yml`. You'll have to restart the server every time you make a change there).

<br>

### 2. Simple anatomy
There are a [few files and folders](https://jekyllrb.com/docs/structure/) that hold most of the content for your site. 

- `_config.yml`: So much key information is set here- site title, various variables for footer/header information, many other things. This is the first thing you should look at in your blog, to get it closer to a personalized space.
- `./posts` and `./drafts`: They're what you think they are.
- `./_site`: Don't touch. This is where your site lives after it's built, and it's rebuilt every time it's built. Built built built.
- `./_includes`: Not present in the default structure after you make a new jekll site, but any partials you want to include in your posts/pages you can put here. Syntax to inclue is {% raw %}`{% include file.ext %}`{% endraw %}.
- `./sass`: Also not present by defult, but for adding any sass files you want to `@include` in './assets/main.scss'
- `./_layouts`: Not present in default new project, this is where templates for your content go. You'll specify a layout for each content page you create (discussed below), and each layout you make will likely be an html page with the line {% raw %}`{{ content }}`{% endraw %} (without the plus signs) in it, to show where the content will sit in the template (layout, whatever). 

Some of these are present in a newly built jekyll site, some you'll have to add manually. The default theme is called [minima](https://github.com/jekyll/minima), and is stored somewhere on your system. You can find out where by running `bundle show minima`, and this will also give you a good example of what `./_layouts`, `./_includes`, and other bits of the file structure should look like. 

Any changes you want to make to the default theme you can do by adding layouts and styles to use instead of/override those in the theme, or you can install a different theme. Github is picky about which [themes it can host with its free serving](https://pages.github.com/themes/), but Jekyll has [a lot more options](http://jekyllthemes.org/) if you're hosting elsewhere.

<br>

### 3. Easy updates
You can update the look and feel of your blog all day long if you like, but what's easy and quick as all heck is adding content. 

For any content page, what's most important to start off with is your [Front Matter (TM)](https://jekyllrb.com/docs/frontmatter/). This tells jekyll some basic information about your page, so it knows how to display it, what to title it, and any other important stuff.
{% raw %}
```
---
layout: post
title: A list of sub-par jellies, jams, and preserves
---
```
{% endraw %}

Add this at the beginning of every content file and you'll have all the important information in place for your page to look like it's an actual real not-fake part of your site. 

To add a post:
1. go to `./_posts`
2. add `yyyy-mm-dd-title-of-post.ext`
3. its done you didit nice v proud

To add a page:
1. replace `./_posts` with root in above list
2. title the page like above except no date
3. nice

Any pages you add to the root will be added to the menu bar for the site, so probably use those sparingly, convenient as it is. 

edit: CONFIRMED you can put in [wacky old dates]({{site.baseurl}}{% post_url 1545-11-18-hello-from-grampa %}) but you can't put in future ones. 

<br>

## And that's about it
for the basics at least! There's very simple [code highlighting](https://jekyllrb.com/docs/templates/#code-snippet-highlighting), it's got all the goodness of markdown (and I assume other ways to do basic text but like, really? Other ways?) and for more information on how the tags fit together you can look at Liquid, the template language jekyll uses. It's got [really readable documentation](https://shopify.github.io/liquid/) and is well worth the look. 

