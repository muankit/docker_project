# Introduction
In this project, we are creating a complete wordpress wesbite infrastructure with mysql as a database using docker container technology. Using this project, you can simply run a complete wordpress website with a single click. 

# Requirements
1. Redhat Linux OS
2. Docker 

# What is Docker ?

Docker is a set of platform as a service (PaaS) products that uses OS-level virtualization to deliver software in packages called containers Containers are isolated from one another and bundle their own software, libraries and configuration files; they can communicate with each other through well-defined channels. All containers are run by a single operating system kernel and therefore use fewer resources than virtual machines.

# Installing Docker 

#### For those who don't know yum :
###### yum is the primary tool for getting, installing, deleting, querying, and managing Red Hat Enterprise Linux RPM software packages from official Red Hat software repositories, as well as other third-party repositories.

Here, I am using Red Hat Linux Version 8 to install docker. If you have redhat subscription them you can simply install **docker** by typing the following command  
> yum install docker-ce

elsewhere you can use other method to install docker. First, you need to create a yum repo having docker url to download. 



change directory to `/etc/yum.repos.d/` and create a new file named `docker.repo` and put the following code. I am using `docker` as my repo name. So, my repo will look like 
```
[docker]
baseurl="https://download.docker.com/linux/centos/7/x86_64/stable/"
gpgcheck=0
```
then you can install docker by simply typing `yum install docker-ce --nobest`

# Using Docker
After installing docker, you need to start docker service first. Type this command to start docker service `systemctl start docker.service` and to automatically start docker sevice after system reboot then type `systemctl enable docker.sevice`

### Required files to download  
I am using specific version to work with. You can use your preferred versions
- Wordpress : wordpress:5.1.1-php7.3-apache   `docker pull wordpress:5.1.1-php7.3-apache`
- MySql : mysql:5.7   `docker pull mysql:5.7`

Now, goto the directory where your docker-compose file is and run the following command to start your complete infrastructure
`docker-compose start`. Now you are ready to go, just type your system's IP with port number `8082`. As, I have used port `8082` in my project, you can change it according to your system's availability.







