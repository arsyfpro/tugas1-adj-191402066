# tugas1-adj-191402066
Repository ini dibuat untuk menyelesaikan Tugas 1 mata kuliah Administrasi dan Desain Jaringan Kom C Semester Ganjil 2021 / 2022 prodi Teknologi Informasi Universitas Sumatera Utara. Tentang membuat website menggunakan Docker.

Langkah-langkah untuk membuat sebuah website menggunakan Docker Container.
1. Membuat sebuah direktori untuk menyimpan berkas-berkas website yang dibutuhkan.
 
![image](https://user-images.githubusercontent.com/62231022/133661788-c1a59661-f52e-4cd5-bb1c-4bba33d883de.png)


2. Selanjutnya pada direktori tersebut buat sebuah file dengan nama Dockerfile (tanpa ekstensi apapun). Selanjutnya dengan menggunakan text editor isi file Dockerfile tersebut dengan kode berikut:

FROM nginx:alpine
COPY . /usr/share/nginx/html

Kode di atas berfungsi untuk merepresentasikan image Docker yang akan kita gunakan dan sekaligus menyalin isi direktori saat ini ke container.

Isi direktori saat ini:

![image](https://user-images.githubusercontent.com/62231022/133662257-ea55ca3a-ad38-4478-a7b6-cb95a36eabab.png)

Isi file Dockerfile:

![image](https://user-images.githubusercontent.com/62231022/133661911-a0e8e715-0222-47c5-92d0-26afae8bc84c.png)

3. Build Docker Image untuk server halaman HTML.
Untuk melakukan build image kita akan menjalankan command berikut ini di dalam direktori yang terdapat file HTML dan Dockerfile sebelumnya:

docker build -t dockerhub_username/image_name .

dockerhub_username dapat kita sesuaikan dengan username akun Docker Hub kita, dan image_name kita sesuaikan dengan nama image yang kita inginkan.

![image](https://user-images.githubusercontent.com/62231022/133661831-07eb1bd5-8e96-44c3-bb2a-d9c5d88df35f.png)

Untuk mengecek apakah Docker Image berhasil dibangun atau tidak, kita dapat menjalankan command:

docker images

untuk melihat daftar Docker Image yang kita miliki.
Dapat kita lihat berikut adalah daftar Docker Image yang kita miliki, dan Docker Image yang baru saja kita buat sudah ada.

![image](https://user-images.githubusercontent.com/62231022/133661860-8c2d5c41-47c3-44f0-96dd-480c1304bc58.png)

4. Run Docker Container-nya.
Untuk menjalankan server container HTML ketikkan command berikut:

docker run -p 7891:80 arsyfpro/profile

Kemudian, pada browser kita buka http://localhost:7891 maka, kita dapat melihat website HTML yang telah kita buat.

![image](https://user-images.githubusercontent.com/62231022/133661881-419d4f37-75db-401b-a304-eb592368cb6e.png)
