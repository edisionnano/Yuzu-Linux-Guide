# Yuzu Linux Guide
## Prologue
Setting up yuzu can be a bit finicky, especially EA on Linux, but this guide aims to simplify the proccess through some small steps.
## Choosing the right method
There are 2 ways to use Yuzu EA on linux, either using the pineapple script or the pineapple appimages. For big distributions which are either based on debian(like ubuntu), arch, RHEL (like fedora) and gentoo using the script is the optimal solution. The pineapple binaries are made as a portable means of using yuzu mostly for people who want to run Yuzu on amd hardware using a pendrive without installing linux or for people with obscure unsupported distributions like intel's Clear Linux to name one. The appimages include an updater but fall a bit short since they lack qtwebengine, some assets and more stuff to cut down on size due to the nature of appimages.
## Using pinEApple
If you are going to go the appimage route skip this step.<br/>
In order to use pineapple you must first install the dependencies.<br/>
The depedencies can be found [here](https://github.com/pineappleEA/Pineapple-Linux#dependencies).<br/>
TIP:Install aria2 for faster download times.<br/>
After you install the dependencies it's highly recommend that you'd add the pineapple script as a command. Like the readme mentions all you have to do is append ```alias pineapple="curl https://raw.githubusercontent.com/pineappleEA/Pineapple-Linux/master/pineapple.sh | sh -s --"``` at the end of your shell configuration file (.zshrc or .bashrc on ~ depending on the shell you use), then you can call it using the command ```pineapple```.<br/>
We can now either call pineapple using it's command (after we restart our terminal emulator) or using ``curl https://raw.githubusercontent.com/pineappleEA/Pineapple-Linux/master/pineapple.sh | sh  -s --``.<br/>
![Initial screen](https://i.ibb.co/MVYPF5f/guide1.png)<br/>
Once you do that you will be greeted with some self explanatory options. We want to download yuzu so we'll just type ```1``` and hit enter.<br/>
The programm will start downloading, extracting and compiling Yuzu. If you have an nvidia GPU the magic number screen will show up.<br/>
![Magic Number screen](https://i.ibb.co/Yj3SYWr/guide2.png)<br/>
This is a simple fix for vulkan outright crashing on nvidia GPUs when starting a game, you can use many different values to find what works best for your hardware.<br/>
TIP:If you want to force the Magic number screen to show up use the ```-n``` flag at the end of the command you use to run pineapple.<br/>
The compilation should be pretty fast but if you aren't satisfied with it you can speed up the proccess upto 10 times by using ccache. To do this install the ccache package of your distribution and either append ```export PATH="/usr/lib/ccache/bin/:$PATH"``` at the end of your shell configuration file to use it globally or run this command everytime before running pineapple to use it only with pineapple.<br/>
When the compilation finishes you will be asked whether you want to install yuzu or not, it is recommended that you do so by typing ```y``` and pressing enter. You will be asked for your password (in linux when typing your password you won't see ****** or any other visual hint) and then you should be notified that the compilation proccess finished successfully.<br/>
You can now either run it using the command ```yuzu``` or from your app launcher.<br/>
![The launcher](https://i.ibb.co/qWZgMP9/launcher.png)<br/>
You can also choose not to install Yuzu by typing ```n``` and hitting enter.<br/>
If you do so, you will find the yuzu binary in a folder called earlyaccess on your home foler (~).<br/>
From there you can just execute it like a common Yuzu mainline linux binary (either click it or run it using ./yuzu from a terminal emulator).
## Using Appimages
WARNING:Appimages are still experimental.
pinEApple now distributes Appimages too thanks to qurious. In order to use them just grab one from [here](https://github.com/pineappleEA/pineappleEA.github.io/releases) (it's the one named ```yuzu-x86_64.AppImage```).<br/>
Just run it by double clicking it, that's it, no dependencies.<br/>
Binaries are also available and just like the official Yuzu mainline binaries they still need dependencies, they are also built without qtwebengine since the Appimages derive from these binaries.
## Gathering the stuff you need
In order to use yuzu you'll need the bellow things:
- [prod.keys](https://raw.githubusercontent.com/emuworld/aio/master/prod.keys) - Since yuzu doesn't support decrypted rom formats you'll need these to decrypt your games.
- Firmware (optional) - This includes shared fonts, Miis and some other misc stuff (aHR0cHM6Ly9kYXJ0aHN0ZXJuaWUubmV0L3N3aXRjaC1maXJtd2FyZXMv).
- Base ROM (NSP or XCI) - These are the only formats supported by Yuzu, NSPs derive from the Nintendo webstore while XCIs are cartridge dump, NSPs are smaller so grab these since they don't include firmware and other stuff.
- Update - Updates fix games in many ways, most of the times you want the latest version but some other times it may not be compatible with Yuzu or the mods you are using yet.
- DLC - Downloadable content expands the games so you do want those.
- [Mods](https://github.com/yuzu-emu/yuzu/wiki/Switch-Mods) - Mods fix games or enhance them in many ways, take a look if the games you wanna play are on the list and grab the ones you want.
TIP:Do not download shader caches for yuzu, they get invalidated, it's recommended that you build your own shader cache.
## Getting Started and Configuration
Create a folder on your home folder called ```.switch``` and drop prod.keys inside (if you can't see hidden folders press Ctrl+H), these keys will be used by Ryujinx too.<br/>
After that you open Yuzu and navigate to ```Install Files to NAND...``` in the File menu, from here you can mass install all your updates, DLC and even games (although it is recommended you don't install games).<br/>
We can now start configuring the emulator, go to Emulation > Configure.<br/>
Most options in the General section are upto personal preference but it is recommended that you do not enable Discord Presence since you may be noticed by Yuzu stuff using an EA build.<br/>
In the System section, in the System tab you want to use your corresponding time zone since this is used by games like Animal Crossing:New Horizons for the ingame day-night cycle. In the profiles tab create a new profile called whatever you want and delete the default yuzu profile, this may fix crashes in games like Super Smash Bros Ultimate. In the Services tab you change BCAT Backend from none to Boxcat in order to get events in games, if you ever get any issues try disabling it again.<br/>
In the Graphics section and Graphics tab you can choose your Graphics Api, it is recommended that you use OpenGL since it works fine in linux and Vulkan has memory leaks. In the Advanced tab you can disable assembly shaders if you don't have nvidia or you have any problems with newer drivers(like flashing picture in Super Mario Odyssey).<br/>
And last but not least in the Controls section you can configure your controller, it is recommended that you use Pro Controller for docked and Joy cons for handheld. Don't forget to save your profile once you are done.<br/>
Yuzu takes a painstackingly long time to search subfolders for ROMs so it is recommended that you create a folder and drop all the base games in the root of this folder.
