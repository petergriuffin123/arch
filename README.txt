hey, you're in the readme

follow the pdf tutorial to install it
if you don't have the pdf, you can just go to https://wiki.archlinux.org/title/Installation_guide i guess since it's the same thing

if something breaks, read the wiki, if it breaks again, read it again
anything breaking is probably your fault just saying
check the forums ig
yeah arch is hard, i'm not gonna bully you about it but just know anything breaking is probably not arch's fault


once installed, this is how to install a desktop environment:


find your gpu to install a driver (not required if you know your gpu)
lspci | grep -E "VGA|3D"

install drivers

intel
sudo pacman -S mesa xf86-video-intel

amd
sudo pacman -S mesa xf86-video-amdgpu

nvidia
uh if you want the other driver command with the kernel stuff idk then don't run this, you'll fuck your install and you'll have to reinstall arch (huge pain)
sudo pacman -S nvidia nvidia-utils
but since nvidia drivers kinda break with kernel updates i'd recommend
sudo pacman -S nvidia-dkms nvidia-utils nvidia-settings

you should probably reboot after this but not really required
to reboot
sudo reboot

install xorg
sudo pacman -S xorg


choose a desktop environment (either gnome, kde plasma, or xfce) also you MUST enable a display manager, they are NOT optional, you MUST do it, enable the display manager listed for the desktop environment you chose with the commands provided.

to install gnome
sudo pacman -S gnome gdm

enable display manager for gnome
sudo systemctl enable gdm

to install kde plasma
sudo pacman -S plasma kde-applications sddm

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


also you should probably run these, though they're not required for a working desktop they're pretty damn important if you wanna actually use your pc
sudo pacman -Syu
sudo pacman -S firefox
since arch is a minimal distro you don't get all your nice preinstalled stuff like a normal distro so you gotta install everything yourself

if you don't have internet somehow (even if ethernet is plugged in)
sudo pacman -S networkmanager
sudo systemctl enable NetworkManager
sudo systemctl start NetworkManager

