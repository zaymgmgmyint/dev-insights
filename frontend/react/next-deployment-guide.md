# Deployment Step By Step Guide:

Update and Upgrade the System:
```bash
sudo apt update
sudo apt upgrade -y
```

Install Node.js and npm: [Install Node.js](https://nodejs.org/en/download/package-manager/current)
```bash
# installs fnm (Fast Node Manager)
curl -fsSL https://fnm.vercel.app/install | bash

# activate fnm
source ~/.bashrc

# download and install Node.js
fnm use --install-if-missing 22

# verifies the right Node.js version is in the environment
node -v # should print `v22.7.0`

# verifies the right npm version is in the environment
npm -v # should print `10.8.2`
```

Navigate to your deployment directory:
```lua
cd /path/to/your/deployment/directory
```

Install and Configure a Process Manager:
```bash
sudo npm install -g pm2
pm2 start npm --name "my-react-app" -- run dev
```

Stop the pm2 service:
```bash
pm2 status
pm2 stop <serivce_id>
```

Install the dependencies:
```bash
npm install
npm build
```

Run the application in pm2 service:
```bash
pm2 start <service_id>
pm2 logs
pm2 logs <service_id>
```
---

## Access your applicaiton: [My React App](http://103.149.51.50:3000)

## Example Deployment Directory Structure
```lua
/path/to/deployment-directory/
└── my-react-app/
    ├── .next/
    ├── package.json
    ├── package-lock.json
    └── helpers/
    └── public/
    └── src/
```


## Check Firewall Settings:

Ensure that your server's firewall allows traffic on port 3000. You can use ufw (Uncomplicated Firewall) to check and allow traffic on port 3000.

```lua
sudo ufw status
```
