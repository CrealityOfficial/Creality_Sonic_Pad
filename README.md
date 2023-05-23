# __Firmware Helper__

https://github.com/CrealityOfficial/Creality_Sonic_Pad_Firmware.git

# __Faq  Helper__

https://www.creality.com/pages/faq?spm=..page_2450731.header_1.1&spm_prev=..page_1934481.products_display_1.1

# __Os  Helper__

https://github.com/CrealityTech/sonic_pad_os

# __User defined firmware compilation guide__

Using Linux subsystem under Windows 10 64-bit
	Download and install VirtualBox
Download VirtualBox from www.VirtualBox.org
	Download Ubuntu 18.04.LTS
Download Ubuntu 18.04.LTS from www.ubuntu.com/download
	Create a new virtual machine and install Ubuntu system
1.	Open VirtuslBox and create a new virtual machine
2.	Select destination folder、Enter a name，Type: Select Linux、Version: Select Ubuntu（64-bit）
3.	Resize memory to 4096MB
4.	Create a virtual hard disk
5.	Select VDI
6.	Select dynamic allocation
7.	Resize the virtual hard disk to 25GB
8.	General Settings – Advanced，Change the shared clipboard and the drag and drop to bidirectional
9.	System settings - adjust the boot order to optical drive - hard disk - floppy drive
10.	Storage Settings--IDE--Select Downloaded Ubuntu 18.04.6LTS
11.	SATA--tick Use Host I/0 Cache
12.	Network Settings - Advanced - Make sure the network is connected
13.	User Interface -Device-Tick Insert Guest additions CD image
14.	Start the virtual machine after confirmation
15.	Install Ubuntu
	System upgrade and install git 
1.	run command  sudo apt update （list all updatable software）
2.	run command  sudo apt upgrade  （upgrade the package）
3.	Devices -- Install Insert Guest additions CD image
4.	run command  sudo apt-get install git（install git）
5.	Restart the system
	Download Klipper firmware
1.	run command cd ~ (switch the working directory to the home directory)
2.	run command git clone  
   https://github.com/CrealityOfficial/Creality_Sonic_Pad_Project.git
	Configure printer firmware
1.	Open the file manager-Klipper folder-scripts folder-Right click-open in terminal
2.	run command ls (confirm that the content in the current directory is consistent with that in the folder)
3.	run command ./install-ubuntu-18.04.sh（install ubuntu）
4.	run command cd .. (switch to the upper directory)
5.	run command ls (confirm that the content in the current directory is consistent with that in the folder)
6.	run command make menuconfig (configure the printer motherboard)
7.	Select the Micro-controller Architecture、Processor model、Bootloader Offset、Clock Reference、Communication interface etc. parameters
8.	After the parameter configuration is completed, press "Q" to save，Press "Y" to confirm
9.	run command make （generate firmware）
	Upgrade printer firmware via SD/TF card
1.	Create a new "ubuntu_sharing" on the computer disk
2.	Open VirtualBox--Settings--Shared Folders，Add a shared folder (tick auto mount)，Mount point type "/sharings"
3.	Copy the klipper.bin file just generated to the sharings folder
4.	Copy klipper.bin in the ubuntu_sharing folder of the computer disk to the TF/SD
	Upgrade printer firmware via USB
(The motherboard has no Bootloader and does not support SD card upgrades)
Please use a USB cable to connect the printer to the computer 
where the virtual machine is located. Please keep the connection 
during the firmware upgrade process
1.	Refer to the previous video to enter the configuration  motherboardinterface、Select the Micro-controller Architecture、 Processor model、Clock Reference、Communication interface etc. parameters
2.	After the parameter configuration is completed, press "Q" to save，Press "Y" to confirm
3.	run command make （generate firmware）
4.	Device--USB--Tick the USB option for connection to the printer
5.	run command ls /dev/tty*(Confirm that /dev/ttyUSB0 appears in the directory)
6.	run command sudo avrdude -cwiring -patmega2560 -P/dev/ttyUSB0 -b115200 -D -Uflash:w:out/klipper.elf.hex:i（Transfer the klipper firmware to the printer for upgrade，Note the space before the "-" in the command）
