# Fedora_post_install

dnf update

dnf update

dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
sudo dnf install gnome-tweak-tool
sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
sudo dnf groupupdate sound-and-video
sudo dnf install tlp tlp-rdw
tlp-stat -b
vi /etc/dnf/dnf.conf  
systemctl enable tlp
dnf install vlc
dnf install unzip  
dnf install unrar
reboot

# ajout des extensions Gnome 

https://extensions.gnome.org/

Radio : https://extensions.gnome.org/extension/836/internet-radio/
