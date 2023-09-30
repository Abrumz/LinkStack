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

Aplikasi ini menyediakan opsi self-hosted yang sederhana dan tidak memerlukan pengetahuan teknis yang mendalam. Selain itu, LinkStack juga menawarkan instansi gratis bagi pengguna yang tidak memiliki keahlian teknis untuk self-hosting.

LinkStack mirip dengan Linktree dan menyediakan fitur dan pilihan yang sama seperti platform berbagi tautan komersial lainnya. Yang terpenting, LinkStack berkomitmen untuk tidak pernah menjual data pengguna dan mengutamakan privasi serta otonomi pengguna dalam mengelola dan berbagi tautan online.

## Instalasi
[`^ kembali ke atas ^`](#)

### Kebutuhan Sistem :
- Sistem Operasi: Windows, Unix, dan lainnya
- RAM: 64Mb atau lebih tinggi

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
