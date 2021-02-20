# How to start Smoking Gun map on Deamon Engine



### Setup Deamon engine :

You can follow the official doc of the engine [Here](https://github.com/DaemonEngine/Daemon), and after go to `Launch SG map` bellow.
#### Dependencies
Linux (Ubtuntu/Debian) :<br/>

```shell
 $ sudo apt update
 $ sudo apt install cmake git libgmp-dev nettle-dev libcurl-dev libsdl2-2.0-0 libsdl2-gfx-1.0-0 libsdl2-image-2.0-0 libsdl2-mixer-2.0-0 libsdl2-net-2.0-0 libsdl2-ttf-2.0-0 libglew-dev libpng-dev libjpeg-dev libwebp-dev libfreetype-dev libopenal-dev libalut-dev libogg-dev libvorbis-dev libtheora-dev libopus-dev libopusfil lib64z1-dev libgeoip-dev lib64ncurses-dev
 ```


Or here you have the list of all the dependencies : <br/>
 `zlib`, `libgmp`, `libnettle`, `libcurl`, `SDL2`, `GLEW`, `libpng`, `libjpeg ≥ 8`, `libwebp ≥ 0.2.0`, `Freetype`, `OpenAL`, `libogg`, `libvorbis`, `libtheora`, `libopus`, `libopusfile`, `ncurses`, `libGeoIP`

#### Download instructions

```shell
git clone --recurse-submodules https://github.com/DaemonEngine/Daemon.git
```
If you have already cloned:
```
cd Daemon/
git submodule update --init --recursive
```

#### Build Instructions

Instead of -j4 you can use -jN where N is your number of CPU cores to distribute compilation on them. Linux systems usually provide an handy nproc tool that tells the number of CPU core so you can just do -j$(nproc) to use all available cores.

Enter the directory before anything else:

```
cmake -H. -Bbuild
cmake --build build -- -j4
```


### Launch SG map :
Extract the pkg/ directory from there: <br/>
https://dl.unvanquished.net/release/unvanquished_0.51.2.zip<br/>
```
./daemon -pakpath path/to/pkg 
```

Then in game console (shift+escape or the key on the left of 1) type this:
```
/set g_neverEnd 1
/devmap dm-name_of_the_SG_map
```
