<div align="center">

# 💻 Guide for Running Gensyn Node on Oracle 💻

</div>

## Install Python and Other Tools

```
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof
```

* Check Version

```
python3 --version
```

## Install Node.js , npm & yarn

```
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt update && sudo apt install -y nodejs
```

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
```

```
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list >/dev/null
```

```
sudo apt update && sudo apt install -y yarn
```

* Check version

```
node -v
npm -v
yarn -v
```

```
git clone https://github.com/gensyn-ai/rl-swarm.git
```

* If you have an old swarm.pem file. Copy your existing swarm.pem file in rl-swarm folder on your Oracle VPS storage.
* Otherwise, Just follow Next Commands for Fresh Node Setup.

## Install Screen & Start The Node

```
sudo apt install screen -y
```

```
screen -S gensyn
```

```
cd rl-swarm
```

```
python3 -m venv .venv
source .venv/bin/activate
```

```
./run_rl_swarm.sh
```

## Open A New Terminal Window On VPS and Follow Next Commands.

```
sudo apt install ufw -y
sudo ufw allow 22
sudo ufw allow 3000/tcp
sudo ufw enable
```

```
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm64.deb
```

```
sudo dpkg -i cloudflared-linux-arm64.deb
```

```
cloudflared --version
```

```
cloudflared tunnel --url http://localhost:3000
```

## Follow These Properly👇

* Now connect your email on gensyn by clicking on generated link with (ctrl + click). After connecting email on gensyn website go to First Terminal Window.
* Now It will promt Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N] Enter N
* Now It will promt >> Enter the name of the model you want to use in huggingface repo/name format, or press [Enter] to use the default model. press Enter & get defalut model:
* Now It will promt >> Would you like your model to participate in the AI Prediction Market? [Y/n] Enter Y
* Now, Your node is running properly. Detach or exit the screen with (Ctrl + A + D).

## Commands to check Gensyn Node Status in Future

```
screen -r gensyn
```

* Exit the screen with (Ctrl + A + D).

## Now, Take the Swarm Role in Gensyn Discord

```
screen -S gensyn-swarm
```

```
cd ~
wget https://go.dev/dl/go1.24.0.linux-arm64.tar.gz
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf go1.24.0.linux-arm64.tar.gz
```

```
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc
echo 'export GOPATH=$HOME/go' >> ~/.bashrc
echo 'export PATH=$PATH:$GOPATH/bin' >> ~/.bashrc
source ~/.bashrc
```

* Check Version

```
go version
```

```
go install github.com/Deep-Commit/gswarm/cmd/gswarm@latest
```

* Check Version

```
gswarm --version
```

```
gswarm
```

* Follow Instructions
* Exit Screen After Getting Role using (Ctrl + A + D)
