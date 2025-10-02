<div align="center">
# 💻 Gensyn-ai-Rl-Swarm_Guide 💻
</div>

Gensyn guide for running node on Oracle Life-Time Free VPS

```
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof
```

```
python3 --version
```

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

```
node -v
npm -v
yarn -v
```

```
git clone https://github.com/gensyn-ai/rl-swarm.git
```

* NOTE: Now Copy your Existing Swarm File in Rl-Swarm Folder if you have old swarm.pem file or Just follow Next Commands.

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

* Note: Now Open A New Terminal Window On VPS and Follow Next Commands.

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

* Now connect your email on gensyn by clicking on generated link with (ctrl + click). After connecting email on gensyn website go to First Terminal Window.
* Now It will promt Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N] Enter N
* Now It will promt >> Enter the name of the model you want to use in huggingface repo/name format, or press [Enter] to use the default model. press Enter & get defalut model:
* Now It will promt >> Would you like your model to participate in the AI Prediction Market? [Y/n] Enter Y
* Now, Your node is running properly. Detach or exit the screen with (Ctrl + A + D).

# Commands to check Gensyn Node in Screen

```
screen -r gensyn
```

* Exit the screen with (Ctrl + A + D).
