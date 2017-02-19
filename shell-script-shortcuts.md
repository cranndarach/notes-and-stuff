# Setting up keyboard shortcuts to execute shell scripts

The most basic version of this is very simple, but I had to search around a bit
to figure out how to effectively set it up to print a status message.

## 1. The basic script

First write the script, with the conditional `echos` based on success/failure:

```sh
#!/bin/sh

(command-to-run && echo "Success message") || echo "Failure message"
```

Then make sure to make it executable: `chmod u+x filename.sh`

Note (mostly to self): I am trying to keep all scripts like this in `~/.scripts`

## 2. Set up the keyboard shortcut

In Preferences -> Keyboard -> Shortcuts (or just start typing 'shortcuts' into
the HUD), add a custom shortcut. 

For the command, make sure to tell it to run in a terminal (i.e., actually open
a terminal window). I'm using gnome-terminal because it is the default and rather
lightweight (no need to open terminix or anything).

```sh
gnome-terminal -e "/home/rachael/.scripts/my_script.sh"
```

Right now, this will open a terminal, but immediately exit when it is done. That's
not enough time to actually see the status message.

## 3. Holding the terminal open

In order to get the terminal to stay open, add a line to the original script that
starts an interactive shell session. You can pick whatever shell you want, but
if you are just doing it to be able to read the message, it doesn't make sense
to start up a shell with heavy config files. Just `sh` will be fine. So that leaves:

```sh
gnome-terminal -e "/home/rachael/.scripts/my_script.sh"

sh
```

Now, when you run it, it will print the success/failure message, and then display
a prompt (`$`). If you're satisfied, you can just hit Ctrl+D to exit. Or, if you want
to stick around for a bit, you can start up your preferred shell by calling it
(e.g., `$ zsh`).
