# Here is my instructions for my introduction to SDR
# Installs
## SDR++
I tried installing SDR++, but I couldn't figure out how to do it from the main github. I'll come back to this later, but for now I will look in to gqrx.

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
