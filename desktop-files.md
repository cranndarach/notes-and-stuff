# Creating "start" menu entries (desktop files)

>Condensed version of [this page](https://developer.gnome.org/integration-guide/stable/desktop-files.html.en)

* The file should be placed in either `~/.local/share/applications` for
  your own use, or `/usr/share/applications` to be accessed by all users. I
  go with the former.
* Name the file `descriptive-program-name-without-spaces.desktop`
* Format:

```
[Desktop Entry]
Name=Program Name
Exec=/path/to/executable
Icon=/path/to/icon
Type=Application
Categories=Programming;Accessories;Office
```

    * It's case-sensitive, but the order does not matter beyond the first line (`[Desktop Entry]`)
    * The categories are your own preference / where you want to look for it.

* I find that it's not always there until I restart the computer, not sure why.
