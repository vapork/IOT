---------------------------------------------------------------------------------------------------
Using CPUminer to mine DashCoin on Raspberry PI with Auto start at reboot and background processing
---------------------------------------------------------------------------------------------------

Installation, Build and Usage:

1. Update the Raspberry Pi:

   sudo apt-get update && sudo apt-get upgrade -y
2. Nix Build:


   sudo apt install git automake autoconf libcurl4-openssl-dev libjansson-dev libssl-dev libgmp-dev
3. Now clone my repo for CPUminer and builds:

   sudo git clone https://github.com/vapork/IOT
4. Go to the directory:


   cd IOT
7. Now build the script


   sudo ./autogen.sh
   sudo ./configure
   sudo ./build.sh
11. Setup an account on poolin, slushpool, minergate(these are trusted pools) or another mining pool
12. Use the credentials, select an algorithm to mine and make new worker with user and password.
13. Run cpuminer without password. We need to enter the email:


   ./cpuminer -a x11 -o stratum+tcp://dash80.suprnova.cc:80 -u vapork.user -p x
    
Autostart on Raspberry Pi boot:    
1. crontab -e
2. @reboot sudo /cpuminer-multi/cpuminer -a x11 -o stratum+tcp://dash80.suprnova.cc:80 -u vapork.user -p x
3. Ctr+x then Y to save

Background Process:
1. screen -S dash 
2. screen -r dash


[Latest cpuminer](https://travis-ci.org/tpruvot/cpuminer-multi.svg)](https://travis-ci.org/tpruvot/cpuminer-multi)

This is a multi-threaded CPU miner,
fork of [pooler](//github.com/pooler)'s cpuminer (see AUTHORS for list of contributors).



Credits:
CPUMiner-multi was forked from pooler's CPUMiner, and has been started by Lucas Jones.
* [tpruvot](https://github.com/tpruvot) added all the recent features and newer algorythmns
* [Wolf9466](https://github.com/wolf9466) helped with Intel AES-NI support for CryptoNight

License:
GPLv2.  See COPYING for details.
