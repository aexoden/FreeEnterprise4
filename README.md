# FreeEnterprise4

This is my personal modification of Free Enterprise 4.x. It is currently
primarily for experimentation and analysis. The changes are not necessarily
limited to a single topic, nor are they in any particular order. Some of the
changes may be inappropriate for eventual merge to the main repository.

As this repository is forked from the open source release of Free Enterprise 4.x,
it currently carries the same omissions:

* The Z sprite and harp songs databases are not included, though the tools to
  generate assets in the correct format are.

* The dwarf job list is omitted; should you wish to create your own, this is a
  simple text file with one job per line.

* Passwords, encryption keys, and similar secrets used in any public deployment
  are excluded.

## Initial Setup

I am not currently necessarily working on a robust setup. What works in my
environment may fail spectacularly in yours. The original repository requires at
least Python 3.7, but I exclusively code with Python 3.11+, so you can assume
this repository will also require Python 3.11+.

1. Clone the repository to a convenient location.
2. In the root directory of the repository, create a virtual environment with [Poetry](https://python-poetry.org/).

The web server requires an installed MongoDB, and Floating IPS installed inside
`FreeEnt/server/bin`. The files should be named `flips.exe`, `flips-linux` or
`flips-mac` according to your environment.

## Usage

All modes of running Free Enterprise tools require specifying a path to an FF2
US v1.1 headerless ROM (not supplied in this repo).

Always run with the virtualenv active.

### Command line generator

From the repo root directory: `python -m FreeEnt <rompath> make -h`

### Web generator

Note as mentioned above that MongoDB must be installed to use the web generator,
and you must have downloaded the Floating IPS binary to `FreeEnt/server/bin`.

From the repo root directory: `python -m FreeEnt <rompath> server --local`

Then navigate in a browser to `localhost:8080`.

### Tools site

From the `fetools` directory: `python tool_site.py <rompath>`

Then navigate in a browser to `localhost:8082`.

### Contributors

Free Enterprise was made possible using the extensive technical research and
knowledge of PinkPuff, Grimoire LD, Chillyfeez, and Aexoden. This repo contains
code written and designed by b0ardface/HungryTenor, Crow, Myself086, Myria,
mxzv, and Wylem. It also contains the graphic design work of SchalaKitty and
Steph Sybydlo. It is based on the game design work of riversmccown and mxzv. And
while their specific assets are not included in this repo, the musical work of
Xenocat and Calmlamity contributes extensively to Free Enterprise, and was
formative in the development of tools contained here.

### License

This repo is distributed under the MIT License.
