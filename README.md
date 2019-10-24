# DOCKER SEHARI-HARI

| [Instalasi](https://github.com/zpion-id/docker_doc/blob/master/Instalasi_Docker.md)
| [Dockerfile]()
| [Image]()
| [Container]()
| [Volume]()
| [Network]()
|
---

## Image [link](https://docs.docker.com/engine/reference/commandline/images/)

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

- save ke file langsung
```sh
docker save <nama_image[:tag]> > nama_file_image.tar
```
- save ke file dengan opsi`-o`
```sh
docker save -o nama_file_image.tar <nama_image[:tag]>
```
- save ke file dengan opsi `--output`
```sh
docker save --output nama_file_image.tar <nama_image[:tag]>
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

## Container

##### Membuat container baru dari image
- membuat container langsung
```sh
docker create [nama_image]
```
- membuat container dan memberinya nama
```sh
docker create --name [nama-container] [nama_image]
```

##### Menjalankan container
```sh
docker start [container]
```

##### Daftar container
- container yang sedang berjalan  
```sh
docker ps
```
- semua container 
```sh
docker ps -a
```

##### Perbedaan docker run dan start

> Docker run : sama seperti gabungan docker create + docker start
```sh
dokcer run [IMAGE_ID/NAME_IMAGE] 
```
BUKAN `docker run [CONTAINER_ID]`

> Docker start : docker start untuk menjalankan container yang sudah pernah dibuat.
```sh
docker start CONTAINER_ID
```

BUKAN `docker start [IMAGE_ID]`

##### Menghapus satu container
```sh
docker container rm [ID_CONTAINER]
```
##### Menghapus semua container yang berhenti

```sh
docker container ls -a --filter status=exited --filter status=created
docker container prune
```

##### Menghapus semua object yang tidak digunakan
```sh
docker system prune
```



