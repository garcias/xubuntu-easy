# xubuntu-easy
Vagrantfile to set up a quick and easy Xubuntu desktop environment for students who don't want to use ssh

## What is this for?

Suppose you are teaching students some kind of computing and you use VMs to ensure a reproducible environment. Normally you would interact with environment through SSH or maybe through browser-based admin portal. But maybe you decide some or all the students are better off starting with an interface that resembles a local desktop environment. 

In that case, you can install a lightweight desktop GUI (in this case Xfce) and have Virtualbox run in GUI mode. This Vagrantfile helps you do that, creating an Ubuntu 14 machine and installing:

- Xfce
- Chrome
- Visual Studio Code

## How to use it?

Download Vagrant and Virtualbox, using directions appropriate for your OS. Then clone this repository and run. You need to reload for the desktop GUI to be available.

```bash
    > git clone https://github.com/garcias/xubuntu-easy.git xubuntu
    > cd xubuntu
    > vagrant up && vagrant reload
```

Log in as the Vagrant user, with password `vagrant`. On the desktop, *right click* > *Create Launcher* and type in "Chrome" ... it should detect metadata from the Chrome package and fill in the location of the binary and an icon. After the icon appears on desktop, open it and *Mark as executable*. Repeat for VS Code.

## Is this the only way?

There are alternatives:

- Managed laboratory, like CoCalc or Cloud9 Education (especially if students' computers are mostly thin clients)
- Install Cloud9 IDE on VM and access through browser

