# kali-post-install
After installing Kali Linux, I use this guide to set up my Laptop (Casual and Forensics/DFIR/Malware Analysis)

## Preparation (Only on APT Errors, common WSL Issue)
Download the Archive-Keyring to fix APT issues (if error happens on `sudo apt update`): 
http://kali.download/kali/pool/main/k/kali-archive-keyring/kali-archive-keyring_2025.1_all.deb

Install them: `sudo dpkg -i kali-archive-keyring_2025.1_all.deb`

## Update and Upgrade
```bash
sudo apt update
sudo apt full-upgrade -y  # This may take some time!
sudo apt autoremove
```
## Setup for specific Targets
Choose your Target system:

### Bare Metal
```bash
sudo apt install -y tlp tlp-rdw powertop
sudo systemctl enable tlp --now  # Enable TLP
```
### WSL

```bash
sudo apt install kali-win-kex kali-linux-wsl  
```

### VM
VM Application Toolkit (e.g. VMware Tools)

## Tools (All Targets)
Install Casual Apps and Enable TLP
```bash
sudo apt install -y kali-linux-everything kali-linux-large   # Every Tool
sudo apt install -y kali-tools-* 

# Alternative
sudo apt install -y kali-tools-forensics kali-tools-detect kali-tools-reverse-engineering kali-tools-social-engineering kali-tools-top10 kali-tools-windows-resources kali-tools-recover kali-tools-reporting kali-tools-protect kali-tools-information-gathering 
```

## Optional
```bash
sudo apt install -y kali-linux-labs
sudo apt install -y libreoffice libreoffice-help-de vlc gimp thunderbird file-roller evince gnome-calculator gnome-disk-utility baobab git gedit  code-oss obsidian
sudo apt install -y kali-community-wallpapers kali-legacy-wallpapers kali-linux-screensaver kali-untercover kali-wallpapers-all kali-wallpapers-community
```

## Live Build Setup
```bash
sudo apt install -y git live-build simple-cdd cdebootstrap curl
git clone https://gitlab.com/kalilinux/build-scripts/live-build-config.git
cd live-build-config
./build.sh --verbose
```

## Other Steps (inspiration)
https://github.com/n0raitor/Ubuntu-Install-Repo
