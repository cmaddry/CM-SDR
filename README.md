# Here is my instructions for my introduction to SDR
# Installs
## SDR++
### First attempt
I tried installing SDR++, but I couldn't figure out how to do it from the main github. I'll come back to this later, but for now I will look in to gqrx.
###  Second attempt with [this](https://www.aaronrombaut.com/build-sdr-on-raspberry-pi-5/)

Ran:
```sh
sudo apt install -y cmake libad9361-dev libairspy-dev libairspyhf-dev libfftw3-dev libglfw3-dev libhackrf-dev libiio-dev librtaudio-dev libvolk2-dev libzstd-dev
```

Got the following error:
```bash
Errors were encountered while processing:
 xtrx-dkms
E: Sub-process /usr/bin/dpkg returned an error code (1)
```

I ignored this and continued to build SDR++:
```bash
cd ~/Downloads
wget https://github.com/AlexandreRouma/SDRPlusPlus/archive/refs/heads/master.zip
unzip master.zip
cd ~/Downloads/SDRPlusPlus-master
mkdir build
cd build
cmake ..
make -j4
```

This actually worked just fine so then I moved onto installing SDR++
```bash
## This creates a root?
cd ..
sh ~/Downloads/SDRPlusPlus-master/create_root.sh

## The actual installation
cd ~/Downloads/SDRPlusPlus-master/build
sudo make install
```

Tested to see if it succesfully installed by running:
```bash
sdrpp
```
IT WORKED!!

After messing around with SDR++ and my RTL-SDR, I started to lose faith in my fix. I can't seem to get any signal out from my antenna. When using gqrx, I was able to at least get some FM stations. I'll look into this some more and see what my issues might be.

## Gqrx
To install gqrx, I ran the commands found [here](https://www.gqrx.dk/download/gqrx-sdr-for-the-raspberry-pi). 

Or,
```bash
sudo apt-get update 
sudo apt-get install -y cmake gnuradio-dev gr-osmosdr qt6-base-dev qt6-svg-dev qt6-wayland libasound2-dev libjack-jackd2-dev portaudio19-dev libpulse-dev
git clone https://github.com/gqrx-sdr/gqrx.git
cd gqrx/
mkdir build 
cd build
cmake ..
make
sudo make install
```

Then, to make sure it was successfully installed, I ran `gqrx` and I think it worked.

# CM-SDR
