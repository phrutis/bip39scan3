# bip39scan v 3.2 + Vulnerable generator libbitcoin v3.2 - For sale $500
To purchase, write to telegram ```@phrutis``` or buy from a bot in a group [t.me/cuda8](https://t.me/cuda8)<br>
The program is sold with the source code (cmake VS2022) + ready-made programs (multigpu) for win, lin, hiveos, Ubuntu 20.04 (22.04)<br>
**There are 2 previous versions in folder BONUS for free [bip39scan v1](https://github.com/phrutis/bip39scan) + [bip39scan v2](https://github.com/phrutis/bip39scan2) + (with sources)**

More about the vulnerability Milk Sad:<br>
RU https://habr.com/ru/articles/771980/<br>
EN https://milksad.info<br>
EN https://milksad.info/disclosure.html#codename-milk-sad<br>
 
Vulnerability 32 bits in each length, each language.<br>
The point is that 32 bits is not a large number of only 4294967296 phrases<br>
At first glance it seems that at a speed of 500k/s it is only 2-3 hours???<br>
How to find all 4294967296 phrases in random mode???<br>
This is almost impossible.<br>
Each phrase is random, after going through 4294967296 combinations, you will find 30% of phrases, 70% will be duplicates.<br>
You will go through another 1000000000 combinations, you will find 20%.<br>
To find the next 10% of unique phrases, you need to go through many times more combinations than before.<br>
Therefore, it is impossible to find all the phrases.<br>
Therefore, there is a high chance of finding a phrase with a positive balance that you could not find before.<br>
Taking into account the different lengths and languages, this gives even more opportunities to find.<br>
Let's add some non-standard patches and different coins here<br>
Not everyone knows about this vulnerability. Some sites and applications still use this vulnerable library.<br>
Therefore, the chance to find a fresh coin is very high. Update your address databases.<br>
The main advantage of bip39scan v3 is its high speed!

Only CUDA cards support GTX, RTX, CMP<br>
Brute speed:<br>
RTX 4090 = ~550k/s<br>
RTX 5090 = ~800k/s<br>

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
```bip39scan.exe --save Found.txt -a btc-bc.txt -t bech32 --save-bin bc.bin-p m/84'/0'/0'/0/0-9 --bits 256```

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

