# cuTORCS
Modified TORCS code for COHRINT lab
## Description of Project
This project is meant to create a realistic simulation environment that can be used for the [COHRINT](http://www.cohrint.info/) lab to use in research.

## Dependencies
Make sure you have the following in order. If any of the following fail, make sure to check the Libraries list below.

### The following libraries
```
build-essential libxmu-dev libxmu6 libxi-dev libxine-dev libalut-dev freeglut3 freeglut3-dev cmake libogg-dev libvorbis-dev libxxf86dga-dev libxxf86vm-dev libxrender-dev libxrandr-dev zlib1g-dev libpng12-dev
```
Note: `freeglut3` has OpenGL as a dependency, OpenGL is also a prerequisite for TORCS
### PLIB 1.8.5:
Download link - http://plib.sourceforge.net/download.html
* Unzip the file and cd into it from the terminal
* Input the following (for x64):
```
./configure CFLAGS="-O2 -m64 -fPIC" CPPFLAGS="-O2 -fPIC" CXXFLAGS="-O2 -fPIC" LDFLAGS="-L/usr/lib64"
make
sudo make install
```

### OpenAL-soft:
Clone from - https://github.com/kcat/openal-soft
* Input (note, `cmake ..` is `cmake[SPACE]..`)
```
cd cmake
cmake ..
make
sudo make install
```

### Freealut:
Clone from - https://github.com/vancegroup/freealut
* Unzip the file and cd into it from the terminal
* Create a directory and call it 'build': `mkdir build`

* Input (note, `cmake ..` is `cmake[SPACE]..`):
```
cd build
cmake ..
make
sudo make install
```

## Compiling TORCS and Installing
* Download TORCS 1.3.6 from (you could also clone this repo, but it has our changes baked it as well) [here](https://sourceforge.net/projects/torcs/files/)
* Export the following using terminal:
```
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
export TORCS_BASE=/usr/src/torcs/torcs-1.3.6
export MAKE_DEFAULT=$TORCS_BASE/Make-default.mk
```
* Input(for x64):
```
cd $TORCS_BASE
./configure CFLAGS="-O2 -m64 -fPIC" CPPFLAGS="-O2 -fPIC" CXXFLAGS="-O2 -fPIC" LDFLAGS="-L/usr/lib64"
make
sudo make install
sudo make datainstall
```
* Finally, enter 'torcs' into the terminal to run the program. Profit.

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
