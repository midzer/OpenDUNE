# Emscripten

## Build

```
emconfigure ./configure --with-sdl2 --without-pulse --without-alsa --without-munt --with-fluid
emmake make
```

## Link

```
emcc -flto -O3 -fno-rtti -fno-exceptions *.o */*.o libfluidsynth.a -o index.html -sUSE_SDL=2 -sUSE_SDL_MIXER=2 --preload-file data/ --preload-file opendune.ini -sASYNCIFY -sASYNCIFY_IGNORE_INDIRECT -sASYNCIFY_ONLY=@../../funcs.txt -sENVIRONMENT=web -sINITIAL_MEMORY=128mb -sASYNCIFY_STACK_SIZE=81920 -Wl,-u,ntohs --closure 1 -sEXPORTED_RUNTIME_METHODS=['allocate']
```
