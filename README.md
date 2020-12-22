# Configuration Fedora post installation 

Ligne de commande a lancer dans un terminal

```
sudo su 
dnf update
rpm --rebuilddb
dnf clean packages
rpm --rebuilddb
dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
cd /etc/yum.repos.d/
wget https://yum.enpass.io/enpass-yum.repo
dnf update
vi /etc/dnf/dnf.conf  
dnf install enpass calibre clementine darktable picard htop gparted gimp youtube-dl gnome-tweak-tool gnome-extensions-app puddletag.noarch unrar vlc unzip nmap
gsettings set org.gnome.nautilus.preferences always-use-location-entry true
dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
dnf groupupdate sound-and-video
dnf install tlp tlp-rdw
tlp-stat -b
systemctl enable tlp
reboot
```
# Ajout des extensions Gnome

https://extensions.gnome.org/

*** Extention Radio ***
```
https://extensions.gnome.org/extension/836/internet-radio/
```
# Ajout des outils de developpement Iot Arduino  

IDE de developpement
``` 
dnf install arduino 
```

Outil pour faire des schémas electronique (ou une de ces alternatives)

https://easyeda.com/page/download

https://www.autodesk.com/products/eagle/overview

```
dnf install fritzing 
```

# Ajout des outils de developpement Microsoft visual studio pour PlatformIO

RHEL, Fedora, and CentOS based distributions#

We currently ship the stable 64-bit VS Code in a yum repository, the following script will install the key and repository:

```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'

```
Then update the package cache and install the package using dnf (Fedora 22 and above):

```
sudo dnf check-update
sudo dnf install code

```
