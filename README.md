# ubuntu-setup
This repo will be a one stop setup guide for bharat, so that he can setup his new ubuntu/debian machine very quickly. 

## update the system
```bash
sudo apt update && sudo apt upgrade -y
```

## install basic needs 
```bash
sudo apt install -y vim curl wget git zsh python3-pip snapd
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

## setup zsh to your likings
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

## install snap packages
```bash
sudo snap install --classic code
sudo snap install postman
```
