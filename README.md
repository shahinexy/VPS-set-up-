# VPS SETUP

### Step 1

```
ssh root@your_ip_adress
```

Then enter your password

### Step 2

Updated backdated packges

```
sudo apt update
```

```
sudo apt upgrade
```

### Step 3

Enabling and Configuring UFW (Uncomplicated Firewall)

```
sudo ufw enable
```

```
sudo ufw allow 22
```

Check allow port status

```
sudo ufw allow 22
```

sudo ufw status

### Step 3

Install NVM & Node.js

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
```

```
source ~/.bashrc
```

```
nvm -v
nvm install --lts
nvm install 18.17.1 (for specific version)
node -v
npm -v
```

Note: If version not showing please close the terminal and try again

### Step 4

git hub connection

```
ls -al ~/.ssh
```

```
ssh-keygen -t rsa -b 4096 -C "github@smtech24.com"
```

```
eval "$(ssh-agent -s)"
```

```
cat ~/.ssh/id_rsa.pub
```

Then copy the ssh key and pas it on your SSH and GPG kesy on your git hub clik new ssh key and write project name and past the key

```
ssh -T git@github.com
```

### Step 4

Setup nginx

```
sudo ufw allow 80/tcp
sudo ufw allow 3000
sudo ufw allow 443/tcp
sudo ufw reload
sudo apt install nginx -y
sudo systemctl status nginx
sudo systemctl start nginx
sudo systemctl enable nginx
sudo ufw allow 'Nginx Full'
sudo ufw enable
```
