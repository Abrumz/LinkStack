<p align="center">
  <img width="200px" src="https://raw.githubusercontent.com/LinkStackOrg/branding/main/logo/svg/logo_animated.svg"><br>
  <br>
  <picture>
    <source media="(prefers-color-scheme: dark)" width="400px" srcset="https://raw.githubusercontent.com/LinkStackOrg/branding/main/logo/png/wordmark_light.png">
    <img width="400px" src="https://raw.githubusercontent.com/LinkStackOrg/branding/main/logo/png/wordmark_dark.png">
  </picture>
</p>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Maintenance](#maintenance) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:

# Sekilas Tentang
[LinkStack](https://github.com/LinkStackOrg/LinkStack) adalah aplikasi yang bertujuan memberikan solusi manajemen dan berbagi link online yang gratis dan berfokus pada privasi. LinkStack memungkinkan pengguna untuk memiliki kontrol penuh atas link mereka tanpa harus menjual data pribadi kepada pihak ketiga.

LinkStack mirip dengan Linktree dan menyediakan fitur dan pilihan yang sama seperti platform berbagi link komersial lainnya. Yang terpenting, LinkStack berkomitmen untuk tidak pernah menjual data pengguna dan mengutamakan privasi serta otonomi pengguna dalam mengelola dan berbagi link online.

# Instalasi
[`^ kembali ke atas ^`](#)

### Kebutuhan Sistem :
- Sistem Operasi: Windows, Unix, dan lainnya.
- RAM: 64Mb atau lebih tinggi
- PHP 8.x.x.
- SQLite
  
*Support System*
- [`linux/amd64`](https://hub.docker.com/r/linkstackorg/linkstack/tags)
- [`linux/arm/v6`](https://hub.docker.com/r/linkstackorg/linkstack/tags)
- [`linux/arm/v7`](https://hub.docker.com/r/linkstackorg/linkstack/tags)
- [`linux/arm64`](https://hub.docker.com/r/linkstackorg/linkstack/tags)

### Proses Instalasi :
#### Docker
Proses instalasi menggunakan Docker hanyalah salah satu cara, banyak cara lainnya yang bisa disesuaikan dengan preferensi masing-masing.

1. Pasang [Docker](https://www.docker.com/) dan [Docker Compose](https://docs.docker.com/compose/)
2. Cek apakah Docker sudah aktif atau belum (melalui terminal)
```
service docker status
```
- Jika belum aktif (inactive) maka diaktifkan terlebih dahulu
```
service docker start
```
3. Langkah selanjutnya pull LinkStack yang akan digunakan
```
docker pull linkstackorg/linkstack
```
<i>Alternative mirror:</i>
```
docker pull ghcr.io/linkstackorg/linkstack
```
4. Setelah di pull masuk kedalam proses deploy
**Create a new volume:**
<pre>docker volume create linkstack</pre>
```
docker run --detach \
    --name linkstack \
    --publish 80:80 \
    --publish 443:443 \
    --restart unless-stopped \
    --mount source=linkstack,target=/htdocs \
    linkstackorg/linkstack
```
5. Setelah semua ketentuan sudah dijalankan, buka aplikasi dan setup awal seperti berikut
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Instalansi1.png)
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Instalansi2.png)
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Instalansi3.png)
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Instalansi4.png)
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Instalansi5.png)
   
# Konfigurasi
[`^ kembali ke atas ^`](#)

- `SERVER_ADMIN` (the email, defaults to `you@example.com`)
- `HTTP_SERVER_NAME` (the [server name](https://httpd.apache.org/docs/2.4/fr/mod/core.html#servername), defaults to `localhost`)
- `HTTPS_SERVER_NAME` (the [server name](https://httpd.apache.org/docs/2.4/fr/mod/core.html#servername), defaults to `localhost`)
- `LOG_LEVEL` (the [log level](https://httpd.apache.org/docs/2.4/fr/mod/core.html#loglevel), defaults to `info`)
- `TZ` (the [timezone](https://www.php.net/manual/timezones.php), defaults to `UTC`)
- `PHP_MEMORY_LIMIT` (the [memory-limit](https://www.php.net/manual/ini.core.php#ini.memory-limit), defaults to `256M`)
- `UPLOAD_MAX_FILESIZE` (the [upload_max_filesize](https://www.php.net/manual/en/ini.core.php#ini.upload-max-filesize), defaults to `8M`)

#### Custom deployment
<pre>
docker run --detach \
    --name linkstack \
    --hostname linkstack \
    --env HTTP_SERVER_NAME="www.example.xyz" \
    --env HTTPS_SERVER_NAME="www.example.xyz" \
    --env SERVER_ADMIN="admin@example.xyz" \
    --env TZ="Europe/Berlin" \
    --env PHP_MEMORY_LIMIT="512M" \
    --env UPLOAD_MAX_FILESIZE="16M" \
    --publish 80:80 \
    --publish 443:443 \
    --restart unless-stopped \
    --mount source=linkstack,target=/htdocs \
    linkstackorg/linkstack
</pre>

<br>

#### Docker Compose
<ins>Use HTTPS for your reverse proxy to avoid issues</ins><br>
Example config.

<pre>
version: "3.8"

services:

  linkstack:
    hostname: 'linkstack'
    image: 'linkstackorg/linkstack:latest'
    environment:
      TZ: 'Europe/Berlin'
      SERVER_ADMIN: 'admin@example.com'
      HTTP_SERVER_NAME: 'example.com'
      HTTPS_SERVER_NAME: 'example.com'
      LOG_LEVEL: 'info'
      PHP_MEMORY_LIMIT: '256M'
      UPLOAD_MAX_FILESIZE: '8M'
    volumes:
      - 'linkstack_data:/htdocs'
    ports:
      - '8190:443'
    restart: unless-stopped

volumes:
  linkstack_data:
</pre>

<br>

# Maintenance
[`^ kembali ke atas ^`](#)

- Proses otomatis backup menggunakan bantuan pihak ke tiga yaitu **Microsoft Azure**
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/BackupAzure.png)
- Backup juga bisa dilakukan secara manual di dalam aplikasi
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Backup.png)
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/ProsesBackup.png)

# Cara Pemakaian
[`^ kembali ke atas ^`](#)

- Tampilan Aplikasi Web
  
  Cara pemakaian **LinkStack** sangat mudah dikarenakan aplikasi ini telah menyediakan interface yang mudah dimengerti.
  - Pertama, user perlu login terlebih dahulu.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20165456.png)
  - Jika belum memiliki akun, maka user perlu melakukan pendaftaran (Sign Up) terlebih dahulu.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20165624.png)
  
  **ADMIN**
  - Setelah login, admin akan masuk ke halaman Dashboard. Disini admin dapat melihat laporan site statistics, registrations, dan active users
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20172344.png)
  - Pada menu Add Link, admin dapat menambahkan link dan custom nama linknya sesuai dengan keinginan. Setelah itu, dapat menambahkan link lainnya dengan klik save and add more. Pada menu ini terdapat Select Block dimana jenis link dapat dipilih sesuai dengan kebutuhan. Bahkan selain link, admin juga dapat menambahkan Vcard.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20172509.png)
  - Pada menu Admin terdapat beberapa fitur
    1. Config, dapat digunakan untuk konfigurasi dan backup secara manual
       ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/admin-page-config.png)
    3. Manage User, admin dapat menambahkan pengguna baru, serta menghapus atau mengedit pengguna yang sudah ada.
       ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20185939.png)
    4. Footer Pages, digunakan untuk menyunting footer pages sesuai kebutuhan.
       ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/admin-page-footer.png)
    6. Site Customization, digunakan untuk mengubah atau mengcustom tampilan website sehingga terlihat lebih menarik.
       ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/admin-page-custom.png)
  - Pada menu Links, admin dapat melihat seluruh link yang sudah dibuat
    ![alt text]()
  - Pada menu Links juga, admin dapat menambahkan Page Icons untuk berintegrasi ke media sosial
    ![alt text]()
  - Pada menu Appearance, admin dapat mengatur halaman profile seperti profile picture, display name, dan lain-lain.
    ![alt text]()
  - Pada menu Themes, admin dapat mengubah atau mengcustom tema sendiri untuk halaman profile.
    ![alt text]()
  - Kemudian, admin juga dapat melihat preview kumpulan link yang sudah dibuat.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20172701.png)

  **USER**
  - Setelah login, user akan masuk ke halaman Dashboard. Disini user dapat melihat laporan total links dan link click-Nya.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Dashboard%20User.png)
  - Pada menu Add Link, user dapat menambahkan link dan custom nama linknya sesuai dengan keinginan. Setelah itu, dapat menambahkan link lainnya dengan klik save and add more. Pada menu ini terdapat Select Block dimana jenis link dapat dipilih sesuai dengan kebutuhan. Bahkan selain link, user juga dapat menambahkan Vcard.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Select%20Block%20(add%20link%20user).png)
  - Pada menu Links, user dapat melihat seluruh link yang sudah dibuat
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Kumpulan%20Link%20yang%20sudah%20dibuat.png)
  - Pada menu Links juga, user dapat menambahkan Page Icons untuk berintegrasi ke media sosial
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Page%20Icons%20(medsos).png)
  - Pada menu Appearance, user dapat mengatur halaman profile seperti profile picture, display name, dan lain-lain.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Appearance%20User.png)
  - Pada menu Themes, user dapat mengubah atau mengcustom tema sendiri untuk halaman profile.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Themes%20User.png)
  - Kemudian, user juga dapat melihat preview kumpulan link yang sudah dibuat.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Preview%20User.png)

