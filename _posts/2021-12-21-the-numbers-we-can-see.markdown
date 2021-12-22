---
layout: post
title:  "The Numbers We Can See"
date:   2021-12-21 00:00:00 +0000
categories: design
---

# Numbers We Can See

Computers are a lot like calculators: They are machines that take numbers, do something with them, and give other numbers back.

After computers came to exist in the 1950s, people began to realize all kinds of ways
numbers could be used to do different things. For example, numbers can be [used to represent letters](https://en.wikipedia.org/wiki/ASCII).
They can also be used to control other devices, like telling a screen to generate images. Fast forward to now, and these ideas have become
so commonplace that we barely even think about them.

Video games have always been built on computer technology. The earliest things we can call "video games" date back to
[software written on some of the first computers](https://en.wikipedia.org/wiki/Tennis_for_Two) in the 1950s.
The birth of video games as an industry was propelled by the availability of affordable [microprocessors](https://en.wikipedia.org/wiki/Microprocessor),
beginning in the 1970s.

So, video games are built on top of computers, which are built on top of numbers. That means we can think about numbers
as the _essence_ of video games. Just like you and I are essentially made of atoms, everything in video games
is essentially made of numbers.

What does it mean for the developer, and what does it mean for the player?

## How Much Is Visible?

Numbers may be the atoms of video games, but when you look at another person, you don't see each atom making up their body. Instead, you see a person; a
meaningful whole. Even though in our brains we _logically_ understand that everybody is made up of atoms, in our hearts we see each person as a
complete and self-contained being.

There is a similar intuitive leap with games. We do not see them as a collection of rapidly changing numbers, but instead see what the numbers represent.

When a developer is writing the code for their game, they are making all kinds of numerical decisions like "How fast should the player walk?
How high should they jump?" But players think more abstractly, like "Can I outrun this enemy? Can I make the jump?" Players only tend to think
about numbers when they are displayed somewhere on the screen.

This means that there is a lot of power in controlling _which numbers a player sees_! A developer's decisions about displaying numbers has a profound
impact on the player's experience.

Let's analyze an example from _Super Mario Bros._ (1985)

![SMB1-1](https://user-images.githubusercontent.com/775593/147008907-447273bc-c07c-488a-8956-2ab9a6734a64.png)

The player can see four numbers on the game screen: "Score," "Coins," "World," and "Time." At the same time, there are many other numbers you can't see,
such as Mario's X and Y positions, his velocity, the camera scroll offset, and so on.

Each of the numbers the player can see serves a purpose. "Score" and "Coins" tell the player how well they are playing. "World" tells the player how far
they are progressing. "Time" informs them of their limitations.

What if these numbers weren't there? If there were no "Score" or "Coins" visible, then interacting with coins, blocks, and enemies would have
less consequence. If "World" were not visible, the player would not understand where they are in context of the game. If "Time" were not visible,
then the player would die for seemingly no reason when they hit the time limit!

Each of these numbers tells the player something the developer thought they should know, so they can understand the rules of the game.
They also reveal that the developer thought displaying a number was the best way to convey the information to the player.

## Visualization and Intuition

When we consider all the games out there, it's always the case that _some numbers are visible to the player_ and _some are not_. But things are rarely as
cut and dry like in the _Mario_ example.

Developers don't just decide _which_ numbers to show players, they also control _how_ numbers are shown.
Numbers will inevitably be present in games, but effective visualization lets players understand them without having to think too much about it.
This is the principle of _visualization_, and it lets players understand numbers with their _intuition_ instead of their _intellect_.

Visualization is important because players tend to _feel_ more than they _think_. It is only human nature, after all. Ideally, a player can look
at a screen and instantly understand all the information they need, then use that to inform their decisions. In many games, players
are making several decisions every second!

Let's take a look at another example: battle system visualization across _Final Fantasy_ games.

In the first _Final Fantasy_ (1987), only the player characters' HP was initially visible on screen:

![ff1](https://user-images.githubusercontent.com/775593/147013217-3319feda-5c0f-4eb2-9c35-2c7ff8943b5f.png)

You may look at this and think, "Well, how much HP do I have?" In _Final Fantasy II_ (1988), the max HP and MP became visible:

![ff2](https://user-images.githubusercontent.com/775593/147012723-c691b3fd-5f35-4145-9ff1-3e5fbf90556c.png) 

By the fifth entry, _Final Fantasy V_ (1992), the series had moved to an Active Time Battle system. This brought the Time gauge, unfortunately at the loss
of other stats:

<img src="https://user-images.githubusercontent.com/775593/147013386-a1af827c-ee2b-4d21-81ac-b8a6f297f8d1.jpg" height=240>

Then by _Final Fantasy 7_ (1997), all of the core battle stats resurfaced as both numbers and gauges:

![ff7](https://user-images.githubusercontent.com/775593/147012752-1b18f5e5-4feb-45e6-9b2a-e07cc42e6436.png)

It is clear that over the course of 10 years, the developers had shifting ideas about how to help the player understand the state of
the battle. They also were dealing with the ground shifting beneath their feet as they moved through console generations.
Regardless, through experimentation and by balancing needs, they discovered more refined solutions.

Visualization is the lens through which players see and feel the rules of the game, so developers ought to ask,
what is the best way to help players do that? Finding the answer is of course a unique challenge for every game.

These examples show that visualization is an ongoing challenge. The ideal solution may be elusive, or could even demand years of exploration.
It is a developer's responsibility to consider visualization thoughtfully.

## Suspension of Disbelief

Visualization is just one facet of numbers. For every number we see on the screen, there are a lot more pulling the strings behind the scenes.
Sometimes we even get an opportunity to peek behind the curtain, whether that is driven by developers or their player communities.

One such example is [Individual Values](https://bulbapedia.bulbagarden.net/wiki/Individual_values) (IVs) in the Pokémon series. Pokémon celebrated
its 25th anniversary this year, and has iterated on its core series gameplay across nearly 20 entries. But IVs have been part of the formula since
_Pocket Monsters: Red and Green_ (1996).

Put simply, IVs are a Pokémon's base stats for battle traits like Attack, Defense, Speed, and so on. In the earliest games, a Pokémon's
stats at a given level could be determined by a math formula that combined their level with the corresponding IV. But, even though IVs were
so critical to calculating stats, they were completely invisible to the player!

As the series grew in popularity, the competitive player community did as well. Over time, players got together and figured out how the
hidden numbers worked. They also began to wonder why such important numbers were even hidden in the first place!

Game Freak's Shigeru Ohmori, director of _Pokémon Omega Ruby and Alpha Sapphire_ (2014), explains the philosophy behind this in a [2014 interview with
Wired](https://www.wired.co.uk/article/pokemon-interview).

> Each Pokémon does have [Invidividual Values], but I don't consider those data as parameters. I prefer to think of them as real, living creatures. It's the same way that if you have a pet and someone else has the same breed of dog, it's a different dog. That way people can play the game and my Pokemon will be different to your Pokemon even if they're the same type.

As the series progressed, the concept of IVs were expanded upon, and gradually became more visible and available to advanced players. The stat
formulas also became more complex, becaming more influenced by the playtime a player spends with with their Pokémon. Nonetheless, the endurance
of the IV system throughout the series is a testament to the original intent of making Pokémon feel organic, and the effectiveness of hiding
these numbers from the player to suspend their disbelief.

## It's All About The Numbers

Video games are numbers at work! As players, we see some of them directly, while others are hidden from us. Game development entails making all kinds of
decisions about which numbers to convey abstractly, and which to convey concretely. A well-honed game experience is one that finds the right balance.

Don't you wonder, how might you use numbers to express your ideas?
