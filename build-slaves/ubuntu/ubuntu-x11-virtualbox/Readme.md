# VirtualBox - Ubuntu

Creates an image using our Ubuntu Java/Gradle/X11 image, setting up a VirtualBox and Packer.

Jenkins needs the ``xvnc`` plugin installed. You have to set the __minimum__ and __maximum__ display number to __1__. The command line is:

    x11vnc -forever -geometry 1200x800 -display :$DISPLAY_NUMBER -shared -nopw -noxfixes -noxdamage
