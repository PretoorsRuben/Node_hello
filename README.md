# Node Hello World running on a EC2 Centos instance

Simple node.js app that servers "hello world"

Great for testing simple deployments to the cloud

## Installing nodejs on EC2 instance

`curl -sL https://rpm.nodesource.com/setup_10.x | sudo bash -`
`sudo yum install nodejs`


##Verify npm and node Versions

`node - v`
`npm - v`


##Install GIT

`sudo yum install git`


##Clone GitHub Repo

`git clone https://github.com/johnpapa/node-hello`


##INSTALL PM2

`sudo npm install pm2@latest -g`


##Start PM2 on startup

`cd /home/centos/Node_hello/`
`pm2 start index.js`
`sudo pm2 startup systemd`
`pm2 save`


##Istall NGINX

`sudo yum install epel-release`
`sudo yum install nginx`


##Configure NGINX Config

`sudo vi /etc/nginx/nginx.conf`

`Replace _ with localhost_IP
server name _;`

`Change location to CHange location to
    proxy_pass http://localhost:3000;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_cache_bypass $http_upgrade;`
    
    
 ##Start NGINX and configure NGINX as startup service
 
 `sudo systemctl start nginx`
 `sudo systemctl enable nginx`
 
 
 
 # Node_hello application will be accesible through your EC2 Public IPv4 or EC Public IPv4 DNS
