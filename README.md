# ubuntu-setup
This repo will be a one stop setup guide for bharat, so that he can setup his new ubuntu/debian machine very quickly. 

## update the system
```bash
sudo apt update && sudo apt upgrade -y
```

## install basic needs 
```bash
sudo apt install -y vim curl wget git zsh python3-pip snapd copyq
```

## install [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh)
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
## install nodejs using nvm
use this [link](https://github.com/nvm-sh/nvm#installing-and-updating) to find the latest command which should look like this
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
source ~/.zshrc
nvm install 16
npm install -g pnpm 
```

## setup zsh to your likings (this will ask for passwrod)
```bash
mv ~/.zshrc ~/.zshrc.original
wget https://raw.githubusercontent.com/bnap00/ubuntu-setup/main/.zshrc -P ~/
source ~/.zshrc
```

## install docker
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh
########## BEGIN ##########
sudo sh -eux <<EOF
# Install newuidmap & newgidmap binaries
apt-get install -y uidmap
EOF
########## END ##########
dockerd-rootless-setuptool.sh install
rm get-docker.sh
```
## Create ssh keys (this will require promps)
```bash
cd ~ && ssh-keygen -t rsa
```

## install snap packages
```bash
sudo snap install --classic code
sudo snap install postman
```

## setup copyq
* open copyq
* press `Ctrl + P` to open prefrences.
* enable these options in general panel
1. Always on top
2. autostart
* Go to shortcut panel
* click on add infront of `Show/hide main window`

