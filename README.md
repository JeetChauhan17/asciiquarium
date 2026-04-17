                              Asciiquarium v1.1
                    by Kirk Baucom <kbaucom@schizoid.com>
                          http://www.robobunny.com

Asciiquarium is an aquarium/sea animation in ASCII art.

Installation
------------

Asciiquarium is a single perl script, so all you have to do is make sure
it's executable and put it somewhere convenient, like /usr/local/bin or
/usr/local/games.

  Ubuntu
  ------

  Out-of-the-box ubuntu doesn't satisfy the Requirements below, so
  here's how to get them:
  1) Get perl's curses package which is available from apt:
       sudo apt-get install libcurses-perl
  2) Run
       cpan
     at the shell.  Agree to the defaults for everything.
     To leave cpan, type 
       quit
  3) Type
    sudo cpan Term::Animation

Requirements
------------

You must have the Term::Animation module, which you can get from
http://www.cpan.org. The Term::Animation module also requires the Curses
module, which you can also get from CPAN. This program will only run on
platforms that have a Curses library (so it won't work on Windows, but
you might get it to run under cygwin).

Usage
-----

Command line arguments:
	-c	"classic" mode, only show species from Asciiquarium 1.0

While running:
	q	quit
	r	redraw (will recreate all entities)
	p	toggle pause

TODO-in-fish integration
------------------------

Asciiquarium can now render TODO text directly inside some fish bodies.
It is designed to work without extra setup with common terminal todo tools
and file formats.

At startup, Asciiquarium scans common task locations and formats, including:

- `~/.local/share/meowdo/todos.txt` (Meowdo format)
- `MDT_DIR` / `MDT_INBOX` markdown files (mdt)
- `TODO.md`, `todo.txt`, `tasks.md`, and similar files in the current
  directory and home directory
- JSON task files (`tasks.json`, `todo.json`, `todos.json`) in common app
  directories such as `~/.config/dooit`, `~/.local/share/dooit`,
  and `~/.local/share/meowdo`
- YAML task files (`todo.yaml`, `todo.yml`) in common dooit-style paths

Supported task patterns:

- Markdown checkboxes: `- [ ] task`
- todo.txt entries (completed lines prefixed with `x YYYY-MM-DD` are ignored)
- Meowdo pipe-delimited rows (`priority|done|tag|description|...`)
- Generic JSON task objects (uses fields like `task`, `title`, `text`,
  `description`, with `done/completed` filtering when present)
- Basic YAML task objects (e.g., `- description: ...` with
  `done/completed: false`)

Contributors
------------

New fish species backported from the Android live wallpaper and
other minor improvements by Claudio Matsuoka.

Pretty much all of the ASCII art was done by Joan Stark:
http://www.geocities.com/SoHo/7373/

Anything that she didn't do, I don't have a source for.
