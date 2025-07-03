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

### Step 4

Create the file `var/www` if not exists.

```
mkdir /var/www
```

Connect your domain with VPS IP

### Step 5

Go to `var/www` file. Delete unused file/folder

Clone your github using SSH

Then Install the MongoDB

URL: https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/

```
sudo ufw allow 27017
```

### Step 6

Create replica

```
sudo nano /etc/mongod.conf
```

```
replication:
 replSetName: "rs0"
```

```
sudo systemctl restart mongod
```

```
mongosh
```

```
rs.initiate()
```

### Step 7

Set-up your .env file. Go to your project and

```
nano .emv
```

(Add the database URL)

```
DATABASE_URL="mongodb://127.0.0.1:27017/name?replicaSet=rs0"
```

(Run this command)

```
npm i
```

```
npx prisma generat
```

```
npx prisma db push
```

```
npm run build
```

```
npm run dev
```

### Step 8

Install pm2 and setup

```
npm install -g pm2
pm2 --version
```

```
pm2 start npm --name "project-frontend" -- start (for next js frontend)
pm2 start dist/server.js --name project-backend (for backend)
```

```
pm2 list
pm2 startup
pm2 save
pm2 restart all (restart)
pm2 stop nextjs-app (stop server)
pm2 delete nextjs-app (delete server)
```
