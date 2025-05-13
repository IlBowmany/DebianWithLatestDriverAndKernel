# Debian with Latest Nvidia Driver and Kernel

Hi Everyone!

I love linux. I love it with all myself. And of it, I love Debian even more. It's my favourite distro, and always come back to it whenever I tend to have distro-hopping struggles.
The point is: If you are someone like me, who plays a lot and do 3D stuff, you will need latest Drivers and Nvidia Kernel for comfort reason (we will talk only about Nvidia, since I have a Nvidia laptop, and we all know how the most recent Nvidia drivers (575 of now) are great, much more then the 535 which Debian repos offers).
Debian is always regarded as a stable but not much updated distro, which can be good for someone, but for others it could be an issue.
That's why I'm writing this guide.

Following this guide, you will have a Stable Debian with latest kernel and Nvidia driver.

First of all, I recommend to do this with a clean and fresh Debian installation.

After you have Installed Debian, update it completely. Open a Terminal and write:

```
sudo apt update
```

```
sudo apt upgrade
```

After everything has been properly updated, let's update the Kernel with the Liquorix one, (Their Website: https://liquorix.net/ , I hope they don't change the script in the future, otherwise the one down here will be outdated!) :

```
curl -s 'https://liquorix.net/install-liquorix.sh' | sudo bash
```

After the kernel has been properly installed, reboot the PC.

Open Terminal again, and write:

```
sudo apt install wget

wget https://developer.download.nvidia.com/compute/cuda/repos/debian12/x86_64/cuda-keyring_1.1-1_all.deb

sudo dpkg -i cuda-keyring_1.1-1_all.deb

sudo apt-get update

sudo apt install cuda-drivers
```

After the driver have been completely installed, reboot again.
Check if everything works properly by writing on Terminal "nvidia-smi"
If it shows you a small log with your graphic card name and driver installed, then we are good to go and everything went well!

To end all this, let's install the 32 bit libraries too (useful for WINE and Steam):

```
sudo dpkg --add-architecture i386

sudo apt update

sudo apt install nvidia-driver-libs:i386
```

After this, reboot again.


Aaaand we are good to go! Debian right now is updated with the latest kernel and nvidia drivers without any issue!

For any issue or problem let me know!
Thanks for reading this guide.

