---
layout: post
tags: [ai, html, next.js, css, copilot]
---

I joined an ai for conservation slack group recently. In that group, one of the developers of SpeciesNet ([camera trap computer vision][1]) and the creator of the MegaDetector object detection model, [Dan Morris][2], hosted a "Vibe coding party" this week.  

The tools for agentic coding are developing rapidly - the point of the party was to start learning and using them now, so that in 6 months we have a much better understanding of the landscape.

> "If you are using AI for autocompletion, that’s great, but **if you’re using only AI for autocompletion, you may be at a counterproductive local maximum.**  I.e., you may be better off _not_ using AI for autocomplete if it forces you to re-think how you use AI." - Dan Morris

So, this week I spent some time at the Vibe coding party and afterwards trying to see if AI could help me quickly contribute features to the website that Urban Rivers uses to have volunteers help label camera trap images -- and then for fun, trying to make GAMES!  

## Using [Jules][8] on a massive code base for Urban Rivers [ranger website][9].  
The wildmile codebase is >45k lines of code - written in Next.js with MongoDB integrations. Between Frontend, Backend, Models, Actions, Utils, and Tests, and having not previously contributed to the project or spent any real time learning the languages - I've hit several barriers to being able to contribute.  

We've wanted to expand our rewards and recognition systems to motivate people who are able to contribute daily or weekly - more than just once.  There's already a system to add badges - which as an admin I've been able to add to. For example, Here's one you get after labeling 9000! images along with 700 points - generated using chatGPT image mode:  

<img src="/assets/images/ai-part-one/1_exbadge.png" width="200">

I have this idea that by logging in weekly, people will be 'taking care of the river.'  Conceptually, we can create a 'tomagachi-pal-like' image of the river, and each week the picture shared gets prettier, until it looks like a very nice, boardwalk lined, wetlands environment.  This then could be picked up as a sticker from Urban Rivers - or mailed - or awarded at a social.  

The existing system was struggling with login cookies so we decided to change it to an "actions" based system - where any valid action (labeling observations) within a day is considered an active day and can increase the streak.

Here's what I prompted Jules with:  
> we have a series of cards that display the user progress and update the streak ex:
>```
>UserProgressSchema.methods.updateStreak = function () { const today = new Date(); const lastLogin >= this.streaks.lastLoginDate;
>
>if (!lastLogin) { this.streaks.current = 1; } else { const daysSinceLastLogin = Math.floor( (today >- lastLogin) / (1000 * 60 * 60 * 24) );
>
>if (daysSinceLastLogin === 1) {
>  this.streaks.current += 1;
>  this.streaks.longest = Math.max(
>    this.streaks.current,
>    this.streaks.longest
>  );
>} else if (daysSinceLastLogin > 1) {
>  this.streaks.current = 1;
>}
>}
>
>this.streaks.lastLoginDate = today; };
>```
>Instead of using the login date, we want to create a function to update a parameter about the user based on their last action on our site - a valid action would be saving an observation. Please make suggestions on how to implement this

From there, Jules read in the entire codebase (I provided credentials), built a plan to edit the function, edited the 3 very specific files needed to change the feature, and - in noticing our lack of tests - added steps on how to implement an entire testing ecosystem.  

Here's a screengrab of where it shows the changes suggested:  
<img src="/assets/images/ai-part-one/3_jules.png">

I pulled the branch into my local env to test out the changes and it loaded. Now, the test system didn't work at all - but I do plan on getting jules to help with that again in the near future.

As of today, Jules is using Google Gemini 2.5 Pro.  

See the [commit][3] here!


## Using claude sonnet 3.5 as a CLI agent to get it running.  
When I first tried to run the website locally to see if my changes worked, I couldn't get the system running at all. After several chat prompts with an AI - I did manage to get something running - only to realize that the wrong drive was being used and needing to start over.  

There was also a problem the first time I tried to submit the PR - my fork of the project was more than 170 commits behind the master branch! This was a gap in my own understanding - when I was merging with the master, I was merging with MY master, not the original. To fix this, all I had to do was hit the "refresh" button on my repo page.

After all of that - pulling the changes and syncing my main branch into my local server - I experimented with Claude Sonnet 3.5 in copilot within VSCode. The difference here being that the CLI version of the AI is able to see what my computer is (Windows) and how incompatibility issues with linux were causing the problems. It fixed things instantly.  

<img src="/assets/images/ai-part-one/4_copilot_claude.png">

Given, this may have only taken a few google searches, but it's something Jules was incapable of knowing - because Jules is entirely online on a VM.

## Using copilot and claude to make a game for elephant conservation.  
In the last 30 minutes of the vibe coding party I suggested we all try to use AI to make a game - for fun & to see how 'one-shot' prompting works these days (this was one of the ideas Dan had originally conceived for the party).  The premise for the game came from another conservation member - [Prabath Gunawardane][7] - who was interested in creating a game that helped teach how elephant friendly deterrents could help prevent farm damage.

Here was my [prompt and chat log][6] to claude:  
> I would like to make a game I can run in my local browser called "Elephriend Zone" - it's a game where elephants will be drawn to farms nearby and could damage them - damaging the farms is a game over condition - the player can build elephant safe de-motivation items on the map - please look up some elephant friendly options for this. For art we can start with simple shapes. Pick any language that is known to be low bandwith and run on a slow computer.

And here's [the repo][4] & screen shot of the..
### **[Elephriend Zone][5] game you can actually play**:   

<img src="/assets/images/ai-part-one/5_elephriends.png">

## In Summary  
The most incredible part of all of this was that I only had to (barely) review the code, and figure out testing/deployment strategies. When you think about the time it would take to learn new languages just to be able to make one small change (months). This is truly an amazing thing.  


<!-- links  -->
[1]: {% post_url 2025-05-22-camera-trap-computer-vision %}  

[2]: https://github.com/agentmorris
[3]: https://github.com/nkwsy/Wildmile/pull/269
[4]: https://github.com/morescode-pm/elephriend-zone
[5]: https://morescode-pm.github.io/elephriend-zone/
[6]: https://github.com/morescode-pm/elephriend-zone/blob/main/development-chat-log.md
[7]: https://www.linkedin.com/in/prabath/
[8]: https://jules.google.com/
[9]: https://rangers.urbanrivers.org/