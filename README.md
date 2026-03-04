# About this fork of FreeSynd

![Screenshot](screenshot.png)

## Improvements

Make it playable with modern controls and high-resolution screens.

- Fullscreen by default, preserving aspect ratio as in the original DOS game.
- Configurable scaling. Go to where user.conf file is saved. For Windows its in C:\User\[account]\.freesynd and change the scale_factor number, 2 is better for 1080 monitors. 1 is same as default as its 1x. 3 and upwards are better for 4K monitors. Default is 0 which is calculated depending on resolution but I found graphics too small for 1080 screens.
- See more of the map in a zoomed out view, pixel-perfect integer scaled.
- Hold down CTRL or Mouse-wheel to pan the view using the mouse.
- Smooth panning with WASD keys instead of edge-panning.
- High framerate. If you have a 144 Hz monitor scrolling is 144 fps (for example).
- Faster menu transitions, without the loud sound from the original.
- Press key 1-4 to select agent. Double press key 1-4 to center on agent.

All credits to the original FreeSynd authors and Bullfrog.

## Developer notes

### Convert data files to lower case
rename.pl -f 'y/A-Z/a-z/' *

### CMake options om macOS
--preset "ninja-clang-arm64-release" -DCONAN_COMMAND=~/Library/Python/3.14/bin/conan

### CMake using Cmake-gui on Windows
- Point to source code folder
- Choose preset from dropdown
- Should then create a build folder for where it will put project files in (such as Visual Studio)
- Click Configure. Let it do its thing.
- Click Generate and now project files are in the build folder.
- Open project in (for eg:) Visual Studio and Build. exe will be in the (for eg:) build\ninja-msvc-x64-release\game\Release folder.
- Copy the exe into the game files folder. Make sure data, icon and relevant dlls are in the folder. They should be: libpng16.dll, libpng16d.dll, SDL2.dll, SDL2_image.dll, SDL2_mixer.dll, zlib.dll, zlibd.dll.
- Run the exe and game should start.

### Go directly to mission with cheats
./FreeSynd -m 8 -c "COOPER TEAM"
