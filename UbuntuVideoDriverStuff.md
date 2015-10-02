Check which video driver is in use:
        
    $ sudo lshw -c video
    [sudo] password for rakrao: 
    *-display               
       description: VGA compatible controller
       product: GK107GLM [Quadro K1000M]
       vendor: NVIDIA Corporation
       physical id: 0
       bus info: pci@0000:01:00.0
       version: a1
       width: 64 bits
       clock: 33MHz
       capabilities: pm msi pciexpress vga_controller bus_master cap_list rom
       configuration: driver=nouveau latency=0
       resources: irq:44 memory:f2000000-f2ffffff memory:e0000000-efffffff memory:f0000000-f1ffffff ioport:5000(size=128) memory:f3080000-f30fffff

Check installed drivers:

    sudo lsmod | grep -e nvidia -e nouveau

    sudo modprobe nvidia
    
    sudo modinfo nvidia_331

    less -p "nvidia|nouveau" /var/log/Xorg.0.log

    sudo lspci | grep -i nvidia
    sudo lspci -vnn | grep -i VGA -A 12
    sudo inxi -xG

    sudo glxinfo | egrep 'vendor|version'


http://forums.linuxmint.com/viewtopic.php?f=90&t=174434#p899831

###nomodeset
The newest kernels have moved the video mode setting into the kernel. So all the programming of the hardware specific clock rates and registers on the video card happen in the kernel rather than in the X driver when the X server starts.. This makes it possible to have high resolution nice looking splash (boot) screens and flicker free transitions from boot splash to login screen. Unfortunately, on some cards this doesnt work properly and you end up with a black screen. Adding the nomodeset parameter instructs the kernel to not load video drivers and use BIOS modes instead until X is loaded.

Note that this option is sometimes needed for nVidia cards when using the default "nouveau" drivers. Installing proprietary nvidia drivers usually makes this option no longer necessary, so it may not be needed to make this option permanent, just for one boot until you installed the nvidia drivers.
