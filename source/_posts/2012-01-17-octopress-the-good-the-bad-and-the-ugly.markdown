---
layout: post
title: "Octopress - the Good, the Bad and the Ugly"
date: 2012-01-17 17:11
comments: true
categories: ruby, gem, octopress
---

{% img left /images/blog/octopress.png Octopress logo %}

To inaugurate my blog, I decided that I am going to review the tool, which I use to manage it - [Octopress][octopress], the self-proclaimed "blogging framework for hackers".

I have been using Octopress to manage the [Software Craftsmanship in Kraków][sckrk] blog for a couple of months now, and now I decided to use it for my personal blog.
This post will explain why I chose it, and what I don't like about it.

<!--more-->

##TL;DR

Octopress is great for programmers who want to take advantage of GitHub or Heroku for hosting their blog, it requires very little setup and comes "with batteries included".

However, it should be made into a gem, because forking the project on GitHub and working on the same source tree as the developer feels more than a bit "hackish".

## Using Octopress

Octopress is a static site generator, that specializes in blogging, as oposed to some other solutions like [Nanoc][nanoc], which are more generic in nature.

If you want to use Octopress, you should either fork the repo on GitHub or add it as a remote to your existing repository.
After that all you need to do is invoke <code>rake install</code>, modify a few config values and you are ready to start adding content.

Deploying to various destinations can be done with <code>rake deploy</code> after some setup.
The setup modifies the Rakefile that comes with Octopress, which in turn generates conflicts when you update later.
Out of the box, Octopress supports GitHub Pages, Heroku and Rsync as deployment options.

## The good

The very best feature of Octopress is the "batteries included" approach, which I mentioned earlier. 

It comes with a bunch of plugins, like Twitter and GitHub integration, Disqus comments, deployment tasks and others.
The default template is mobile friendly, and will adjust according to the screen size.

Having so much from the get go saves you quite a lot of setup compared to some other solutions, so you can have a blog live in minutes after you install the tool.

Compared to Wordpress, Octopress is also much easier to customize, and the templates are much cleaner - it uses Mustache for templates and SASS for styles.
Also using Markdown for composing posts and VIM (does not come with Octopress;) for editing them is much more convenient than Wordpress's WYSIWYG editor.

As a static page generator, Octopress also has the advantage of easily backing up the blog content and versioning it, especially compared to the database backed tools like Wordpress.
Now I have an (almost) full copy of the blog data everywhere I check it out and on GitHub.
This is a huge win, because you don't want to worry about loosing your data.

Another great thing about Octopress is Solarized theme for syntax highlighting.
Check it out:

```ruby Sample of syntax highliting
def hello_world
  puts "Octopress is awesome!"
end
```

## The bad

The biggest downside of Octopress for me is that [almost][blog1] [every][blog2] [blog][blog3] [which][blog4] [uses][blog5] [it][blog6] [looks][blog7] [almost][blog8] [exactly][blog9] [the][blog10] [same][blog11].
You can customize colors very easily and even modify the templates that come with the default theme, but modifying colors is usually the biggest change most people (including me) make.

Octopress comes with only one theme, and different ones are not easy to find.
Thankfully the default one looks nice and is very well done.

Compare this with Wordpress, which has thousands of templates readily available, and your biggest problem is finding the right one.

## The ugly

Right now, Octopress encourages you to fork the project to use it.
Whenever you want to update the "library", you have to merge or rebase the remote changes and since there are no release tags, you most likely will do it against master.
You will also probably run into some conflicts, because some core files, like Rakefile, need to be modified to store configuration.

In my opinion Octopress should move to the same model that Nanoc uses.
It should be a gem, which is easily installable and upgradeable, and only the customizable files should go into the user's project directory.
Instead of using Rake, it should provide its own commandline tool to accomplish common tasks like deployment or compiling the content.

## Conclusion

Octopress is a great tool for programmers that want to start blogging without having to worry about customizing some static page generator or Wordpress.
It comes with beautiful syntax highlighting, responsive layout and useful plugins for integrating with applications like Disqus and Twitter.

The downside is that you should spend some time to customize the layout and styles, because most of the blogs that use it look very similar.

[octopress]: http://octopress.org
[sckrk]: http://sckrk.com
[nanoc]: http://nanoc.stoneship.org/ 

[blog1]: http://sciruby.com/
[blog2]: http://www.telenet.com.au/
[blog3]: http://jcsims.me/
[blog4]: http://www.mariovisic.com/
[blog5]: http://hairysun.com/
[blog6]: http://yagnesh.org/
[blog7]: http://nomedojogo.com/
[blog8]: http://trucsdedev.com/
[blog9]: http://duffomelia.com/
[blog10]: http://depth-first.com/
[blog11]: http://www.uru.ch/
