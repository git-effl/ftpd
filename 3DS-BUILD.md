# HOW TO BUILD FOR 3DS
This command sequence will show you how to build FTPD as 3DSX.
```bash
git clone https://github.com/git-effl/ftpd.git
cd ftpd
mkdir build-3ds
cd build-3ds
cp -r romfs ../romfs
cmake .. -DCMAKE_TOOLCHAIN_FILE=${DEVKITPRO}/cmake/3DS.cmake
cmake --build .
```
"I also wanna build as CIA,but how?"
Simple,you use the 3DSX base and run this sequence of commands in your terminal:
```bash
bannertool makebanner -i ../meta/banner.png -a ../meta/audio.wav -o banner.bnr
makerom -f cia -o ftpd.cia -elf ftpd.elf -rsf ../meta/ftpd-cia.rsf -banner ../banner.bnr -icon ftpd.smdh -exefslogo
```
