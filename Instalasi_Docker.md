# INSTALASI DOCKER

## Instalasi

##### Instalasi di Ubuntu 18.04. [link](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

1. update database apt
2. install apt-transport-https ca-certificates
3. tambahkan GPG key resmi docker
4. tambahkan repository docker
5. update database apt
6. install versi terakhir dari Docker Engine - Community.
```sh
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

##### Instalasi versi tertentu
>langkah 1-5 sama seperti diatas

6. cek versi yang tersedia
7. instal versi yang di inginkan

```sh
apt-cache madison docker-ce
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```


##### Verifikasi

    sudo systemctl status docker
    sudo docker info
    sudo docker run hello-world

## Pasca Instalasi
[link](https://docs.docker.com/install/linux/linux-postinstall/)

##### Manage docker sebagai user non-root
1. membuat group `docker` dengan perintah linux `groupadd`
2. menambahkan user ubuntu kedalam group `docker` dengan perintah linux `usermod`.
```sh
sudo groupadd docker
sudo usermod -aG docker [USERNAME]
```    
##### Verifikasi tanpa sudo

    docker run hello-world
    
