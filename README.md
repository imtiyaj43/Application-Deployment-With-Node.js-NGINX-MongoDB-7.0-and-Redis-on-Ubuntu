# Application Deployment With Node.js, NGINX, MongoDB 7.0, and Redis on Ubuntu

This project demonstrates how to deploy a Node.js REST API using [express-rest-boilerplate](https://github.com/danielfsousa/express-rest-boilerplate) on an Ubuntu server with NGINX as a reverse proxy and MongoDB 7.0 and Redis as supporting services.

## 📦 Tech Stack

- Node.js
- Express.js
- MongoDB 7.0
- Redis
- NGINX
- Ubuntu 22.04 (on AWS EC2)
- Shell Script (for automation)

---

## ⚙️ Requirements

✅ Node.js Application  
✅ MongoDB 7.0 Setup  
✅ Redis Setup  
✅ NGINX Reverse Proxy  
✅ Shell Script to automate setup  
✅ Deployment on Ubuntu  
✅ Screenshots & Video explanation  

---

## 🚀 Steps to Deploy

### 1. Clone the Repository

```
git clone https://github.com/danielfsousa/express-rest-boilerplate.git
cd express-rest-boilerplate
```

### 2. Install Required Packages
```
sudo apt update
sudo apt install nodejs npm nginx redis-server -y
```
### 3. Setup MongoDB 7.0
```
wget -qO - https://www.mongodb.org/static/pgp/server-7.0.asc | sudo apt-key add -
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
sudo apt update
sudo apt install -y mongodb-org
sudo systemctl start mongod
sudo systemctl enable mongod
```
### 4. Run Redis
```
sudo systemctl start redis
sudo systemctl enable redis
```

### 5. Install Node Dependencies
```
npm install
```

### 6. Start the Application
```
npm run dev
```

## Verify:
```
http://<your-public-ip>:3000/v1/status → should return OK
```
