# morc_menu
Categorized desktop application menu
* independent of any window manager
* highly and easily customizable

morc_menu is a bash script that simulates the functionality of an [Openbox](https://en.wikipedia.org/wiki/Openbox)
/ [Fluxbox](https://en.wikipedia.org/wiki/Fluxbox) style menu without requiring those window
managers or associated dependencies. It was originally
written for the [i3 window manager](https://en.wikipedia.org/wiki/I3_%28window_manager%29), and using '[dmenu-manjaro](https://github.com/manjaro/packages-community/tree/master/dmenu-manjaro)' (wikipedia: [dmenu](https://en.wikipedia.org/wiki/Dwm#dmenu) )
as its front-end, but it should also work in pretty much
any X11 environment, and has been tested with
alternative front-ends such as the [normal/vanilla/real version of 'dmenu](http://tools.suckless.org/dmenu/)', as well as  '[rofi](https://davedavenport.github.io/rofi/)', '[zenity](https://en.wikipedia.org/wiki/Zenity)' and
'yada'.

morc_menu generates menus based upon the presence of
.desktop files in the system-wide definition folder
/usr/share/applications and the user-local definition
folder ${HOME}/.local/share/applications, per the
xfreedesktop and linux LSB standards.

A readable version of the script's [man page](https://github.com/Boruch-Baum/morc_menu/wiki/man-page) is available on this repository's [wiki](https://github.com/Boruch-Baum/morc_menu/wiki).

## Screenshots

Let's start with a menu customized to be 'skinned' consistently with Manjaro i3, and using all the dmenu features. It spawns the menu at the mouse position, calculates the menu geometry based upon the menu content, has mouse support, and has prefix and suffix labels to distinguish sub-menus from executables. All of this is easily changeable in the user or system config file.<br/>
![Main menu](https://github.com/Boruch-Baum/morc_menu/blob/screenshots/morc_menu_01_main_menu.png)

One way to navigate the menu is by using your arrow keys, or the mouse:<br/>
![Main menu navigation](https://github.com/Boruch-Baum/morc_menu/blob/screenshots/morc_menu_02_%28arrow_nav_to_system%29.png)

But why bother using the mouse when you can use the keyboard? (Don't answer that) As you type your selection, dmenu dynamically updates its presentation to the matching subset of menu entries. In the following screenshot, the user has typed 's' from the main menu and now has presented only those menu items with that letter.<br/>
![Main menu keyboard entry 's'](https://github.com/Boruch-Baum/morc_menu/blob/screenshots/morc_menu_11_main_menu_%28typing_s%29.png)

With a second keystroke, 'y', the user has reduced the menu to one item, and can press return to select that item.<br/>
![Main menu keyboard entry 'sy'](https://github.com/Boruch-Baum/morc_menu/blob/screenshots/morc_menu_12_main_menu_%28typing_sy%29.png)

After three keystrokes, 'sy\<enter\>', the user has navigated to the 'System' category sub-menu. The user could have saved a keystroke by typing just 'y\<enter\>' since that character was unique to the 'System' line among all displayed menu entries. <br/>
![System menu](https://github.com/Boruch-Baum/morc_menu/blob/screenshots/morc_menu_13_system_menu.png)

Finally, here is what morc_menu looks like in its most simple, uncustomized form, using the most primitve version of dmenu. The menu appears at a fixed position along the entire width of the top of the screen.<br/>
![Main menu with most basic setup](https://github.com/Boruch-Baum/morc_menu/blob/screenshots/morc_menu_21_main_menu_plain.png)

## Requirements

For the presentation front-end:
* dmenu, or
* rofi, or
* zenity, or
* yada, or
* something else.

If you use dmenu, the plain unpatched version will work, but using a version that includes the developers' add-on patches will offer more customization options and more attractive defaults. See the configuration file and man page for details. An example of a patched version is the package 'dmenu-manjaro', used in [Manjaro's i3 edition](https://manjaro.github.io/Manjaro-i3-15.12-released/)


Optionally, for aligning / positioning the menu at the current mouse pointer:
* [xdotool](http://www.semicomplete.com/projects/xdotool), from package xdotool;
* lsw and wattr, both from package [wmutils](https://github.com/wmutils/core)

## Setup

  If your distribution has a packaged version of this
  script, it is advisable to install that package and
  to follow any supplemental instructions of the
  packager.

  Otherwise, if you wish to install morc_menu for system-wide use, available to all users: Download the package zip file; Unzip it,; cd into the created folder morc_menu-master, and; Run 'sudo make install'. How then to create system-wide keybindings for morc_menu and how to propagate them is a matter too system-specific and too dependent on your use-case for this readme to fully address.  An example keybinding for use with the i3 window manager would be to modify the /etc/skel/.i3/config file and ${HOME}/.i3/config files to include a statement in the form: `bindsym $mod+z exec morc_menu`


  For personal use, without installing system-wide, and without requiring administrator privileges, manually install the script  by performing the following: download the package zip file; unzip it; copy the script file 'morc_menu' to a convenient location, for
  example, somewhere on your `${PATH}`; Make it executable by running 'chmod +x /path/to/file'; Optionally, copy
  the script's associated config file to `${HOME}/.config/morc_menu`; Optionally, copy the script's associated man page to somewhere your system will recognize (run command 'manpath', and if you can not place it in any of those places, run 'man manpath'
  to see how to set $MANPATH), and; Create a keybinding for the script. An example keybinding for use with the
  i3 window manager would be to modify your `${HOME}/.i3/config file` to include a statement in the
  form:
````
     bindsym $mod+z
             exec "${HOME}/path/to/morc_menu"
````
## Customization
  This script offers many ways to customize the menu's
  content and 'look' ('skin'). Refer to the script's
  [man page](https://github.com/Boruch-Baum/morc_menu/wiki/man-page) and [configuration file](https://raw.githubusercontent.com/Boruch-Baum/morc_menu/master/morc_menu_v1.conf) for details.

## Copyright and License

 ©2016, Boruch Baum <boruch_baum AT gmx DOT com>

 This program is free software; you can redistribute it
 and/or modify it under the terms of the GNU General
 Public License aspublished by the Free Software
 Foundation; either version 3 of the License, or (at your
 option) any later version.

 This program is distributed in the hope that it will be
 useful, but WITHOUT ANY WARRANTY; without even the
 implied warranty of MERCHANTABILITY or FITNESS FOR A
 PARTICULAR PURPOSE. See the GNU General Public License
 for more details.
