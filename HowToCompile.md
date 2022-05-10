# [archAhazi's](https://github.com/archAhazi/FlipperZeroBuildNotes) Notes on modifying firmware for the Flipper Zero

I am using Windows 10 (64-bit) on a laptop

# Prerequisites

Install Git

    https://git-scm.com/downloads

Install VSCode

    https://code.visualstudio.com/docs/?dv=win
    
Install Docker

    Install [Docker Engine and Docker Compose](https://www.docker.com/get-started)
    
Install qFlipper

    https://flipperzero.one/update
    
# Clone the Firmware repository

Create the project directory in a prferred location on your harddrive.
Go into the folder

Get the firmware from FlipperDevices
Open the command prompt (I ran as admin, donno if it matters)
```sh
git clone https://github.com/flipperdevices/flipperzero-firmware.git
```

I also made sure to download any submodules while still in the flipperzero-firmware directory
```sh
git submodule update --init
```
#  Do your Code thing

Make modifications to the firmware
    DroomOne has a good starter for that
    
    https://github.com/DroomOne/Flipper-Plugin-Tutorial
    
#  Docker Time

I deep dived into Docker to understand it better, sorry no TL;DR for what I learned.
Watch some videos and RTFMan
     This video was very helpful.  Well worth the 90 minutes 
     
     https://www.youtube.com/watch?v=3c-iBn73dDE
     
Prepare the container:

 ```sh
 docker-compose up -d
 ```

Compile everything
    This step initially dod not work for me originally because I had downloaded the repository and not CLONED it 
    and did not git the submodules as referenced above.
```sh
docker-compose exec dev make
```

Check `dist/` for build outputs in the f7 folder.
The dist folder is in your project directory with all the other firmware repository files.

# Install Firmware!!!

Plug in your flipper to your Windows 10 computer.

Open qFlipper.

Click the Install from file below the big INSTALL button

Find your .dfu file in the dist/f7/ folder and Open

# PROFIT!!!
