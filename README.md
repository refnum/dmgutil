dmgutil
=======
dmgutil is a command line tool for creating, configuring, and
compressing macOS disk images for distribution.

It allows you to automate your build process, preparing a release
without pre-existing templates or user interaction.

dmgutil can adjust the size, position, and appearance of Finder
windows. It can also apply custom icons to volumes, folders, or files
and assign a license agreement.



Usage
-----
To create a new disk image for your "MyApp 1.0" release, invoke dmgutil as:

```
    $ dmgutil.pl --open --volume="MyApp 1.0" myapp_1.0.dmg
```

Once the disk image has been populated with files, invoke dmgutil to configure it:

```
    $ dmgutil.pl --set --iconsize=128 --background=flowers.jpg "/Volumes/MyApp 1.0"
    $ dmgutil.pl --set --x=20 --y=60 --width=300 --height=200  "/Volumes/MyApp 1.0"
```

You can also use dmgutil to set the position of file or folder icons within the window:

```
    $ dmgutil.pl --set --x=100 --y=100 "/Volumes/MyApp 1.0/Read Me.rtf"
    $ dmgutil.pl --set --x=200 --y=100 "/Volumes/MyApp 1.0/MyApp.app"
```

dmgutil can also adjust the background color or toolbar visibility of
the window, and apply custom icons to the volume or its contents.

Once the volume has been prepared, compress the disk image with:

```
    $ dmgutil.pl --close --volume="MyApp 1.0" myapp_1.0.dmg
```

By invoking dmgutil from a post-build shell script, builds can be
automatically converted into a user-friendly disk image for
distribution.



Version History
---------------
* dmgutil 1.3
  * Released 2008/05/01
  * Added workaround for Finder bug when setting background image on 10.5
  * Added workaround for hdiutil bug when closing disk image on 10.5

* dmgutil 1.2
  * Released 2007/03/07
  * Fixed typo in zlib-level flag, was defaulting to 1 not 9

* dmgutil 1.1
  * Released 2006/07/31
  * Added --icon parameter to set custom icons
  * Added --bgcol parameter to set background color
  * Added --toolbar flag to control toolbar visibility

* dmgutil 1.0
  * Released 2006/07/22
  * Initial release
  
  