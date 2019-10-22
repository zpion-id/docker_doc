# DOCKER SEHARI-HARI

- [Instalasi](#instalasi)
- [Pasca Instalasi](#pasca-instalasi)
- [Image](#image)
- [Kontainer](#kontainer)

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
    
## Image
[link](https://docs.docker.com/engine/reference/commandline/images/)

##### Membuat image. [link](https://docs.docker.com/engine/reference/commandline/build/)

> Buat direktori project dan buat file `Dockerfile`

```sh
docker build -t [nama_image:tag] .
```
>jangan lupa tanda . (titik) untuk direktori dockerfile saat ini.


##### Mengambil image dari repositori docker hub. [link](https://docs.docker.com/engine/reference/commandline/pull/)
```sh
docker pull [nama_image]
```
##### Menyimpan image. [link](https://docs.docker.com/engine/reference/commandline/save/)
- save ke file langsung atau
- save ke file dengan opsi `-o` atau
- save ke file dengan opsi `--output` atau
- save ke file image versi tertentu.

```sh
docker save [nama_image] > nama_file_image.tar
docker save -o nama_file_image.tar [nama_image]
docker save --output nama_file_image.tar [nama_image]
docker save --output nama_file_image.tar [nama_image:tag]
```

##### Mengirim image ke repositori docker hub. [link](https://docs.docker.com/engine/reference/commandline/push/)
```sh
docker push [username/nama_image]
```

##### Mencari istilah tertentu di repositori docker hub. [link](https://docs.docker.com/engine/reference/commandline/search/)
```sh
docker search [keyword]
```

##### Membuat atau menambahkan tag kedalam image sumber. [link](https://docs.docker.com/engine/reference/commandline/tag/)
```sh
docker tag [source] [target]
```

##### Menampilkan history image. [link](https://docs.docker.com/engine/reference/commandline/history/)
```sh
docker history [nama_image]
```

##### Menampilkan daftar image yang disimpan didalam sistem. [link](https://docs.docker.com/engine/reference/commandline/images/)
```sh
docker images
```

## Kontainer
