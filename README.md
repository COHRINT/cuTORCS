# cuTORCS
Modified TORCS code for COHRINT lab
## Descriptions of Project

## Dependencies

## Installation

FOR LINUX:
<br />
Make sure you have the following:
<br />
1. OpenGL. Open up terminal and enter glxinfo | grep direct. The result should be: direct rendering: Yes
2. The following libraries: build-essential libxmu-dev libxmu6 libxi-dev libxine-dev libalut-dev freeglut3 freeglut3-dev cmake libogg-dev libvorbis-dev libxxf86dga-dev libxxf86vm-dev libxrender-dev libxrandr-dev zlib1g-dev libpng12-dev

PLIB 1.8.5: <br />
<br />
Download link - http://plib.sourceforge.net/download.html <br />

1. Unzip the file and cd into it from the terminal <br />
2. Input the following <br />
    ./configure CFLAGS="-O2 -m64 -fPIC" CPPFLAGS="-O2 -fPIC" CXXFLAGS="-O2 -fPIC" LDFLAGS="-L/usr/lib64"
3. make install <br />

OpenAL 1.1: <br />
<br />
Download link - https://www.openal.org/downloads/
<br />
1. Input cd cmake
2. cmake ..
3. make
4. make install
<br />
Freealut: <br />
<br />
Download link - https://github.com/vancegroup/freealut <br />
<br />
1. Unzip the file and cd into it from the terminal
2. Create a directory and call it 'build'
3. Input cmake .. -DCMAKE_INSTALL_PREFIX:STRING="/usr" -DCMAKE_C_FLAGS:STRING="-march=athlon-xp -O2"
4. make
5. make install
<br />
TORCS: <br />
<br />
1. Download the latest version of TORCS from here - https://sourceforge.net/projects/torcs/files/
2. Unzip the file
3. Export the following using terminal: <br />
    export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib <br />
    export TORCS_BASE=/usr/src/torcs/torcs-1.3.6 <br />
    export MAKE_DEFAULT=$TORCS_BASE/Make-default.mk <br />
3. Input cd $TORCS_BASE
4. sudo ./configure
5. make install
6. make datainstall
<br />
Finally, enter 'torcs' into the terminal to run the program. Profit. <br />
