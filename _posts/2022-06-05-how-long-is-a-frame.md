---
layout: post
title:  "How Long is a Frame?"
date:   2022-06-05 00:00:00 +0000
categories: design
excerpt_separator: <!--more-->
---

I've recently stumbled upon a topic that differs greatly depending on the backgrounds
of different game creators. It's a fundamental question of time; namely, should time
be measured in terms of seconds, or in terms of frames?

I am a stalwart defender of frames... but I still think seconds
have their use. As for you, let's dive into the merits of both, and then see how
you're feeling!

<!--more-->

## The Usual Defense of Seconds

I understand the appeal of seconds, I really do. They are a natural, universal
way to measure a relatively short interval of time. A second is 1/60th of a minute,
which is 1/60th of an hour. The arguments I hear in favor of seconds generally focus
on this point: that seconds are common and natural to understand.

There are other benefits to seconds too... for example, it's easy to hop online and
find physics equations that are in terms of some value per second. But these
benefits still tend to reinforce a bias of familiarity with the second. 

Just because seconds are intuitive to most people does not mean a second is always
the best way to express intervals of time in game design.
That familiarity bias can even impact our ability to perceive time in more
granular intervals.

## Where Seconds Break Down

_(For these examples, I am hacking around with some JavaScript code by [Richard Davey](https://twitter.com/photonstorm) I found [here](https://phaser.io/tutorials/coding-tips-007))_

Let's say we are making a shoot-em-up game, and we have a spaceship that needs
to shoot rapid fire projectiles. To start off, let's make so where if you hold the fire button,
it shoots 1 bullet per second:

<img src="/img/frames_1shotpersecond.gif">

When you see this animation, you'll immediately think "Wow, those bullets need to shoot a lot
faster!" So let's try them faster... instead of a bullet every 1 second, let's do a bullet every
0.5 seconds:

<img src="/img/frames_2shotspersecond.gif">

Still a bit slow! It really only starts feeling naturally like a shoot-em-up game once we get
the shot interval down to 0.125 seconds:

<img src="/img/frames_8shotspersecond.gif">

When we're dealing with gameplay actions, especially ones that need to respond to a button
press, game feel is determined by changes that transpire over the course of fractions
of a second.

This means that insisting on measuring with seconds means that the programmers and
designers are going to be juggling a lot of fractional numbers! Fine tuning these very
quick gameplay actions often means deciding over the difference between numbers like 0.2 and
0.25 seconds.

That's where the familiarity benefit starts to crumble. While one may be able to easily discern
the difference between 1 and 2 seconds, can one just as easily discern the difference between
0.2 and 0.25 seconds? For most people, fractional differences between numbers seem negligible.
So, these seemingly tiny values hinder one's ability to perceive the difference between them.

## Re-Framing Our Perception

What do I mean by "frame" exactly? In a time sense, a frame is the time a game takes between 
drawing a screen and drawing the next screen after it. How many seconds this is depends on the
**frame rate**, but in common practice we are dealing with **60 frames per second**.
This means we are dividing each second up into 60 parts.

To convert 1 frame at 60 FPS to seconds, the math works out like this:

<div style="text-align:center;">1 second / 60 frames = <i>~0.01667 seconds per frame</i></div>

When we recalibrate our perception to declare **1** as a much shorter unit of time,
negligible fractions suddenly become substantial intervals.

Our 1-second shot from earlier is a shot every 60 frames. Our 0.5-second shot is a shot every
30 frames. Now the numbers we are seeing better match the "feeling" of those too-long intervals.
In the end, when we settled on 0.125 seconds, those shots were firing about every 8 frames.

## Feeling The Difference

_(For this section, I got the GIFs from
[this imgur link](https://imgur.com/r/StreetFighter/aShg9f8),
and the frame data from [EventHubs](https://www.eventhubs.com/guides/2009/apr/18/sakuras-frame-data-street-fighter-4/))_

I'd be remiss if I talked about frame timing without bringing up fighting games.
In fact, I'd say my own tendency to think in frames is heavily influenced by being
a fighting game fan.

In fighting games, the action unfolds quickly, and a lot can happen over the course
of a second. Hardcore players pore over **frame data**, which is information
about how long attacks take, the position of hitboxes and hurtboxes during
the attack animations, and how much damage those active hitboxes deal to opponents.

As a rule of thumb in fighting games, slower attacks which take longer to execute tend
to do more damage than faster attacks that can be thrown out more rapidly.

In the **Street Fighter** series, attacks are divided into three grades: Light,
Medium, and Hard. As a case study, let's look at three grades of Sakura's
_standing far punch_ attacks in **Street Fighter IV**.

Sakura's Light Punch (LP) animation takes 10 frames and does 25 damage:
<img src="/img/frames_sakura_lp.gif">

Her Medium Punch (MP) animation takes 22 frames and does 75 damage:
<img src="/img/frames_sakura_mp.gif">

Her Hard Punch (HP) animation takes 28 frames and does 110 damage:
<img src="/img/frames_sakura_hp.gif">

Although we are ultimately dealing with a difference of 18 frames (0.3 seconds) across all
three attacks, you can feel the difference in speed and weight among them. You can
throw two LPs in the time it takes you to throw one MP!

Once you start to tune in to the differences of frame timings, you can start to train 
your sense of "how long a frame is." I recommend reading Masahiro Sakurai's [Famitsu column on
this subject](https://www.famitsu.com/news/201904/24175091.html) (Or [Source Gaming's
English translation](https://sourcegaming.info/2018/05/18/learn-to-count-frames-sakurais-famitsu-column-vol-552/)).

## Settling The Great Debate

Hopefully now, you can see some benefit to thinking about time in frames if you didn't
before. So now we're all 100% frame-thinkers, right?

Well of course, nothing is ever that cut and dry. In a practical sense, you may want
to take advantage of differences in perceiving seconds vs. frames.

At my studio [Evening Star](https://eveningstar.studio/), we accomodate both approaches 
in our **Star Engine**. We have a delta-time value programmers can use called
`Time.deltaSeconds`, which is generally `0.01667` when running at 60 FPS. We also
have a value called `Time.deltaFrames`, which is `1.0` when running at 60 FPS. We
use either-or to drive timers depending on the context.

For most people, numbers between 1 and 100 are easiest to think with and visualize.
To play into this natural inclination, we generally use this rule of thumb:
**favor expressing "fast" intervals less than 1 second in frames** (which avoids fractional
second values),
and **favor expressing "slow" intervals longer than 1 second in seconds** (which avoids large
frame values). One may show up a lot more often than the other depending on the nature
of each game.

Either way, it is useful to develop your perception of frames, because they have the
power to help you make the most out of timing details!