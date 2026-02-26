hey, you're in the readme

follow the pdf tutorial to install it
if you don't have the pdf, you can just go to https://wiki.archlinux.org/title/Installation_guide i guess since it's the same thing

once installed, this is how to install a desktop environment:


find your gpu to install a driver (not required if you know your gpu)
lspci | grep -E "VGA|3D"

install drivers

intel
sudo pacman -S mesa xf86-video-intel

amd
sudo pacman -S mesa xf86-video-amdgpu

nvidia
sudo pacman -S nvidia nvidia-utils

you should probably reboot after this but not really required
to reboot
sudo reboot

install xorg
sudo pacman -S xorg


choose a desktop environment (either gnome, kde plasma, or xfce

to install gnome
sudo pacman -S gnome gnome-extra

enable display manager for gnome
sudo systemctl enable gdm

to install kde plasma
sudo pacman -S plasma kde-applications

enable display manager for kde plasma
sudo systemctl enable sddm


to install xfce
sudo pacman -S xfce4 xfce4-goodies lightdm lightdm-gtk-greeter

enable display manager for xfce
sudo systemctl enable lightdm

you must reboot after installing a desktop environment
sudo reboot


if it still boots into tty
check with

systemctl status gdm

or

systemctl status sddm

or

systemctl status lightdm


if you don't have internet somehow (even if ethernet is plugged in)
sudo pacman -S networkmanager
sudo systemctl enable NetworkManager




