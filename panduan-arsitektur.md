# Panduan Arsitektur Perangkat Lunak

## Struktur Component vs Functional 

Struktur berbasis fungsi: aplikasi disusun berdasarkan fungsi berkasnya (contohnya MVC, mempunyai layer Model, View & Controller sebagai struktur utama)

Struktur berbasis komponen: aplikasi disusun berdasarkan komponen yang disusun oleh berkas (contohnya ada komponen Dokter, Pengguna, Pesanan, Produk yang mungkin bisa berisi MVC, MVP atau struktur berbasis fungsi yang lain)

Kelebihan struktur berbasis fungsi 
- Lebih simpel
- Konteks teknis lebih jelas terlihat

Kelebihan struktur berbasis komponen
- Kemiripan konteks dengan frontend (yang memang sudah menggunakan arsitektur berbasis komponen)
- Konteks bisnis lebih jelas terlihat

Rekomendasi:
- Gunakan struktur berbasis komponen untuk FE
- Anjuran untuk menggunakan struktur berbasis komponen untuk BE

---
> "So what does the architecture of your application scream? When you look at the top level directory structure, and the source files in the highest level package; do they scream: Health Care System, or Accounting System, or Inventory Management System? Or do they scream: Rails, or Spring/Hibernate, or ASP?"
> - Uncle Bob


## Layer untuk Abstraksi

Klinik Pintar menggunakan Onion Architecture untuk memecah aplikasi menjadi beberapa layer dengan tujuan agar mendapatkan aplikasi yang lebih mudah dipelihara. Beberapa layer penting yang perlu diketahui adalah
- Model: Model adalah representasi dari data dan entitas bisnis pada aplikasi. Model biasanya merepresentasikan objek atau struktur & hubungan entitas dalam aplikasi, seperti pengguna, produk, atau pesanan.
- Repository: Repositori bertanggung jawab untuk mengelola dan memfasilitasi akses ke data, termasuk mengambil, menyimpan, dan memperbarui data melalui Model.
- Service: Service adalah komponen pada aplikasi yang bertanggung jawab untuk menjalankan tugas-tugas tertentu dalam aplikasi. Service biasanya berinteraksi dengan komponen lain di dalam aplikasi dan menerapkan aturan bisnis yang kompleks.
- Controller: Bertanggung jawab untuk mengontrol interaksi antara pengguna dan sistem, menerima permintaan dari pengguna, memproses permintaan tersebut, dan mengembalikan respons yang sesuai.

Hubungan antara Controller, Service, Repository dan Model adalah sbb:
- Controller akan melakukan akses ke Service untuk menjalankan logika bisnis aplikasi yang mungkin membutuhkan akses ke beberapa Repository
- Service akan melakukan akses ke Repository untuk mendapatkan data dari beberapa Model
- Repository akan melakukan akses ke Model untuk mendapatkan data dari DB
- Repository tidak bisa akses Service, dan Service tidak bisa akses ke Controller

Rekomendasi:
- Wajib menggunakan Repository Layer
- Anjuran untuk menggunakan Service Layer
- Gunakan layer & pattern lain yang dianjurkan oleh framework yang digunakan

Bacaan lebih lanjut mengenai [Onion Architecture](https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/)

## Data & Tipe Respon

Rekomendasi:
- Wajib menggunakan HTTP Code yang sesuai dengan respon
- Wajib menambahkan API testing untuk memastikan BE & FE mempunyai basis tes yang sama
- Anjuran untuk mematuhi [Klinik Pintar API Standard ](api-standard.md)

## Panduan spesifik Framework

### NodeJS
https://github.com/practicajs/practica

### Express
https://github.com/klinikpintar/express-component-starter

### PHP
https://github.com/klinikpintar/laravel-repository