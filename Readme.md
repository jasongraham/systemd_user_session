# Systemd User Session Units #

This repository contains systemd user session unit files.

Many are based on the excellent examples done by [KaiSforza][], who also does
much more with his.  See the link for a much more thorough explanation of what
to do.

## What to do ##

On Arch Linux, using the slim login manager, I did the following and it works.

For more useful instructions, see the link above or the [Arch Wiki][] article.

1. Install [user-session-units][] from the AUR.  We need this for our dbus
   socket.

2. Install (or link) this repository to the location `$HOME/.config/systemd`.

3. Edit (backup first) your `$HOME/.xinitrc` to include
   `/usr/lib/systemd/systemd --user` at the end.

4. Add `session    required    pam_systemd.so` to `/etc/pam.d/login` and
   `/etc/pam.d/system-auth`.

5. Enable the unit files you want handled by systemd through `systemctl --user
   enable whatever`.

6. Reboot and pray it works. If not, debugging is fun, right? What, where are
   you going?

[KaiSforza]:https://bitbucket.org/KaiSforza/systemd-user-units/src
[Arch Wiki]:https://wiki.archlinux.org/index.php/Systemd/User
[user-session-units]:https://github.com/sofar/user-session-units
