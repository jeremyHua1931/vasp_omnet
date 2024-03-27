# V2X Application Spoofing Platform (VASP) 🦟

>   *   Omnet++工作目录
>   *   ubuntu18/20:sumo1.8.0+Omnetpp5.6.2+veins5.2(Test_OK)
>   *   Official Repository： https://github.com/quic/vasp

​	This repository provides a framework to simulate attacks on V2X networks. It uses the VEINS simulation framework as a dependency.

## Install

### Dependencies

Operating System: Ubuntu/Debian/macOS

* [CSVWriter.h](https://github.com/al-eax/CSVWriter/blob/cee5f9d0ec72120404c1510708ba818307a6ab80/include/CSVWriter.h)
  Please put this file in your system's (or user's) default include directory. E.g., /usr/include
* [json.hpp](https://github.com/nlohmann/json/releases/download/v3.10.5/json.hpp)
  Rename this file to json.h and
  Put it in your system's (or user's) default include directory. E.g., /usr/include
  `sudo chmod 777 json.h`
* Clone [VEINS](https://veins.car2x.org/) (version 5.2): `git clone --branch veins-5.2 https://github.com/sommer/veins.git`
* Add this repo as submodule under `<path/to/veins>/src/`: `cd veins && git submodule add https://github.com/quic/vasp src/vasp`

## Build

* Change directory to <path/to/veins>
* Configure and build
  `./configure && make [-j6]`
* std::make_unique报错(if exsit)
  * `driver/CarApp.cc`中`std::make_unique`全部换成`veins::make_unique`


## Running simulations

* Change directory to <path/to/veins>
* Start sumo server: bin/veins_launchd -vv
* Change directory to <path/to/veins>/src/vasp/scenario/
* Run simulation: `./run [-u Cmdenv]`

### Make Top Repository

```
mkdir vasp_omnet
cd vasp_omnet
git submodule add -b veins-5.2-vasp git@github.com:jeremyHua1931/veins.git
```

>   If there are installation issues with VASP, you can contact me via email[ jeremyhua@foxmail.com ] and the email subject is "[Github-vasp_omnet]-Installation issues with VASP".