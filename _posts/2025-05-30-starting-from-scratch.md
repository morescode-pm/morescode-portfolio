---
layout: post
tags: [gettingstarted]
title: Converting from HTML was a project
---


Wow, making a website in Jekyll is great, but it definitely has a learning curve.  
Even after purchasing a domain, figuring out the DNS records for github, and getting an HTML page initially stood up there was still a lot to learn.

Here are the steps I followed on windows:
1.  Download Ruby (with Bundler by default) and Jekyll on Windows  
    - Here's the [Ruby+Devkit][1] for windows install page - I had to use 3.3.8-1
2.  Read a bunch of how to guides that are based on varying deployments of jekyll and jekyll themes
    - Here's a link to the most comprehensive walkthrough when using [github pages with Jekyll][2].
3.  Double check that all software installed correctly in the Path variable.
    - This includes not installing the most up to date version of jekyll because github pages uses an older version. They will likely not update because of stability concerns for users. 
    - Confirm installs with `bundle exec jekyll -v`  and `ruby-v`
    - Very important Gemfile line: `gem "github-pages", "~> 232", group: :jekyll_plugins`
4.  Spend a lot of time figuring out what the _config.yml file does and how to configure it.
5.  Learn about what `gems`, `bundler`, `_layouts` and `_includes` are for and what jinja syntax is being used in jekyll.
6.  More that I thought to myself "wow this would be good to write down" but didn't.

<br>
What you get for all the effort:
 - Strong thematic elements across all pages.
 - A templating implementation to avoid repeating yourself in html.
 - The option to write posts in markdown and html - instead of all html.
 - Examples from other users that you can use to improve your own site.
 - An easy and auto-reloading localhost:4000 testing environment
    - `bundle exec jekyll serve`
 - Ultimately, the knowledge of how to do this again in the future and a fast way to add new projects.



    [1]: https://rubyinstaller.org/downloads/
    [2]: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll