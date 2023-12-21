# Free Enterprise TODO

This is my (Aexoden) personal list of TODO items for Free Enterprise. Not all of
these ideas may be appropriate for the main repository. Some of them are highly
opinionated, and other opinions may be valid. I may not actually work on any of
these anytime soon or ever. However, I do want to keep track of them for future
reference.

## Architectual Changes

* Eliminate the embedded outdated `lark` library, and replace it with the
  current version installed as a regular Python dependency. I do not currently
  know how difficult this would be, as I have not assessed how much `lark`
  itself has changed or if Free Enteprise has modified its copy.

* Add complete type hinting. This is a massive undertaking that is currently
  responsible for a large percentage of the warnings in my development
  environment. Free Enterprise frequently uses `*args` and `**kwargs`
  constructions which may be more difficult to add type hinting for without
  extensive refactoring. Undertaking this project before 5.x is available is
  probably not the best use of resources, though it may identity previously
  unknown bugs or potential bugs.

* Rewrite the entire project in Rust. This would negate the need for the
  previous two, but would also be an even more extensive project.

## Core Game Features

* Allow the Zeromus sprite to use all three palettes available for monsters,
  expanding available colors from 15 to 45. Note that a given 8x8 tile still
  cannot use more than one palette, so some method of tile allocation and
  optimization is necessary. My [snesimage](https://github.com/aexoden/snesimage)
  tool can help with this, though it currently has a weak algorithm and could be
  improved, though it does produce good results given enough time.

* Implement a new ATB system. The primary intent is to eliminate the advantage
  gained by agility anchoring. Exact implementation details are up in the air.

## Randomizer Features

* Expand the nature of what is randomized. Optionally randomize equipment,
  characters, sprites, and so on. This is a marked change from the randomizer's
  history as vanilla-adjacent, and is likely to be relegated to forks.

* Randomize the PRNG table to prevent encounter manipulation. This could be
  combined with more advanced changes like a global PRNG state that is updated
  each frame to make all potential manipulation frame perfect.
