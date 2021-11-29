## DWMBLOCKS BASED ON LUKESMITH'S BUILD

# dwmblocks

Modular status bar for dwm written in c.


# Muelthebest's build

I have dwmblocks read my preexisting scripts
[here in my dotfiles repo](https://github.com/muelthebest/dotfiles/tree/main/.local/bin/statusbar).
So if you want my build out of the box, download those and put them in your
`$PATH`.

# Signaling changes

Most statusbars constantly rerun every script every several seconds to update.
This is an option here, but a superior choice is giving your module a signal
that you can signal to it to update on a relevant event, rather than having it
rerun idly.

For example, the audio module has the update signal 10 by default.  Thus,
running `pkill -RTMIN+10 dwmblocks` will update it.

You can also run `kill -44 $(pidof dwmblocks)` which will have the same effect,
but is faster.  Just add 34 to your typical signal number.

My volume module *never* updates on its own, instead I have this command run
along side my volume shortcuts in dwm to only update it when relevant.

Note that all modules must have different signal numbers.

# Clickable modules

Like i3blocks, this build allows you to build in additional actions into your
scripts in response to click events.  See the above linked scripts for examples
of this using the `$BLOCK_BUTTON` variable.
