# V2X Application Spoofing Platform (VASP) 🦟

>   *   Omnet++工作目录
>   *   sumo1.8+Omnetpp5.6+veins5.2

​	This repository provides a framework to simulate attacks on V2X networks. It uses the VEINS simulation framework as a dependency.

## Install

### Git Clone Repository

```
mkdir vasp_omnet
cd vasp_omnet

git submodule add -b veins-5.2-vasp git@github.com:jeremyHua1931/veins.git

cd veins

git submodule update --init

```

### Dependencies

Operating System: Ubuntu/Debian/macOS

* [CSVWriter.h](https://github.com/al-eax/CSVWriter/blob/cee5f9d0ec72120404c1510708ba818307a6ab80/include/CSVWriter.h)
  Please put this file in your system's (or user's) default include directory. E.g., /usr/include
* [json.hpp](https://github.com/nlohmann/json/releases/download/v3.10.5/json.hpp)
  Rename this file to json.h and
  Put it in your system's (or user's) default include directory. E.g., /usr/include
  `sudo chmod 777 json.h`

## Build

* Change directory to <path/to/veins>
* Configure and build
  `./configure && make [-j6]`

## Running simulations

* Change directory to <path/to/veins>
* Start sumo server: bin/veins_launchd -vv
* Change directory to <path/to/veins>/src/vasp/scenario/
* Run simulation: `./run [-u Cmdenv]`