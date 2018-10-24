
https://www.mathewinkson.com/2013/03/force-rgb-mode-in-mac-os-x-to-fix-the-picture-quality-of-an-external-monitor#comment-15886

- Download the patch-edid.rb script from the forums thread above, or download Andrew Daugherity’s improved patch-edid.rb script from his github page. Put the script in your home directory.

-  Start by running the .rb script.

It only generates a couple of files in your user’s directory and does not require any special rights to read the current monitor / tv configuration. (TV must be connected).

- Boot to into the recovery system (Cmd+R during boot).

All your files are accessible here and you have write permissions to the “Overrides” folder. Your system disk is just not mounted to / but to /Volumes/ (e.g. “/Volumes/Macintosh HD/”)

- Open a terminal and copy the DisplayVendor-directory. Remember that every path is now prefixed by “/Volumes/Macintosh HD/”.

E.g. I had the Ruby script in a folder “EDID-Fix” on my desktop.
-bash-3.2# cp -r /Volumes/Macintosh\ HD/Users/Chao/DisplayVendorID-* /Volumes/Macintosh\ HD/System/Library/Displays/Contents/Resources/Overrides/

- Reboot to your system
