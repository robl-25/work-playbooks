# Firefox

Install Firefox developer edition if necessary. Also remove all other firefox's
installed such as firefox-esr.

## Error
If during the installation you receive this error:
```bash
/usr/bin/xdg-mime: <LINE>: local: <FILENAME>: bad variable name
```
It refers to a file (FILENAME) that has space in the name. To fix you can:
- run `cd ~/.local/share/applications`
- find the file that has spaces in the name (look for the name in the error (FILENAME))
- change the file name removing the space (you can add `_` instead of space)
- change all references to that file in `~/.local/share/applications/mimeapps.list`

[reference](https://forums.linuxmint.com/viewtopic.php?t=280798)
