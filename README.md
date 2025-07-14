# bip39scan v 3.2 (Milk Sad) - For sale ~~$500~~ $250
Vulnerable generator libbitcoin explorer v3.2<br>
To purchase, write to telegram ```@phrutis``` or buy from a bot in a group [t.me/cuda8](https://t.me/cuda8)<br>
The program is sold with the source code (cmake VS2022) + ready-made programs (multigpu) for win, lin, hiveos, Ubuntu 20.04 (22.04)<br>
**There are 2 previous versions in folder BONUS for free [bip39scan v1](https://github.com/phrutis/bip39scan) + [bip39scan v2](https://github.com/phrutis/bip39scan2) + (with sources)**

More about the vulnerability Milk Sad:<br>
RU https://habr.com/ru/articles/771980/<br>
EN https://milksad.info<br>
EN https://milksad.info/disclosure.html#codename-milk-sad<br>
 
bip39scan v3 generates all possible mnemonics across the entire 32-bit<br>
Not everyone knows about this vulnerability. Some sites and applications still use this vulnerable library.<br>
Therefore, the chance to find a fresh coin is very high. Update your address databases.<br>
The main advantage of bip39scan v3 is its high speed!

### The program's operating principle:<br>
When first launched, the program checks all 4294967296 phrases in vulnerable 32 bits of entropy.<br>
At a speed of 550k phrases per second - this is only 2 hours of brute force.<br>
All these phrases have been checked many times, and are unlikely to have a positive balance.<br> 
Perhaps with a fresh address base there is a chance to find a fresh coin.<br> 
There is also a chance to find by a non-standard patch or a rare coin, token.<br>
After that, the program again goes through 32 bits of entropy but with greater depth, as if the entropy was generated a second time.<br>
Then, the third, fourth ... the program searches indefinitely.<br>
No one has used this method! There are finds with a positive balance for it.

[**View finds with positive balance**](https://github.com/phrutis/bip39scan3/blob/main/Founds.md)<br>

[**Download all empty finds CSV FOUNDS.txt (137к phrases)**](https://github.com/phrutis/bip39scan2/releases/download/3.2/FOUNDS.txt)<br>

**Important! There is no continuation of the search.**<br> 
If you stop brute force, start the program from the beginning, it will start searching all over again.<br> 
You will find what you found before until you reach the place where you stopped.

Unix timestamp range (from January 1, 1970, to January 19, 2038).<br>
date/time: 1970-01-01 00:00:00 for first timestamp. If chosen english ETH addresses pach ```m/44'/60'/0'/0/0-9```<br>
it will generate "milk sad ..." mnemonic<br>

<img width="977" height="511" alt="Image" src="https://github.com/user-attachments/assets/e787df51-071c-4fb7-bf7f-69299d045abc" />

Only CUDA cards support GTX, RTX, CMP<br>
Brute speed:<br>
RTX 4090 = ~550k/s<br>
RTX 5090 = ~800k/s<br>

https://github.com/user-attachments/assets/68ce9389-cf9a-4296-944e-3410db1f469f

## Mode 1

```bip39scan.exe --save Found.txt -a allbtc1.bin -t P2PKH --bloom 2048M -p m/44'/0'/0'/0/0-9 --bits 256```<br>
```bip39scan.exe --save Found.txt -a allbtc3.bin -t P2SH --bloom 2048M -p m/49'/0'/0'/0/0-9 --bits 256```<br>
```bip39scan.exe --save Found.txt -a allbc.bin -t bech32 --bloom 2048M -p m/84'/0'/0'/0/0-9 --bits 256```<br>
```bip39scan.exe --save Found.txt -a alleth.bin -t ethereum --bloom 4096M -p m/44'/60'/0'/0/0-9 --bits 256```

### Length of phrases
```--bits 64``` (random phrase 6 words)<br>
```--bits 96``` (random phrase 9 words)<br>
```--bits 128``` (random phrase 12 words)<br>
```--bits 160``` (random phrase 15 words)<br>
```--bits 192``` (random phrase 18 words)<br>
```--bits 224``` (random phrase 21 words)<br>
```--bits 256``` (random phrase 24 words)<br>
ex. ```bip39scan.exe --save Found.txt -a allbtc3.bin -t P2SH --bloom 2048M -p m/49'/0'/0'/0/0-9 --bits 128```

### Phrase Languages
If not specified, the default will be en<br>
```-l en``` English phrases<br>
```-l es``` Spanish phrases<br>
```-l fr``` French phrases<br>
```-l it``` Italian phrases<br>
```-l ja``` Japanese phrases<br>
```-l cs``` Czech phrases<br>
```-l ru``` Russian phrases<br>
```-l uk``` Ukrainian phrases<br>
```-l zh_Hans``` Chinese (Simplified)<br>
```-l zh_Hant``` Chinese (Traditional)<br>
ex. ```bip39scan.exe --save Found.txt -a allbtc3.bin -t P2SH --bloom 2048M -p m/49'/0'/0'/0/0-9 --bits 128 -l it```

<img width="978" height="325" alt="Image" src="https://github.com/user-attachments/assets/f525a4ab-209c-41b8-baab-ac6de917ddc8" />

<img width="976" height="370" alt="Image" src="https://github.com/user-attachments/assets/70f884ad-21dd-40d2-bcd6-c091033cc2a2" />

## Linux (ubuntu, hiveos)
The commands are the same as for Windows.<br>
You need to add in patch \ before '

```chmod +x bip39scan```<br>
``` ./bip39scan -a eth.txt --save Found.txt -p m/44\'/60\'/0\'/0/0-9 --bits 256```

## Database .bin
To avoid waiting for a long time for the addresses to be loaded into the program.<br>
Create and use binary databases.<br>
The program will start in seconds<br>
Create databases:<br>
BTC<br>
```bip39scan.exe --save Found.txt -a btc1.txt -t P2PKH --save-bin btc1.bin -p m/44'/0'/0'/0/0-9 --bits 256```<br>
```bip39scan.exe --save Found.txt -a btc3.txt -t P2SH --save-bin btc3.bin -p m/49'/0'/0'/0/0-9 --bits 256```<br>
```bip39scan.exe --save Found.txt -a btc-bc.txt -t bech32 --save-bin bc.bin -p m/84'/0'/0'/0/0-9 --bits 256```

ETH and tokens<br>
```bip39scan.exe --save Found.txt -a eth_addresses.txt --save-bin eth.bin -t ethereum -p m/44'/60'/0'/0/0-9 --bits 256```

Next launches run like this<br>
```bip39scan.exe --save Found.txt -a btc1.bin -t P2PKH -p m/44'/0'/0'/0/0-9 --bits 256```<br>
```bip39scan.exe --save Found.txt -a btc3.bin -t P2SH -p m/49'/0'/0'/0/0-9 --bits 256```<br>
```bip39scan.exe --save Found.txt -a bc.bin -t bech32 -p m/84'/0'/0'/0/0-9 --bits 256```<br>
```bip39scan.exe --save Found.txt -a alleth.bin --bloom 4096M -t ethereum -p m/44'/60'/0'/0/0-9 --bits 256```


Where can I download a fresh database of addresses?<br>
BTC and other coins https://blockchair.com/dumps<br>
Fresh ETH addresses + ETH Tokens taken from node dumps<br>
https://routescan.io/dumps?page=2&nexttoken=undefined<br>
Each address must be on a new line.<br>
Ethereum addresses must be 0x...<br>
Bitcoin addresses 1.., 3.., bc.. (New long addresses bc.. does not accept)

# Download ready-made address databases for bip39scan

**ALL ETH 1458757703 addresses with balance 09/07/2025** + empty + ALL ETH TOKENS with balance 09/07/2025 + empty history:<br>
ARBITRUM, AVALANCHE, BASE, BNB, BSC, BTT, CRONOS, CELO, ETC, Ethereumnie, ERA, ERC20, ETH, Ethered, FANTOM, <br>
GETH (Goerli), GNOSIS, IOTX, LINEA, MOONBEAM, MOONRIVER, OPBNB, OPTIMISM, POLYGON, VET, ZKEVM-POLYGON...<br>
Add these arguments to run ```--bloom 4096M -t ethereum```<br>

**Doesn't start on 8 GB cards! The database fits on a 12 GB card or more.** <br>
**To run you need 32 GB of RAM (if you don't have that much, you can use the swap file)** <br>
Download http://89.23.98.83/up/alleth.bin  **29 GB**

**ALL BTC addresses 1...** P2PKH with balance + empty (history)<br>
Add these arguments to run ```--bloom 2048M -t P2PKH```<br>
Download http://89.23.98.83/up/allbtc1.bin  **11.9 GB**

**ALL BTC addresses 3...** P2SH with balance + empty (history)<br>
Add these arguments to run ```--bloom 2048M -t P2SH```<br>
Download http://89.23.98.83/up/allbtc3.bin  **7.6 GB**

**ALL BTC addresses bc1q...** bech32 with balance + empty (history)<br>
Add these arguments to run ```--bloom 2048M -t bech32```<br>
Download http://89.23.98.83/up/allbc.bin  **6.5 GB**

## Addresses only with positive balance

Download ETH addresses 0x ```-t ethereum``` 20/05/2025<br>
http://89.23.98.83/up/eth.bin  **3.1 GB**

Download BTC addresses 1... 30/06/2025<br>
http://89.23.98.83/up/btc1.txt  **787 MB**

Download BTC addresses 3... 30/06/2025<br>
http://89.23.98.83/up/btc3.txt **240 MB**

Download BTC addresses bc... 30/06/2025<br>
http://89.23.98.83/up/bc.txt **842 MB**

I recommend using large address bases.<br>
For example, BCH may remain on the historical address 1... (P2PKH)

<hr>
Frequently asked question does bip39scan support Solana, Tron...? - No.<br>
You can hire a programmer, he will add the necessary coins, the source code comes with the program.<br>

There is an alternative option. Convert the coin addresses into Ripemd160 hashes. <br>
They must be optimized 000... 0ff<br>
Run the program with the solana.bin database, specify the coin type, for example -t P2PKH<br>
You will find an empty BTC address 1.. you don't need it!<br>
Take the found mnemonic phrase, generate an address tree or paste it into the application..<br>
Take the private key, generate a specific Solana address found. <br>
I don't have a Solana address database, haven't tried it, in theory it should work.<br>
<hr>

## Building on Windows VS-2022

Install cmake 3.30+ from this link: https://github.com/Kitware/CMake/releases/download/v3.31.8/cmake-3.31.8-windows-x86_64.msi<br>
Or find another version on this page: https://cmake.org/download/<br>

Install Visual Studio 2022 community: https://learn.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2022<br>
click the big Download button
 
Install Nvidia CUDA 12.9: https://developer.nvidia.com/cuda-downloads?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local<br>
choose Windows version
 
Install OpenSSL from https://slproweb.com/download/Win64OpenSSL-3_0_16.msi

Go to the "Sources" folder<br>
In cmd run: 

```cmake bip39scan```

The project files will appear in the folder:<br>
bip39scan.sln (run this file the project will open)<br>
bip39scan.vcxproj<br>
bip39scan.vcxproj.filters<br>
..

![brute bip39 phrases](https://github.com/user-attachments/assets/16e2197f-a01e-43ee-a02e-5b6f9e515e15)

OpenSSL should be found. If now, rename c:\program files\OpenSSL-Win64 to OpenSSL and re-run. Note that the libcrypto dll should<br>
be in PATH or in the current directory when running bip39scan.

 
Visual Studio 2022 opens. In the top toolbar choose: Release/x64.<br>
In the "Solution explorer" to the right, right-click bip39scan, choose "build".<br>
The executable builds in the your-build-directory\Release
 
![gpu brute bip39 mnemonic](https://github.com/user-attachments/assets/34d6574c-20a3-462c-a857-117ae9ae664f)

If necessary run precomp.exe file precomp.bin will be generated

## Building on Ubuntu:

Below is detailed instruction with bash commands required to build bip39scan.<br>
The symbol '$' denotes command prompt.<br>
If your prompt is shown as '#' on your terminal, skip 'sudo'.<br>
For example, instead of

$ sudo sh cuda_12.0.1_525.85.12_linux.run

you should run

sh cuda_12.0.1_525.85.12_linux.run

Let's start.

install CUDA. Download the linux version from the NVIDIA website and run.<br>
Open https://developer.nvidia.com/cuda-12-0-1-download-archive?target_os=Linux<br>
in your browser and choose your system. The following is valid for Ubuntu 18.04.

$ wget https://developer.download.nvidia.com/compute/cuda/12.0.1/local_installers/cuda_12.0.1_525.85.12_linux.run<br>
$ sudo sh cuda_12.0.1_525.85.12_linux.run

Skip the driver installation (deselect the 'driver' checkbox) if you already have it.

To ensure the cuda is installed, run:<br>
$ nvcc --version<br>

It should print information and version of CUDA.<br>
If no nvcc is found, try adding the CUDA bin path to the PATH variable:<br>
$ export PATH=/usr/local/cuda/bin:$PATH

install build-essential:<br>
$ sudo apt-get install build-essential

Check the gcc version:<br>
$ gcc --version

if the version is less than 9, install gcc 9:

$ sudo apt-get install software-properties-common<br>
$ sudo add-apt-repository ppa:jonathonf/gcc<br>
$ sudo apt-get update<br>
$ sudo apt-get install gcc-9<br>
$ sudo apt-get install g++-9<br>
$ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 10<br>
$ sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-9 10

install libssl:<br>
$ sudo apt-get install libssl-dev<br>
for the client-server version, install boost:<br>
$ sudo apt-get install libboost-all-dev

You will need Boost version at least 1.71. If apt-get does not intall at least 1.71, build Boost from source:
$ wget https://archives.boost.io/release/1.71.0/source/boost_1_71_0.tar.gz<br>
$ tar -xzvf boost_1_71_0.tar.gz<br>
$ cd boost_1_71_0<br>
$ ./bootstrap.sh --prefix=/usr && ./b2 stage threading=multi link=static<br>
$ sudo ./b2 install threading=multi link=static<br>
$ sudo ln -svf detail/sha1.hpp /usr/include/boost/uuid/sha1.hpp

install cmake from here: https://cmake.org/download/ choose Binary distributions, if that does not work - build from source<br>
$ wget https://github.com/Kitware/CMake/releases/download/v3.28.0/cmake-3.28.0-linux-x86_64.tar.gz<br>
$ tar -xzvf cmake-3.28.0-linux-x86_64.tar.gz

unpack the bip39scan source, let's say bip39scan/<br>
make an empty build directory, and run cmake in it e.g.<br>
$ mkdir bip39scan-build<br>
$ cd bip39scan-build

On first make, it will generate precomp.bin file, which may take quite some time. <br>
If you already have the precomp.bin, copy it to the build directory and comment this line in the ../bip39scan/CMakeLists.txt: add_dependencies(bip39scan precomp-bin) like this:<br>
#add_dependencies(bip39scan precomp-bin)

Save CMakeLists.txt and run cmake:
$ ../cmake-3.28.0-linux-x86_64/bin/cmake ../bip39scan<br>

where ../bip39scan is the source code directory<br>
make the project<br>
$ make bip39scan
