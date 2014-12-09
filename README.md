# Target Display Mode Service

## Description

This is a very basic [Sinatra](http://sinatrarb.com) service which provides a way to toggle
your iMac in/out of [Target Display Mode](http://support.apple.com/en-us/HT3924)

#### Installation

Please note, these instructions assume you are running from the
terminal.  To use tdm, clone the repo, run bundle and start the
service script, ie.

    git clone https://github.com/jasonm23/tdm.git
    cd tdm
    bundle

You should install this on the machine(s) you want to use as a slave
monitor with [Target Display Mode](http://support.apple.com/en-us/HT3924).

#### Startup

From the folder where you cloned this repository, enter:

    ./tdmservice


The assumption is that you'll want to cancel it when you have your
display back, so there are no instructions for installing this script
as a daemon.

#### Usage

This service is useful if you don't have a modern Apple keyboard on
the iMac which you want to use as the slave display.

Connect up the two machines via a Thunderbolt† (or mini DisplayPort‡) cable.

Install and start `tdmservice` as described above.

Make a note of the computer name of the slave iMac (open System
Preferences > Sharing)

> Computers on your local network can access your computer at:
> **computer-name**.local

Move over to the master machine (which will be using the slave
display) open a web browser at
`http://computer-name.local:5678/toggle`. Replace **computer-name.local**
with the name of the slave machine, which you saw in **System
Preferences > Sharing** on the other machine.

The slave machine should switch into Target Display Mode.

Just for laughs, refresh the browser page and the slave machine should
switch off Target Display Mode.  Turn on/off just by refreshing this
page, you may want to bookmark it for future use.

#### Notes on Thunderbolt / DisplayPort cables

* † For Target Display Mode, genuine Thunderbolt cables are
  required for newer iMacs (ie. if the port is specified as a Thunderbolt
  port in the system info, it is necessary to use a Thunderbolt cable.)
  Older iMacs can use both Thunderbolt and mini DisplayPort cables.

* ‡ If either of the machines is has a Thunderbolt port (instead of a
  mini DisplayPort) a Thunderbolt cable is still necessary. For
  example, if your master machine is a newer MacBook Pro or MacBook
  Air, it will be a Thunderbolt port.

#### Notes on Keyboards

Only the latest Apple Keyboards
([wireless](http://deskthority.net/w/images/d/dd/MC184LLA-Entire.jpg)
or [wired](http://deskthority.net/w/images/e/e8/A1243_full.jpg)) which
have an `Fn` key, will activate Target Display Mode (to the best of my
knowledge.)

It is possible to fix this on other keyboards, by using Karabiner to
fix the F2 key (or any key of your choice to send key code 144 +
Command Modifier flag.)

The code to send is `KeyCode::VK_CONSUMERKEY_BRIGHTNESS_UP`. See the
[Karabiner project](https://github.com/tekezo/Karabiner) for more info.

## Licence

GNU/GPL2
