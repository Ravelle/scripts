# My Scripts
Scripts that aid in the operation of my system!<br />
The scripts caintained here are likely to be heavily related to one of two things:<br />
Software Development<br />
Customizing *NIX systems (see https://www.reddit.com/r/unixporn/)<br />
And even when the latter is in mind, it is likely that those customizations will be
in the spirit of making the system "better" for software development.

## Disclaimer

These scripts will be initially authoured and intended
for use on modern linux machines with access to an abundence of dependencies which
you may not wish to install - so if you find a simpler or more general solution
I wouldn't be surprised! (Do feel free to hit me up with a PR if that happens)

If you find a way in which one of these scripts is entirely redundant (usually I
write such things after not finding a good result on google) please DM me on twitter @max_ravelle

## on-change-to
TLDR: it's a function which takes two arguments: `on-change-to <path-to-file> <thing-to-execute>` <br />
`<path-to-file>` can be relative (`./file-in-this-dir`) <br />
`<thing-to-execute>` will be executed every time `file` is saved. <br />

`on-change-to` is intended to be a sort of hot-reload for when you're editing config files, usually when I'm messing with something like `i3` or `dunst` I will make small incrementental changes and want to see the effects immediately (mostly because I'm too lazy to read manuals so I just hack around and see what works), to do this with i3's config and save the 3ms it would take to hit the normal restart bind, do:<br />
`on-change-to ~/.config/i3/config "i3-msg restart"`<br />
to use this with `dunst-test`: <br />
`on-change-to ~/.config/dunst/dunstrc dunst-test`
if your editor has a really weird way of saving files you may need to read the debug output and tweak the script accordingly.

## dunst-test
Handy little script for testing dunst with, was designed specifically for use with `on-change-to`<br />
running `dunst-test` will start/restart dunst and give you one each of: low, normal, and critical notifications.
