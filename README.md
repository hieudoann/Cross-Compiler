Cross-Compiler Instructions
Check Your Raspberry Pi’s Architecture
Open a terminal and run the following command:

bash
gcc -dumpmachine
Ensure it shows arm-linux-gnueabihf or a similar architecture.

Download the Matching Toolchain
Download the toolchain from this link: **https://shorturl.at/binzO**

Extract the Toolchain
Run the following command to extract the toolchain:

bash
tar -xvf gcc-arm-*.tar.bz2

Add the Toolchain to Your PATH
Export the toolchain’s path to your environment variables:

bash
export PATH=/path/to/gcc-arm-10.3-2021.07/bin:$PATH
Replace /path/to with the folder where the toolchain was extracted.

Cross-Compile Your Code
Use the following command to cross-compile your code:

bash
arm-none-linux-gnueabihf-gcc -o my_app my_code.c
Adjust file names (my_app, my_code.c) as needed.

Transfer the Compiled Binary to the Raspberry Pi
Use the scp command to copy the compiled binary to your Raspberry Pi:

bash
scp -P 5022 my_app pi@<raspberry_pi_ip>:/home/pi/
Replace <raspberry_pi_ip> with your Raspberry Pi’s IP address. Adjust the port (5022) if needed.

Run the Application on the Raspberry Pi
SSH into your Raspberry Pi and run the application:

bash
./my_app
