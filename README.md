# Gensyn_Node_Oracle_Guide
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
