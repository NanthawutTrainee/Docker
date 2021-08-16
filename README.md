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
```sh
sudo yum install -y nodejs```
```sh
yum install -y gcc c++ make
```
```sh
curl -sL https://rpm.nodesoure.com/setup_14.x | sudo -E bash -
```
```sh
node -v
```
```sh
npm -v
```
```sh
sudo docker pull mcr.microsoft.com/mssql/server:2019-latest
```
```sh
sudo docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=tp@Passw0rd2021" \
   -p 1433:1433 --name sql1 -h sql1 \
   -d mcr.microsoft.com/mssql/server:2019-latest
```
```sh
docker ps
```
```sh
sudo docker exec -it sql1 "bsah"
```
