Note: super slow gazebo sim (~4.66%) if ran through putty > scrap
Shutdown with ACPI shutdown

VBox
Ubuntu Server 22

Putty
Vcxsrv (Xlaunch)


Requirements

Download Ubuntu Server 20.04 LTS https://ubuntu.com/download/server

Download link: https://releases.ubuntu.com/20.04.5/ubuntu-20.04.5-live-server-amd64.iso

Install VirtualBox

For Enrolled Intune: Install VirtualBox using the company portal

For unsupported: Download Oracle Virtualbox https://www.virtualbox.org/wiki/Downloads

Install Visual Studio Code (vscode) https://code.visualstudio.com/docs/?dv=win

# Create a Virtual Machine
Name your VM. Make sure type is Linux and version is (Ubuntu 64-bit)

Set memory size. I recommend using half of your physical machine’s RAM.

Create a hard disk. For hard disk file type, default VDI (Virtualbox Disk Image) and Dynamic Allocation

should be fine.

            
            
For the upper limit in disk space, you can set it around 100 GB. You can resize this later. (Would recommend just setting it at 200GB from the get go! saves you hassle. RJ faced it here. -kt)

Press create and your empty virtual machine should be available

Right click VM > Go to Settings

Go to System > Processor

Set number of processors to half of your physical machine’s cores. I set mine to 4 cores

Go to Storage tab > Click on the Empty slot below the IDE Controller > Click the disk icon in the right sidebar > Choose a disk file

Choose your downloaded Ubuntu Server ISO then press OK.

Double click your VM to boot it up. Start it with your Ubuntu 20 server ISO

if VM cannot boot up, encountering “VT-x is disabled in the BIOS”, please check Troubleshooting section

VM should boot up to the installation screen

# Installation
Installation is pretty straight forward. I keep it minimal as possible so I don’t need to wait that much so feel free to breeze through the default settings.

Skip this

Use entire hard disk

You can use the recommended partition table

Don’t be afraid of this prompt, trust me and select continue

Add your name and username as well as an edgy server name. Will use this later for SSH config.

           
Install OpenSSH server, we will need this later to connect from Windows Host to this box.

Proceed by selecting Done. There’s a screen for selecting optional packages, I prefer to skip this since I can install them later anyway.

Proceed again by selecting Done, then installation should start.

Press ENTER.

Installation will complete, then select Reboot Now

You now have a working Ubuntu Server box!!!

Press enter for the login prompt to appear. Login with your username and password.
(Note: Your password will not appear when you type it but don't panic. Just type it then press enter and you will be logged in.)

# Troubleshooting
Error: VM keeps turning off after going through guided VBox setup

Not in a hypervisor partition (HVP=0) (VERR_NEM_NOT_AVAILABLE). VT-x is disabled in the BIOS for all CPU modes (VERR_VMX_MSR_ALL_VMX_DISABLED). 
Solution:

Ask admin access from @security-team

Enter BIOS video 1:26 onwards

Enable virtualization in BIOS
# Setting up VSCode to connect to our Linux box
Install Remote - SSH extension from the VSCode Extension Marketplace. Once installation is done, restart VS code for the Remote Explorer tab to appear under the Extension Marketplace.

In the Remote Explorer tab, click the gear button and select your SSH config. SSH configs are normally placed inside <YOUR_WINDOWS_USERNAME>\.ssh\config so create the file if you don’t have it yet.

Add another entry for our new Linux box in the ssh config

Sample SSH config

Host nexus
  Hostname localhost
  User ncdejito

Host - Can be anything or the server name you used in the installation. ProTip: make it the most easiest to type

User - the username you used in the installation part

Open cmd.exe and generate an SSH key. If you already have an SSH key, you can skip this

ssh-keygen -t ed25519 -C "<INSERT_YOUR_EMAIL_HERE>" 
Enter the file in which to save the key or leave it empty and just press “Enter”.

Copy the pubkey from C:\Users\<YOUR_WINDOWS_USERNAME>\.ssh\config\id_ed25519.pub.

NOTE: Copy your PUBLIC KEY not your PRIVATE KEY. Public key is inside the .pub file

I censored my own pubkey so you won't copy. It's not sensitive since it's a PUBKEY

Setup Port Forwarding Rules for your Linux Box

Create Port Forwarding Rules.

These port numbers are usually the ports we use for web development. Feel free to add more ports when needed.

Optional: Add another Rule for Host Port 9200 and Guest Port 9200 for Elasticsearch connection

Open your Linux box using Headless Start

Open cmd.exe in Windows and SSH to your Linux box

ssh <YOUR_LINUX_USERNAME>@127.0.0.1
Paste your pubkey in ~/.ssh/authorized_keys

nano ~/.ssh/authorized_keys
ProTip: Use Right-Click to paste

Exit your SSH session. Then try to SSH again, it should not prompt for a password anymore. Hooray!

Open VSCode again then select your Linux Box from the SSH targets list

This will open a new VSCode window. Select Linux as the platform. VSCode will download VSCode Server

Open Terminal inside VSCode `Ctrl + ~` Or go to Terminal > New Terminal

Now you have a fully working headless Linux environment. Does it feel like WSL2 but better?

❗DON’T FORGET to PROPERLY shut down the VM after use.
How? See the screenshot below.

If you don’t properly shut it down, you’re gonna run into errors the next time you turn it on.

In case you still forgot to properly shut it down even after reading this warning (😢), Shut Down - Turn On your computer until it works again lol.

# Mounting Host filesystem to the Linux Box
I mostly use this when I need a file downloaded from the Host’s browser then I need to open it inside the Linux Box

Install VirtualBox Guest Additions

sudo apt update
sudo apt install --no-install-recommends virtualbox-guest-dkms virtualbox-guest-x11 
Reboot VM

sudo reboot
Check if kernel module is loaded

lsmod | grep vbox


Go to your Settings > Shared Folders > Click + icon in the right hand side

Add a folder path from the host system that you want to mount to the Linux filesystem. I usually use my Windows Downloads folder for convenience.

Inside /media you will find your mounted Machine Folder

This contains the files of your Windows download folder if set right.

# Troubleshooting
If you encounter Permission denied when accessing a Shared Folder using a terminal, try to turn the VM off and on. The folder was probably not mounted properly by VirtualBox.

# Running Linux GUI Apps
Install Putty https://www.putty.org/

Install Vcxsrv Windows X server https://sourceforge.net/projects/vcxsrv/


Open Putty

Create a new Session
127.0.0.1

Connection > Data: Set your username here
ncdejito

Go to Connection > SSH > X11 > Check Enable X11 Forwarding

You can create a ppk based of your id_rsa private key for Putty so you wouldn’t have to put password here

Install sample x11 apps

sudo apt install x11-apps
Run Vcxsrv(XLaunch)

Start with no client

Inside the Putty Terminal, run sample x11 app to test X server forwarding

xclock &
xeyes &
This is super useful when running test automation frameworks like Cypress.

