
## Windows Setup Instructions

In this course we will be using a unix terminal. Since it may be difficult to debug many different computers with many different configurations, I ask that all Windows users install Ubuntu, a linux based operating system.

The following are the options for booting Ubuntu on a Windows computer. I reccomend "Option 1": setting up Ubuntu inside a virtual machine on Windows.

1. **Option 1** (recommended) - If your computer is fast enough, run Ubuntu inside a virtual machine. Instructions to do this are below. This [link](http://www.psychocats.net/ubuntu/virtualbox) does a good job of explaining the benefits of this option.
2. **Option 2** - Boot Ubuntu [off of a flash drive](https://unetbootin.github.io/). This might be a good option if your computer is proving too slow to run Ubuntu in a Virtual Machine. You can boot the operating system off a flash drive rather than your hard-drive. This will work best with a USB 3.0 capable flash drive.
3. **Option 3** [Dual boot](https://help.ubuntu.com/community/WindowsDualBoot) Linux and Windows on your computer. This is recommended only for advanced users because it involves making major changes to your hard-drive. Make sure to back up all of your files before installing the new operating system.

### Setting up a virtual machine
* Download [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
* Download the [Ubuntu ISO](https://www.ubuntu.com/download/desktop)
* Make sure resource virtualization is enabled in the bios for your computer (this will vary based on the computer you have)
* Create a new "Ubuntu" virtual box, when you first open the virtual box, a prompt will pop up

	![](https://www.evernote.com/shard/s150/sh/e26bb014-0fd8-4bb2-93f5-18f55d5169ec/83abe0b21d90e39a/res/cbc6682a-8f44-43de-abe8-6ed8da6a7fee/skitch.png?resizeSmall&width=832)

* Select the folder icon and find your ubuntu ISO and hit "start"
* Follow the on-screen instructions to "install ubuntu"
* Jump up to the "Ubuntu" section of this document and follow those rules inside the virtual box.

### Enable "Bash on Ubuntu on Windows 10" (if you have Windows 10)
Ideally we won't be using this feature, but as a backup, please follow these instructions to enable it.

* Enable Bash for Windows 10 [[instructions](http://www.windowscentral.com/how-install-bash-shell-command-line-windows-10)]
