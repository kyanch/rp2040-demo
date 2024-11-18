# RP2040 demo

> [official example](https://github.com/raspberrypi/pico-examples)

> [Getting started with Raspberry Pi Pico](https://datasheets.raspberrypi.com/pico/getting-started-with-pico.pdf)

> [RPI Pico C/C++ SDK book](https://datasheets.raspberrypi.com/pico/raspberry-pi-pico-c-sdk.pdf)

## Setup your compiler toolchain

For Arch:

```bash
$ sudo pacman -S arm-none-eabi-gcc base-devel cmake --needed
$ sudo pacman -S arm-none-eabi-newlib --asdeps --needed
```

For Ubuntu:

```bash
$ sudo apt update
$ sudo apt install cmake gcc-arm-none-eabi libnewlib-arm-none-eabi build-essential
# Optional
$ apt install g++ libstdc++-arm-none-eabi-newlib
```

## Pull this repo and all submodules

拉取仓库及所有依赖项(主要是pico-sdk)

```bash
git clone https://github.com/kyanch/rp2040-demo.git --depth=1 --recurse-submodules
```

## Build as a normal cmake project

```bash
cd <repo>
mkdir build
cd build
make -j4
```

Or you want use Ninja:

```bash
cmake -B build -G Ninja
cmake --build build
```

## Flash your pico2

Press the button on your pico2 and connect the cable.

find `*.uf2` file in `build` folder, and drag it into the folder created by pico2.

That is it.
