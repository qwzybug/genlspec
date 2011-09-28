---
layout: post
title: Stuck in the Middle with Users
blurb: "Apple, Apps, Appeals, & Appeasement: the Story of Drift"
splash_background: "#95a4c1"
splash_color: "#333"
splash_link_color: "#111"
faded_background: "#95a4c1"
faded_title_color: "#333"
background: "#f5f5f5"
title_color: "#333"
body_color: "#555"
link_color: "#95a4c1"
visited_link_color: "#95a4c1"
---

"Artists should use git," Greg told me one day, and I didn't believe him at first. But it's true: the programmer classes have version control, permanent history, easy collaboration, and "The Cloud" while the more creative types are stuck with ~/Desktops full of "Site mockup-round 2 FINAL tuesdayrev.jamesversion #3 actuallyfinal.tweaks.psd" files. (Or Adobe Bridge. Haha.)

But Greg and I saw an out: [github](http://github.com/), a social network purpose-built around versioning and collaboration with stellar usability, and the iPad, the end-user right-brain machine to end them all. Even artists should be able to use git, we reasoned, if properly covered in a glossy coating of iOS! I set to code.

This is the story of how that weekend hack became a summer-long ordeal, as we found ourselves caught constantly on the wrong corner of three-way fights&mdash;reviewers vs. appeals board, Apple vs. GitHub&mdash;that Apple, eventually and inevitably, wins.

### Those Halcyon Days

[Drift](http://permanentmaintenance.com), based on an [early MacRuby hack of Greg's](http://github.com/atduskgreg/drift), was functional in a couple days of coding and won an honorable mention at iPadDevCamp 2010's hackathon. The featureset is pretty simple:

- Edit text files and persist them as GitHub gists (there is no "Save" button)
- Search for other GitHub users, browse their gists, and fork them to edit
- Share links to your documents on github.com
- Use the app anonymously, if you like, or sign in to a GitHub account to associate your documents with that account

<p style="text-align: center"><a href="http://permanentmaintenance.com/"><img src="http://genlspec.s3.amazonaws.com/2011-09-24-drift/diagram-drift.png" alt="The Drift Editor" /></a></p>

We haven't explored the more interesting interfaces of distributed version control, but it's already fun and compelling: a good hack, and a great example of a native/web mashup that's good for all parties.

### 11-13 Split

> *11.13* Apps that link to external mechanisms for purchases or subscriptions to be used in the app, such as a "buy" button that goes to a web site to purchase a digital book, will be rejected.

When cleaning up the app to submit, we took care to hew to Apple's guidelines on accounts and payment links: the app works without a login, and we (naively) only linked at first to the signup page for GitHub's free accounts&mdash;none of the paid accounts give any gist-related benefits, and we considered them orthogonal to our app.

Unsurprisingly, the reviewers disagreed: we were swiftly rejected for violating rule 11.13, quoted above.

Interestingly, the appeals board members assigned to us seemed to be often on our side. For the first rejection they agreed that a link to the free signup page should be alright; for the fourth, they couldn't imagine that a benign read-only link could get us in trouble.

In the App Store parliament, the appeals board is the populist left wing, while the reviewers are the arch-conservative old-guard landed gentry, with power of purse. The process went something like this: on rejection we'd make our case to the appeals board; they'd tend to agree, with minor edits; a week later word would come down that we were, once again, unequivocally rejected.

Through five rounds of rejection and revision, over eight weeks, we and our appeals team kept bowdlerizing our signup links and verbiage to no avail: every week the big red dot would descend again on our iTunes Connect icon, our app's own lickable case of herpes, always accompanied by the predictable, un-annotated text: "In violation of 11.13." It sounded like the reviewers were getting pretty testy, with us and the appeals board, for being thick-headed enough to keep breaking the rules.

Through all this, the appeals board members appointed us seemed as mystified as we were about these sparse, Talmudic rejections. Towards the end we had ripped out nearly every link in the app, when Greg received a call from the board advising us how to proceed. Greg and I chatted on a backchannel:

> Greg: but no links to gh.com that would open in the browser  
> Devin: like, the link to view your gist online?  
> Devin: are they serious?  
> Devin: that's the whole point of the app  
> Greg: urls for individual gists is ok  
> Greg: its ok because it's part of the function of the app  
> Devin: I want you to get him on the record about that  
> Devin: because that worries me  
> Greg: what do you mean "on the record"?  
> Devin: I want to make sure the "View in Safari" link to the individual gist is okay  
> Devin: we don't have any external links in the app outside of that, right now  
> Greg: that's ok  
> Greg: "I don't see any problem with that at all"  

Eventually it became clear that, from the reviewers' perspective, there was a problem with that, at all: it wasn't the (already redacted) signup links that we were being rejected for, but any GitHub link. At all.

### The First One's Free: Whose Users Are Youse? & There Ain't No Such Thing As A Free Account

When operating inside GitHub's system as we do, it is difficult for us not to appear to be constantly shilling for them: every external link we provide is never more than a few clicks away from giving GitHub a couple bucks. In the world of user acquisition, any even tangential linkout to GitHub's pages is tainted by association with their marketing department.

Watch carefully:

<p style="text-align: center"><img src="http://genlspec.s3.amazonaws.com/2011-09-24-drift/diagram-acquisition.png" alt="Diagram: User Acquisition" /></p>

It all makes perfect sense, if you think about it. D&mdash;, our estimable reviewer, explained it aptly. If your users, with their shiny MyWebBookSauceHubsterVille account, come to your app from MyWebBookSauceHubsterVille.com, they're your customers: your marketing got them, you own them, Apple respects that.

If, however, users come to the app from the App Store, they've never heard of MyWebBookSauceHubsterVille before: all they're interested in doing is making their iPad a little more useful. Then, Apple sees them as Apple customers, first and foremost, and Apple wants its cut of the action. You're standing on top of their stack, and that costs 30%.

It's a perfectly bright line, and others in the business of acquiring eyeballs and big cash moneys (Amazon, Conde Nast, Netflix, even scrappy GitHub) can surely see the logic in it. It's Apple's screen; we're all just icons on it.

But (as with so many other of the App Store rules&mdash;no "executable code"? Kurt Gödel called, and he wants to tell you a story...) it disproportionately fucks those of us on the periphery: the kind of people who are interested in mashing up APIs, building interfaces to your data no one's thought of; those of us who just want to sell you a slightly better widget for living online.

### Mashup Smashup & API Apps

As a concrete example: one of the great App Store gold rushes was Twitter clients. What makes our undertaking, a Gist client, different from theirs? Well, largely it's that GitHub has a business model, while Twitter doesn't. Think of that: if Twitter charged a buck a month for their service, instead of aggregating your sentiments to sell to OmniCom and co. to turn into failed viral marketing campaigns, Loren Brichter might still be quietly churning out the most polished iPhone apps in the world; people might meet Craig Hockenberry and exclaim "oh, the Icon Factory! It's so cool to meet a graphic designer at WWDC."

What about the high school kid hacking on a MacRuby iOS app to mash up your Hulu viewing history with your GitHub commits, or seeing how photographing your food correlates with Facebook status updates involving the phrase "single again, sigh", or finding [just the right New York Times crossword to go along with your favorite Kindle vampire novel](http://rexwordpuzzle.blogspot.com/2010/10/1986-brad-davis-film-sun-10-31-10-jazz.html)? People often accuse Apple of "not getting the web"; to the extent that the web these days is about large data silos ceding some control over users' data through APIs, it is frustrating and a bit backwards for Apple to actively discourage developers that don't happen to own the whole user stack.

Apple's position is understandable and defensible: they don't want their [magically reconfigurable glass machine from the far future](http://apple.com/ipad) coopted by grifters and charlatans into a monthly money suck for services of dubious value. 

But like their policies on executable code and virtual machines, invariably some babies are going to get drowned in the drain: for every Adobe Flash trying to suck my battery and fuck with the whole paradigm of native apps, there is a [Scratch](http://blog.scratch.mit.edu/2010/04/scratch-on-iphone.html) or a [Briefs](http://blog.robrhyne.com/post/4179305832/always-a-bridesmaid) that gets accidentally gutshot; for every dull, net-negative-value middleman like Zinio, in the game for nothing more than to resell cheaply scanned PDFs wrapped in shoddy software and a hefty monthly markup, there are going to be a few genuinely interesting ideas lost to the vagaries of customer acquisition and corporate turf wars.

It were ever so.

### Coda: the Crazy Ones

Apple is necessarily conservative in what it accepts: in the world of spectral grays, their levels are way off to the right. To the HackerNews, internet activist types, this makes them seem simply insane&mdash;or, if your dander is especially tumescent and your HN karma needs fluffing, 'evil'.

<p style="text-align: center"><img src="http://genlspec.s3.amazonaws.com/2011-09-24-drift/diagram-the-world.png" alt="Diagram: the World, to Apple and The Internet At Large" /></p>

They aren't, but they do not compromise, and their opaque, upside-down judiciary can seem architected especially to present a Phil Dick Empire-Never-Ended impenetrable brick wall of callous confusion. The appeals board is more a pool of state-appointed defense attorneys than authoritative circuit courts, while, as far as anyone can tell, the reviewers remain an [untouchable caste](http://daringfireball.net/2009/05/diary_of_an_app_store_reviewer): faceless, inscrutable, impenetrable, infallible.
 
Drift isn't going to be the next FarmVille or Instagram. I'm not terribly bitter about the knuckling-under we've done to get it on the store, though I do think our users have ultimately suffered for it. But the amount of ground we've had to give (from a starting position which I think most people would find fairly reasonable), while the reviewers have done little more than dig in and ask for more, is a little worrisome.

Apple's not crazy, or evil; they're just looking out for themselves, like all of us. But at the same time, it doesn't seem like they're equipped to compromise. People who don't compromise turn crazy, or at least they lose all their friends.

Our idea wasn't especially groundbreaking or interesting: it's just a relatively well-done mashup of native client and web API. What about the really great, crazy new ideas&mdash;how well will they stand under such withering review?

_Drift is on the [App Store](http://itunes.apple.com/us/app/drift-editor/id454838524?mt=8), and is under [Permanent Maintenance](http://permanentmaintenance.com/)._
