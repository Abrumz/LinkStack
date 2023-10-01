<p align="center">
  <img width="200px" src="https://raw.githubusercontent.com/LinkStackOrg/branding/main/logo/svg/logo_animated.svg"><br>
  <br>
  <picture>
    <source media="(prefers-color-scheme: dark)" width="400px" srcset="https://raw.githubusercontent.com/LinkStackOrg/branding/main/logo/png/wordmark_light.png">
    <img width="400px" src="https://raw.githubusercontent.com/LinkStackOrg/branding/main/logo/png/wordmark_dark.png">
  </picture>
</p>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Maintenance](#maintenance) | [Otomatisasi](#otomatisasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:

# Sekilas Tentang
[LinkStack](https://github.com/LinkStackOrg/LinkStack) adalah aplikasi yang bertujuan memberikan solusi manajemen dan berbagi tautan online yang gratis dan berfokus pada privasi. LinkStack memungkinkan pengguna untuk memiliki kontrol penuh atas tautan mereka tanpa harus menjual data pribadi kepada pihak ketiga.

LinkStack mirip dengan Linktree dan menyediakan fitur dan pilihan yang sama seperti platform berbagi tautan komersial lainnya. Yang terpenting, LinkStack berkomitmen untuk tidak pernah menjual data pengguna dan mengutamakan privasi serta otonomi pengguna dalam mengelola dan berbagi tautan online.

# Instalasi
[`^ kembali ke atas ^`](#)

### Kebutuhan Sistem :
- Sistem Operasi: Windows, Unix, dan lainnya.
- RAM: 64Mb atau lebih tinggi
- PHP 8.x.x.
- SQLite

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

# Konfigurasi

# Maintenance

# Otomatisasi

# Cara Pemakaian
[`^ kembali ke atas ^`](#)
- Tampilan Aplikasi Web
  Cara pemakaian **LinkStack** sangat mudah dikarenakan aplikasi ini telah menyediakan interface yang mudah dimengerti.
  - Pertama, kita perlu login terlebih dahulu.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20165456.png)
  - Jika tidak memiliki akun, maka perlu Sign Up terlebih dahulu.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20165624.png)
  
  **ADMIN**
  - Setelah login, kita akan masuk ke halaman Dashboard. Disini kita dapat melihat laporan site statistics, registrations, dan active users
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20172344.png)
  - Pada menu Add Link, kita dapat menambahkan link dan custom nama linknya sesuai dengan keinginan. Setelah itu, dapat menambahkan link lainnya dengan klik save and add more.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20172509.png)
  - Pada menu Admin - Manage User, admin dapat menambah user baru, atau menghapus dan mengedit user.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20185939.png)
  - Kemudian, pada halaman berikut ini, kita dapat melihat (preview) link yang sudah dibuat.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20172701.png)

  **USER**
  - Setelah login, kita akan masuk ke halaman Dashboard. Disini kita dapat melihat laporan total links dan link click-Nya.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20175743.png)
  - Pada menu Add Link, kita dapat menambahkan link dan custom nama linknya sesuai dengan keinginan. Setelah itu, dapat menambahkan link lainnya dengan klik save and add more.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20175537.png)
  - Kemudian, pada halaman berikut ini, kita dapat melihat (preview) link yang sudah dibuat.
    ![alt text](https://github.com/Abrumz/LinkStack/blob/main/folder/Screenshot%202023-10-01%20175850.png)

# Pembahasan
[`^ kembali ke atas ^`](#)

**LinkStack** adalah sebuah aplikasi yang menyediakan opsi self-hosting yang mudah digunakan tanpa memerlukan pengetahuan teknis yang mendalam. Aplikasi ini juga memiliki berbagai kelebihan, seperti berikut:
- **Manajemen Tautan yang Efisien:** LinkStack memberikan solusi yang efisien untuk mengelola dan berbagi tautan secara online, memungkinkan pengguna mengatasi batasan hanya dapat menambahkan satu tautan di platform media sosial.
- **Instansi Gratis untuk Pengguna Pemula:** LinkStack menawarkan instansi gratis bagi pengguna yang tidak memiliki keahlian teknis untuk melakukan self-hosting.
- **Kustomisasi Halaman Profil:** Pengguna dapat dengan mudah membuat halaman profil kustom mereka sendiri di LinkStack tanpa biaya tambahan.

Namun, **LinkStack** juga memiliki beberapa kekurangan, seperti berikut:
- **Kompleksitas Self-Hosting:** Meng-host tautan sendiri di server web pribadi atau penyedia hosting web mungkin memerlukan pengetahuan teknis yang lebih, dan proses pengaturan awal bisa lebih rumit.
- **Biaya Tambahan untuk Self-Hosting:** Self-hosting dapat menghasilkan biaya tambahan untuk hosting web, yang mungkin menjadi kendala bagi beberapa pengguna.
- **Keterbatasan Integrasi:** LinkStack mungkin memiliki integrasi yang lebih terbatas dengan beberapa platform media sosial atau alat dibandingkan dengan Linktree.

Dalam perbandingan dengan Linktree, LinkStack memiliki keunggulan dan kelemahan sebagai berikut:
- **Linktree** dikenal dengan kesederhanaan penggunaannya, sehingga cocok bagi pengguna yang ingin membuat halaman profil dengan cepat tanpa kerumitan. 
- **Linktree** memiliki integrasi yang lebih mudah dengan beberapa platform media sosial dan alat lainnya, seperti Instagram, Twitter, dan Facebook, dibandingkan dengan LinkStack.
- **LinkStack** menonjol dalam hal fleksibilitas karena memungkinkan pengguna untuk meng-host tautan mereka sendiri di server web pribadi atau penyedia hosting web, memberi pengguna lebih banyak kontrol. Sebaliknya, Linktree memiliki keterbatasan dalam hal penyesuaian dan desain halaman profil.
- Beberapa fitur tambahan **Linktree**, seperti analitik, penjadwalan tautan, dan opsi desain, hanya tersedia dalam paket berbayar.

Aplikasi sejenis lainnya adalah **Linked List (ipb.link)**.  Perbandingannya adalah sebagai berikut.
- POKOKNYA JLEK

# Referensi
- [Azure Cloud](https://azure.microsoft.com/id-id/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Linktree](https://linktr.ee/)
- [Linked List (ipb.link)](https://ipb.link/)

[`^ kembali ke atas ^`](#)
