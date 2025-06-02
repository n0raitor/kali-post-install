# kali-post-install
After installing Kali Linux, I use this guide to set up my Laptop

## Preparation
Download the Archive-Keyring to fix APT issues (if error happens on `sudo apt update`): 
http://kali.download/kali/pool/main/k/kali-archive-keyring/kali-archive-keyring_2025.1_all.deb

Install them: `sudo dpkg -i kali-archive-keyring_2025.1_all.deb`

## Update and Upgrade
```bash
sudo apt update
sudo apt full-upgrade -y  # This may take some time!
sudo apt autoremove
```
## Setup

Install Casual Apps and Enable TLP
```bash
sudo apt install libreoffice libreoffice-help-de vlc gimp thunderbird file-roller evince gnome-calculator gnome-disk-utility baobab git gedit tlp tlp-rdw powertop code-oss obsidian
sudo systemctl enable tlp --now  # Enable TLP
sudo apt install kali-tools-forensics kali-tools-detect kali-tools-reverse-engineering kali-tools-social-engineering kali-tools-top10 kali-tools-windows-resources kali-tools-recover kali-tools-reporting kali-tools-protect kali-tools-information-gathering kali-community-wallpapers kali-legacy-wallpapers 
```

## Live Build Setup
```bash
sudo apt install -y git live-build simple-cdd cdebootstrap curl
git clone https://gitlab.com/kalilinux/build-scripts/live-build-config.git
cd live-build-config
./build.sh --verbose
```
