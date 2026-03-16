---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
  - "[[Game Design]]"
---

#empty

# Spellblade Input Idea Taken

So I had this **UNIQUE** and **INNOVATIVE** idea about game mechanics and input.
Took inspiration from input systems such as Vim, Invoker (DotA), and Magicka.

Then I spent a bunch of time polishing and optimizing my idea to make it simpler
and a better overall fit for the type of gameplay I'm looking for.

Had many design drafts, and each of them had its own set of problems to fix.

Also, its helpful to think about other systems and their potential downsides:

#wip Rework this as chapters maybe:

- **Magicka** is amazing, but way too complex, and it uses way too many input buttons.
  It has like `8` different elements to choose from, and if I recall correctly it has
  at least `3` different ways to cast them. So it needs at least `11` buttons to play.
  Again, love that game, but I am looking for something simpler and more fast-paced.
- **Udyr**: #wip
- **Invoker** is one of my favorite and most played heroes in DotA. His input mechanics
  are great, but only for the DotA environment that he is in. Applying the same
  mechanics to a faster game makes them kinda bad, as he requires about 4-5 button
  presses just to cast a single spell. Casting a Meteor goes like this: `E W E R D`.
  Now, one of the buttons can be removed, as when he invokes a spell he actually stores
  it in one of two slots to be used later. Removing that, invoking AND casting Meteor
  could be simplified to `E W E R`. Technically, we can simplify further and remove the
  Invoke button (`R`) itself, which leaves us with `E W E`. That's still 3 presses for
  a single spell. To reduce the button count even further, lets think about whether the
  order of button presses matter. Meteor can be cast with `E W E`, but also `E E W` and
  `W E E`. The order does not matter, it just needs "2 orbs of E and 1 orb of W" to cast.
  With 3 unordered orbs, that allows for `10` different spells. We can make it so that
  order matters, meaning that `E W E` is NOT equal to `E E W`, which will bump the amount
  of spells from `10` to `27`, which is now way too many... or is it? Anyways, with order,
  the `3` orb spell casts combinations would become something like this: `QQQ, QQW, QQE,
QWQ, QWW, QWE, QEQ, QEW, QEE, WQQ, WQW, WQE, WWQ, WWW, WWE, WEQ, WEW, WEE, EQQ, EQW, EQE,
EWQ, EWW, EWE, EEQ, EEW, EEE`. So now we can simplify to only require `2` orbs to cast a
  spell, leaving us with `9` ordered combinations: `QQ, QW, QE, WQ, WW, WE, EQ, EW, EE`.

And there I saw the potential of the system. Using `3` (or `4`) mode buttons, with only two
combinations will result in `9` different spells. It has the benefit of a big spell arsenal,
as well as the simplicity of only requiring `2` presses to launch the spell.

So I started optimizing for that system.

## Optimization Process

## SUDDENLY, MERLIN!

_On two different planets without contact, intelligent species would both eventually figure out what PI is._

#wip

Bruh. Someone actually did it.

#wip

Multiple roads to the top of (THE SAME) mountain.

When designing good systems, we may end up in the same place, unaware of eachother.

#wip

Well what about Merlin, actually? Well I love that.
