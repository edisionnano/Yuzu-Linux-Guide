# Yuzu Linux Guide
## Prologue
Setting up yuzu can be a bit finicky, especially EA on Linux, but this guide aims to simplify the proccess through some small steps.
## Choosing the right methon
There are 2 ways to use Yuzu EA on linux, either using the pineapple script or the pineapple appimages. For big distributions which are either based on debian(like ubuntu), arch, RHEL (like fedora) and gentoo using the script is the optimal solution. The pineapple binaries are made as a portable means of using yuzu mostly for people who want to run Yuzu on amd hardware using a pendrive without installing linux or for people with obscure unsupported distributions like intel's Clear Linux to name one. The appimages include an updater but fall a bit short since they lack qtwebengine, some assets and more stuff to cut down on size due to the nature of appimages.
## Using PinEApple
If you are going to go the appimage route skip this step.<br/>
In order to use pineapple you must first install the dependencies.<br/>
The depedencies can be found [here](https://github.com/pineappleEA/Pineapple-Linux).<br/>
TIP:Install aria2 for faster download times.<br/>
After you install the dependencies it's highly recommend that you'd add the pineapple script as a command. Like the readme mentions all you have to do is append ```alias pineapple="curl https://raw.githubusercontent.com/pineappleEA/Pineapple-Linux/master/pineapple.sh | sh -s --"``` at the end of your shell configuration file (.zshrc or .bashrc on ~ depending on the shell you use), then you can call it using the command ```pineapple```.<br/>
We can now either call pineapple using it's command (after we restart our terminal emulator) or using ``curl https://raw.githubusercontent.com/pineappleEA/Pineapple-Linux/master/pineapple.sh | sh  -s --``.<br/>
![Initial screen](https://i.ibb.co/r0vh4ZL/guide1.png)<br/>
Once you do that you will be greeted with some self explanatory options. We want to download yuzu so we'll just type ```1``` and hit enter.<br/>

## Gathering the stuff you need
In order to use yuzu
