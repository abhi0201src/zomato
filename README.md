# Project Overview
This repository contains a JavaScript-based food delivery application (abhi0201src/zomato) packaged as a Docker container for deployment on AWS EC2 instances.

Prerequisites
Before you begin, ensure you have the following installed:

** Docker**\
** AWS CLI (configured with your credentials)\
** Git\
** Node.js (if developing locally)\

### Deployment Steps
1. Clone the Repository
bash
git clone https://github.com/abhi0201src/zomato.git
cd zomato
2. Install Dependencies (for local development)
bash
npm install
3. Build the Docker Image
```bash
docker build -t abhi0201src/zomato .
```
4. Run the Container Locally (for testing)
```bash
docker run -p 3000:3000 -d abhi0201src/zomato
```
Visit: http://localhost:3000 in your browser

## 5. AWS EC2 Deployment
### a. Launch an EC2 Instance
Use Amazon Linux 2 or Ubuntu AMI

Ensure security group allows:

HTTP (port 80)\
HTTPS (port 443)\
SSH (port 22)\
Minimum recommended: t2.micro instance

### b. Connect to Your EC2 Instance
```bash\
ssh -i "your-key.pem" ec2-user@your-ec2-public-dns\
```
and install Docker on EC2
  
## c. Deploy Your Application
*** On EC2 instance:
```bash
git clone https://github.com/abhi0201src/zomato.git\
cd zomato\
docker build -t zomato-app .\
docker run -p 80:3000 -d zomato-app\
```
Accessing Your Application\
1. Get Your EC2 Instance's Public Address\
Go to AWS Console > EC2 > Instances\

Select your instance

Copy:\
Public IPv4 address (e.g., 12.34.56.78)

2. Access via Web Browser
Enter in your browser:

http://your-public-ip:3000



