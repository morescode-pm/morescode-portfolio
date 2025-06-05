---
layout: post
tags: [ai, html, node, cursor, lovable, copilot]
---

I joined an ai for conservation slack group recently. In that group, one of the developers of SpeciesNet ([camera trap computer vision][1]) and the creator of the MegaDetector object detection model, [Dan Morris][2], hosted a "Vibe coding party" this week.  

The tools for agentic coding are developing rapidly - the point of the party was to start learning and using them now, so that in 6 months we have a much better understanding of the landscape.

> "If you are using AI for autocompletion, that’s great, but **if you’re using only AI for autocompletion, you may be at a counterproductive local maximum.**  I.e., you may be better off _not_ using AI for autocomplete if it forces you to re-think how you use AI." - Dan Morris

So, this week I spent some time at the Vibe coding party and afterwards trying to see if AI could help me quickly contribute features to the website that Urban Rivers uses to have volunteers help label camera trap images -- and then for fun, trying to make GAMES!  

## Using Jules on a massive code base for Urban Rivers ranger website.  
The wildmile codebase is > 10k lines of code - written in Next.js with MongoDB integrations. Between Frontend, Backend, Models, Actions, Utils, and Tests, and having not previously contributed to the project or spent any real time learning the languages - I've hit several barriers to being able to contribute.  

We've wanted to expand our rewards and recognition systems to motivate people who are able to contribute daily or weekly - more than just once.

https://github.com/nkwsy/Wildmile/pull/269

## Using claude sonnet 3.5 as a CLI agent to get it running.  
When I first tried to contribute

There was also a problem the first time I tried to submit the PR - my fork of the project was more than 170 commits behind the master branch! This was a gap in my own understanding - when I was merging with the master, I was merging with MY master, not the original. To fix this, all I had to do was hit the "refresh" button on my repo page

## Using cursor and loveable to make a game of tag.  






[1]: {% post_url 2025-05-22-camera-trap-computer-vision %}  
[2]: https://github.com/agentmorris