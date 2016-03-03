# cuTORCS
Modified TORCS code for COHRINT lab
## Descriptions of Project

## Requirements

## Installation

NOTE: sudo

FOR LINUX:

Make sure you have the following:

1. OpenGL. Open up terminal and enter 'glxinfo | grep direct'. The result should be: 'direct rendering: Yes'
2. The following libraries: build-essential libxmu-dev libxmu6 libxi-dev libxine-dev libalut-dev freeglut3 freeglut3-dev cmake libogg-dev libvorbis-dev libxxf86dga-dev libxxf86vm-dev libxrender-dev libxrandr-dev zlib1g-dev libpng12-dev

PLIB:

Download link - http://plib.sourceforge.net/download.html

1. Unzip the file and cd into it from the terminal
2. Input the following './configure CFLAGS="-O2 -m64 -fPIC" CPPFLAGS="-O2 -fPIC" CXXFLAGS="-O2 -fPIC" LDFLAGS="-L/usr/lib64"'
3. 'make install'

OpenAL:

Download link - https://www.openal.org/downloads/

1. Input 'cd cmake'
2. 'cmake ..'
3. 'make'
4. 'make install'

Freealut:

Download link - https://github.com/vancegroup/freealut

1. Unzip the file and cd into it from the terminal
2. Create a directory and call it 'build'
3. Input 'cmake .. -DCMAKE_INSTALL_PREFIX:STRING="/usr" -DCMAKE_C_FLAGS:STRING="-march=athlon-xp -O2"'
4. 'make'
5. 'make install'

TORCS:

1. Download the latest version of TORCS from here - https://sourceforge.net/projects/torcs/files/
2. Unzip the file
3. Export the following using terminal:
    export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
    export TORCS_BASE=/usr/src/torcs/torcs-1.3.6
    export MAKE_DEFAULT=$TORCS_BASE/Make-default.mk
3. Input 'cd $TORCS_BASE'
4. './configure'
5. 'make install'

Finally, enter 'torcs' into the terminal to run the program. Profit.
