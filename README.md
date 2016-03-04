# cuTORCS
Modified TORCS code for COHRINT lab
## Description of Project
This project is meant to create a realistic simulation environment that can be used for the [COHRINT](http://www.cohrint.info/) lab to use in research.

## Dependencies
Make sure you have the following:

### OpenGL
1. Open up terminal and enter glxinfo | grep direct. The result should be: direct rendering: Yes
2. If not install freeglut3, which has opengl as a dependency (so it will be automatically installed) `sudo apt-get install freeglut3-dev`

### The following libraries
```
build-essential libxmu-dev libxmu6 libxi-dev libxine-dev libalut-dev freeglut3 freeglut3-dev cmake libogg-dev libvorbis-dev libxxf86dga-dev libxxf86vm-dev libxrender-dev libxrandr-dev zlib1g-dev libpng12-dev
```

### PLIB 1.8.5:
Download link - http://plib.sourceforge.net/download.html
1. Unzip the file and cd into it from the terminal
2. Input the following
```
    ./configure CFLAGS="-O2 -m64 -fPIC" CPPFLAGS="-O2 -fPIC" CXXFLAGS="-O2 -fPIC" LDFLAGS="-L/usr/lib64"
```
3. `make install`

### OpenAL 1.1:
Download link - https://www.openal.org/downloads/
1. Input `cd cmake`
2. `cmake ..``
3. `make`
4. `make install`

### Freealut:
Download link - https://github.com/vancegroup/freealut
1. Unzip the file and cd into it from the terminal
2. Create a directory and call it 'build': `mkdir build`

3. ***I don't this this worked for me, I think I just ran*** `cmake` -- Input `cmake .. -DCMAKE_INSTALL_PREFIX:STRING="/usr" -DCMAKE_C_FLAGS:STRING="-march=athlon-xp -O2"`
4. `make`
5. `make install`

## Compiling TORCS and Installing
1. Download TORCS 1.3.6 from (you could also clone this repo, but it has our changes baked it as well) [here](https://sourceforge.net/projects/torcs/files/)
2. Unzip the file
3. Export the following using terminal:
```
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
export TORCS_BASE=/usr/src/torcs/torcs-1.3.6
export MAKE_DEFAULT=$TORCS_BASE/Make-default.mk
```
3. Input `cd $TORCS_BASE`
4. `sudo ./configure`
5. `make install`
6. `make datainstall`

Finally, enter 'torcs' into the terminal to run the program. Profit.

## For those participating in the project
We want to store keep these origianl files in the repo:
```
/src/doc/torcsdoc.conf
config.h
Make-config
```
But, they should be modified when making on your computer. In order to ignore these files that are already in the repo use the following commands. This will allow the file to be in the repository in its origianl form but to be changed on your local computer.
```
git update-index --assume-unchanged */Make-config
git update-index --assume-unchanged */config.h
git update-index --assume-unchanged */src/doc/torcsdoc.conf
```
