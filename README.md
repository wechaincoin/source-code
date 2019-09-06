This is the reference code for [wechaincoin](http://www.wechaincoin.info/) cryptocurrency.

* Official homepage: [wechaincoin](http://www.wechaincoin.info/)
* Official repository: [wechaincoin GitHub](https://github.com/wechaincoin)
* Official Announcement thread: [wechaincoin BitcoinTalk](https://bitcointalk.org/index.php?topic=4643409.0)
* Official Discord: [wechaincoin Discord](http://discord.gg/AbT3vEg)
* Official Telegram: [wechaincoin Telegram BR](http://t.me/wechaincoin)
* Official Block explorer: [wechaincoin Block explorer](http://explorer.wechaincoin.info/)


## _wechaincoin_ Cryptocurrency

wechaincoin [WXTC] is an ASIC resistant CryptoNightLite V1 algorithm based cryptocurrency.

- __Name__: WeChain Coin
- __Ticket__: WXTC
- __Mining Protocol__: Proof of Word (POW)
- __PoW Hashing Algorithm__: CryptoNight-Lite V1 (ASIC Resistant)
- __Max Supply__: 150,000,000,000
- __GPU/CPU Mining__: 100,000,000,000
- __Pre-Mining__: 50,000,000,000:
- __Share Capital__: 30,000,000,000
- __Reserved for Social Projects__: 15,000,000,000
- __Giveaways__: 5,000,000,000
- __Minimun transaction fee__: 0.01 WXTC
- __Reward per Block__: 23,803.253 WXTC and going down
- __Block Time__: 120 seconds
- __Difficulty adjustment__: Every Block

## How to compile

### Compile on Linux Ubuntu 16

**1. Install dependencies**

- Update

```
sudo apt-get update
```

- Install dependencies

```
sudo apt-get install -y build-essential python-dev gcc g++ git cmake librocksdb-dev libboost-all-dev
```

- Optional: create folder _wechaincoin_

If you want to have all files related to __wechaincoin__  in one folder, run the following code:

```
mkdir wechaincoin
```

You can create the folder anywhere you like, we will assume it to be `/home/USER/wechaincoin` for this tutorial, where `USER` is your username.

- Enter the folder:

```
cd wechaincoin
```

**2. Clone source code from GitHub**

```
git clone https://github.com/wechaincoin/source-code.git
```

**3. Give the correct permission**

- navigate to:

```
cd source-code/external/rocksdb/build_tools
```

- Make the following files executable:

```
chmod +x build_detect_platform
chmod +x version.sh
```

**4. Build executables**

- Navigate back to root folder

```
cd /home/USER/wechaincoin/source-code
```

- prepare the build

```
mkdir build && cd $_
```

```
cmake ..
```

- Export flags

```
export CXXFLAGS="-std=gnu++11"
```

- Make/Build

```
make
```

_Your executables will be located in `build/src` folder._


### Compile on Manjaro (Arch) Linux

**1. Install dependencies**

- Install dependencies

```
sudo pacman -S base-devel python gcc git cmake gflags boost snappy lz4 zlib bzip2 zstd
```

- Install RockSDB from source

```
git clone https://github.com/facebook/rocksdb.git
cd rocksdb
USE_SSE=1 make static_lib
```


- Optional: create folder _wechaincoin_

If you want to have all files related to __wechaincoin__  in one folder, run the following code:

```
mkdir wechaincoin
```

You can create the folder anywhere you like, we will assume it to be `/home/USER/wechaincoin` for this tutorial, where `USER` is your username.

- Enter the folder:

```
cd wechaincoin
```

**2. Clone source code from GitHub**

```
git clone https://github.com/wechaincoin/source-code.git
```

**3. Give the correct permission**

- navigate to:

```
cd source-code/external/rocksdb/build_tools
```

- Make the following files executable:

```
chmod +x build_detect_platform
chmod +x version.sh
```

**4. Build executables**

- Navigate back to root folder

```
cd /home/USER/wechaincoin/source-code
```

- prepare the build

```
mkdir build
cd build
```

```
cmake ..
```

- Export flags

```
export CXXFLAGS="-std=gnu++11"
```

- Make/Build

```
make
```

_Your executables will be located in `build/src` folder._


### Compile on Windows 7/8/10

**1. Environment**

- Visual Studio 2017 Community Edition with desktop development with C++ and the VC++ v140 toolchain features selected
- Boost 1.59.0, with the installer for MSVC 14

**2. Build**

- From the start menu, open 'x64 Native Tools Command Prompt for vs2017'


``
cd <wechaincoin/source-code>
``

``
mkdir build
``

``
cd build
``


-  Set the PATH for Cmake:

```
set PATH="C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin";%PATH%
```

- Run Cmake:

```
cmake -G "Visual Studio 14 Win64" .. -DBOOST_ROOT=C:/local/boost_1_59_0
```

- Build:

```
MSBuild wechaincoin.sln /p:Configuration=Release /m
```

_Your binaries  will be located in `..\build\src\Release` folder._


### Compile on macOS High Sierra

**1. Dependencies**

- Download and install Xcode from App Store
- Open Xcode and download additional contents
- Download CMAKE for OSX: https://cmake.info/files/v3.10/cmake-3.10.3-Darwin-x86_64.dmg
- Copy the CMAKE app to Application folder
- Open CMAKE GUI first time, and close it afterwards
- Run this command in terminal for CMD tools:

- on newer devices

```
sudo "/Applications/CMake.app/Contents/bin/cmake-gui" --install
```

- older than 4 years

```
sudo "/Applications/CMake.app/Contents/bin/cmake-gui" --install=/path/to/bin
```

- install Homebrew if you haven’t already

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

- install xCode CMD tools and install Xcode from app store:

```
xcode-select --install
```

- accept Xcode license

```
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
```

```
sudo xcodebuild -license accept
```

- install rocksdb

```
brew install rocksdb
```

- install boost

```
brew install boost
```

**2. Build**

```
cd wechaincoin
```

- get the source code

```
git clone https://github.com/wechaincoin/source-code.git
```

- CHMOD

```
cd source-code/external/rocksdb/build_tools
```

```
sudo chmod +x build_detectplatform
sudo chmod +x version.sh
```

- navigate back to source folder and run

```
mkdir build && cd $
```

```
sudo cmake -DBOOST_ROOT=/usr/local/include/boost ..
```

```
sudo make
```

_Your binaries  will be located in `..\build\src\Release` folder._

### Credits
Cryptonote Developers, Bytecoin Developers, Monero Developers, Forknote Project, TurtleCoin Developers
