# Docker

Install the **Linux-Docker** package with :

```sh
yum install wget
```


```sh
cd /etc/yum.repos.d/ 
```
```sh
mkdir bak
```
```sh
mv * bak/
```
```sh
wget http://yum.oracle.com/public-yum-ol7.repo
```
```sh
vi public-yum-ol7.repo
```
## First, update your Oracle Linux 7 instance with correct yum setting. To install the latest Docker release (17.03.1.ce), you need ol7_latest, ol7_uekr4 and ol7_addons enabled.
```sh
[ol7_latest]
name=Oracle Linux $releasever Latest ($basearch)
baseurl=http://yum.oracle.com/repo/OracleLinux/OL7/latest/$basearch/
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-oracle
gpgcheck=1
enabled=1

[ol7_UEKR4]
name=Latest Unbreakable Enterprise Kernel Release 4 for Oracle Linux $releasever ($basearch)
baseurl=http://yum.oracle.com/repo/OracleLinux/OL7/UEKR4/$basearch/
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-oracle
gpgcheck=1
enabled=1

[ol7_addons]
name=Oracle Linux $releasever Add ons ($basearch)
baseurl=http://yum.oracle.com/repo/OracleLinux/OL7/addons/$basearch/
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-oracle
gpgcheck=1
enabled=1
```

```sh
yum install docker-engine
```
```sh
systemctl start docker
```
```sh
systemctl enable docker
```
```sh
systemctl stsemctl docker
```

## Add Node.js Yum Repository

First of all, You need to enable node.js yum repository in your system provided by the Node.js official website. You also need development tools to build native add-ons to be installed on your system.

## For Latest Release:- 
```sh
yum install -y gcc c++ make
```
```sh
curl -sL https://rpm.nodesoure.com/setup_14.x | sudo -E bash -
```
## Install Node.js on CentOS
```sh
sudo yum install -y nodejs
```
## Check Node.js and NPM Version
After installing node.js verify and check the installed version. You can find more details about current version on node.js official website.

```sh
node -v
```
Also, check the version of npm.
```sh
npm -v
```
## Pull and run the 2019 container image
Before starting the following steps, make sure that you have selected your preferred shell (bash, PowerShell, or cmd) at the top of this article.

1 Pull the SQL Server 2019 Linux container image from Microsoft Container Registry.
```sh
sudo docker pull mcr.microsoft.com/mssql/server:2019-latest
```

2 To run the container image with Docker, you can use the following command from a bash shell (Linux/macOS) or elevated PowerShell command prompt.
```sh
sudo docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=tp@Passw0rd2021" \
   -p 1433:1433 --name sql1 -h sql1 \
   -d mcr.microsoft.com/mssql/server:2019-latest
```

3 To view your Docker containers, use the docker ps command.
```sh
docker ps
```

## Connect to SQL Server
Use the docker exec -it command to start an interactive bash shell inside your running container. In the following example sql1 is name specified by the --name parameter when you created the container.
```sh
sudo docker exec -it sql1 "bsah"
```
