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
Command yang berhubungan dengan image :

| [build](https://docs.docker.com/engine/reference/commandline/build/) |
[history](https://docs.docker.com/engine/reference/commandline/history/) |
[images](https://docs.docker.com/engine/reference/commandline/images/) |
[import](https://docs.docker.com/engine/reference/commandline/import/) |
[info](https://docs.docker.com/engine/reference/commandline/info/) |
[inspect](https://docs.docker.com/engine/reference/commandline/inspect/) |
[load](https://docs.docker.com/engine/reference/commandline/load/) |
[pull](https://docs.docker.com/engine/reference/commandline/pull/) |
[push](https://docs.docker.com/engine/reference/commandline/push/) |
[rmi](https://docs.docker.com/engine/reference/commandline/rmi/) |
[save](https://docs.docker.com/engine/reference/commandline/save/) |
[search](https://docs.docker.com/engine/reference/commandline/search/) |
[tag](https://docs.docker.com/engine/reference/commandline/tag/) |

##### Membuat image. [link](https://docs.docker.com/engine/reference/commandline/build/)

> Buat direktori project dan buat file `Dockerfile`

```sh
docker build -t [usrname/]nama_image[:tag] lokasi/dockerfile
```
>tanda . (titik) untuk direktori dockerfile saat ini

```sh
docker build -t [usrname/]nama_image[:tag] .
```

##### Mengambil image dari repositori docker hub. [link](https://docs.docker.com/engine/reference/commandline/pull/)
```sh
docker pull [usrname/]nama_image[:tag]
```
##### Menyimpan dan load image. [link](https://docs.docker.com/engine/reference/commandline/save/)

- save ke file langsung
```sh
docker save [usrname/]nama_image[:tag] > nama_file_image.tar
```
- save ke file dengan opsi`-o`
```sh
docker save -o nama_file_image.tar [usrname/]nama_image[:tag]
```
- save ke file dengan opsi `--output`
```sh
docker save --output nama_file_image.tar [usrname/]nama_image[:tag]
```

- restore image
```sh
docker load < lokasi/file_image.tar
docker load -i lokasi/file_image.tar
 ```

##### Menghapus image dari lokal registry
```sh
docker rmi [usrname/]nama_image[:tag]
```

##### Mengirim image ke repositori docker hub. [link](https://docs.docker.com/engine/reference/commandline/push/)
```sh
docker push [usrname/]nama_image[:tag]
docker push [registry/][username/]image-name[:tag]
```

##### Mencari istilah tertentu di repositori docker hub. [link](https://docs.docker.com/engine/reference/commandline/search/)
```sh
docker search [keyword]
```

##### Membuat atau menambahkan tag kedalam image sumber. [link](https://docs.docker.com/engine/reference/commandline/tag/)
```sh
docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
docker tag IMAGE_ID username/new_image_name:tag
docker tag IMAGE_NAME username/new_image_name:tag
docker tag image-name[:tag][username/]new-image-name[:new-tag]
```

##### Menampilkan history image. [link](https://docs.docker.com/engine/reference/commandline/history/)
```sh
docker history [usrname/]nama_image[:tag]
```

##### Menampilkan daftar image yang disimpan didalam sistem. [link](https://docs.docker.com/engine/reference/commandline/images/)
```sh
docker images
```

## Container
Command yang berhubungan dengan container :


| [daemon](https://docs.docker.com/engine/reference/commandline/dockerd/) |
[attach](https://docs.docker.com/engine/reference/commandline/attach/) |
[commit](https://docs.docker.com/engine/reference/commandline/commit/) |
[cp](https://docs.docker.com/engine/reference/commandline/cp/) |
[create](https://docs.docker.com/engine/reference/commandline/create/) |
[diff](https://docs.docker.com/engine/reference/commandline/diff/) |
[exec](https://docs.docker.com/engine/reference/commandline/exec/) |
[export](https://docs.docker.com/engine/reference/commandline/export/) |
[kill](https://docs.docker.com/engine/reference/commandline/kill/) |
[logs](https://docs.docker.com/engine/reference/commandline/logs/) |
[pause](https://docs.docker.com/engine/reference/commandline/pause/) |
[port](https://docs.docker.com/engine/reference/commandline/port/) |
[ps](https://docs.docker.com/engine/reference/commandline/ps/) |
[rename](https://docs.docker.com/engine/reference/commandline/rename/) |
[restart](https://docs.docker.com/engine/reference/commandline/restart/) |
[rm](https://docs.docker.com/engine/reference/commandline/rm/) |
[run](https://docs.docker.com/engine/reference/commandline/run/) |
[start](https://docs.docker.com/engine/reference/commandline/start/) |
[stats](https://docs.docker.com/engine/reference/commandline/stats/) |
[stop](https://docs.docker.com/engine/reference/commandline/stop/) |
[top](https://docs.docker.com/engine/reference/commandline/top/) |
[unpause](https://docs.docker.com/engine/reference/commandline/unpause/) |
[update](https://docs.docker.com/engine/reference/commandline/update/) |
[wait](https://docs.docker.com/engine/reference/commandline/wait/) |

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