# Pembahasan
[`^ kembali ke atas ^`](#)

**LinkStack** adalah sebuah aplikasi yang menyediakan opsi self-hosting yang mudah digunakan tanpa memerlukan pengetahuan teknis yang mendalam. Aplikasi ini juga memiliki berbagai kelebihan, seperti berikut:
- **Manajemen link yang Efisien:** LinkStack memberikan solusi yang efisien untuk mengelola dan berbagi link secara online, memungkinkan pengguna mengatasi batasan hanya dapat menambahkan satu link di platform media sosial.
- **Pilihan Block yang beragam:** Pada LinkStack terdapat block yang sangat banyak, bahkan user dapat membuat dan berbagi Vcard online.
- **Instansi Gratis untuk Pengguna Awam:** LinkStack menawarkan instansi gratis bagi pengguna yang tidak memiliki keahlian teknis untuk melakukan self-hosting.
- **Customisasi Halaman Profil:** Pengguna dapat dengan mudah membuat halaman profil custom mereka sendiri di LinkStack tanpa biaya tambahan.

Namun, LinkStack juga memiliki beberapa kekurangan, seperti berikut:
- **Kompleksitas Self-Hosting:** Meng-host link sendiri di server web pribadi atau penyedia hosting web mungkin memerlukan pengetahuan teknis yang lebih, dan proses pengaturan awal bisa lebih rumit.
- **Biaya Tambahan untuk Self-Hosting:** Self-hosting dapat menghasilkan biaya tambahan untuk hosting web, yang mungkin menjadi kendala bagi beberapa pengguna.
- Satu akun hanya bisa membuat satu **LinkStack**.

Dalam perbandingan dengan Linktree, LinkStack memiliki keunggulan dan kelemahan sebagai berikut:
- **Linktree** dikenal dengan kesederhanaan penggunaannya, sehingga cocok bagi pengguna yang ingin membuat halaman profil dengan cepat tanpa kerumitan. 
- **LinkStack** menonjol dalam hal fleksibilitas karena memungkinkan pengguna untuk meng-host link mereka sendiri di server web pribadi atau penyedia hosting web, memberi pengguna lebih banyak kontrol. Sebaliknya, Linktree memiliki keterbatasan dalam hal penyesuaian dan desain halaman profil.
- **Linktree** memiliki integrasi yang lebih mudah dan banyak dengan beberapa platform media sosial dan alat lainnya dibandingkan dengan **LinkStack**.
- Berbeda dengan **LinkStack** yang gratis, beberapa fitur tambahan Linktree, seperti analitik, penjadwalan link, dan opsi desain, hanya tersedia dalam paket berbayar.
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Linktree1.png)
![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Linktree2.png)

Aplikasi sejenis lainnya adalah **Link List (ipb.link)**.  Perbandingannya adalah sebagai berikut.
- Tampilan pada ipb.link kurang menarik dibandingkan dengan **LinkStack**
  ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/tampilan.png)
- Tema pada halamannya juga hanya sedikit dan terbatas (tidak bisa custom tema). Hal ini berbeda dengan **LinkStack** yang dapat custom halamannya tanpa biaya tambahan.
  ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/tema%20ipblink.png)
- Di luar link tambahan, integrasi ke media sosial langsung hanya terbatas untuk Twitter, Facebook, Instagram, dan Youtube saja.
  ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/ipblink%20medsos.png)

# Referensi
- [Azure Cloud](https://azure.microsoft.com/id-id/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Linktree](https://linktr.ee/)
- [Link List (ipb.link)](https://ipb.link/)

[`^ kembali ke atas ^`](#)
