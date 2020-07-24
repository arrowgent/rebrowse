# rebrowse
based on LinuxMint (ubuntu) MATE

**modify "default browser" to use various system tools to open applications**

originally designed for Discord in a Firejail
can also be used in Chatty

you will need to create this as the "Default Browser" system wide to a take effect
some options to do this:

> overrides:

* ~~#gvfs-mime --set x-scheme-handler/http rebrowse.desktop~~
* ~~#gvfs-mime --set x-scheme-handler/https rebrowse.desktop~~

* #xdg-mime default rebrowse.desktop x-scheme-handler/http
* #xdg-mime default rebrowse.desktop x-scheme-handler/https

* #gio mime x-scheme-handler/http rebrowse.desktop
* #gio mime x-scheme-handler/https rebrowse.desktop

* #xdg-settings set default-web-browser rebrowse.desktop

* #gconftool-2 -g /desktop/gnome/url-handlers/http/command
* #gconftool-2 --type string -s /desktop/gnome/url-handlers/http/command "rebrowse %U"
* #gconftool-2 --type string -s /desktop/gnome/url-handlers/https/command "rebrowse %U"

* #update-desktop-database ~/.local/share/applications
* #sudo update-mime-database /usr/share/mime

* __#sudo update-alternatives --install <link> <name> <path> <priority>__
* __#sudo update-alternatives --config x-www-browser__
* __#sudo update-alternatives --config gnome-www-browser__

> file locations to check
* #~/.local/share/applications
* #/usr/share/applications
* #~/.config/mimetypes.list