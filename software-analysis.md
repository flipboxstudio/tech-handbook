# Panduan untuk *System Analyst*
Bagian ini berisi mengenai deskripsi dokumen analisis yang ada di Klinik Pintar, proses dan kesepakatan yang berlaku di Klinik Pintar.

---

### Dokumen *Software Requirement Specification*

Merupakan dokumen hasil analisis kebutuhan sistem yang diinginkan oleh pengguna. Dokumen ini berisi garis besar pembuatan sistem dan asumsi awal yang diberikan. Pembuatan dokumen ini dapat dilakukan dengan menggunakan *Google Drive Template* ( *New -> Google Docs -> From a template* )

Beberapa hal yang perlu dianalisis dalam dokumen ini adalah :

- Deskripsi singkat sistem yang akan dikerjakan, tujuan pembuatan sistem dan asumsi awal yang diberikan
- Fitur utama yang terdapat di dalam sistem
- Tipe pengguna di dalam sistem
- Teknologi yang akan digunakan dalam pembuatan sistem
- Diagram basis data (ERD) / *Class diagram*
- Penjelasan entitas sistem
- Daftar Pustaka / referensi

Masukkan dokumen SRS ke dalam drive folder dengan menggunakan penamaan sebagai berikut :

- *Parent Folder* : [NAMA PROJECT] Software Analysis
- Nama folder : SRS
- Nama berkas : SRS [Nama Project] [Platform]

---
### Dokumen *Product Backlog*

Merupakan dokumen hasil penjabaran analisis ke dalam deskripsi singkat fitur-fitur yang akan diimplementasikan (*user stories*). Pembuatan dokumen ini dapat dilakukan dengan menggunakan *Google Drive Template* ( *New -> Google Sheets -> From a template* )

Format *user stories* yang digunakan adalah 
`As a <User Role>, I can <do something>` atau bisa disingkat `<User Role> can <do something>`.
> Contoh : Admin can create user, Customer can buy products, dan lain lain.

Masukkan dokumen *Product Backlog* ke dalam drive folder dengan menggunakan penamaan sebagai berikut :

- *Parent Folder* : [NAMA PROJECT] Software Analysis
- Nama folder : PRODUCT BACKLOGS
- Nama berkas : Product Backlog [Nama Project] [Platform]

---
### Dokumen *Tech Spec*

Kepanjangan dari *Technical Specification*, dokumen ini berisi penjabaran setiap item dalam *Product Backlog* menjadi lebih detail dalam aspek teknis implementasi. Dokumen ini dibuat untuk mendukung *sprint* yang akan berjalan. Pembuatan dokumen ini dapat dilakukan dengan menggunakan *Google Drive Template* ( *New -> Google Docs -> From a template* )

Beberapa hal yang perlu dianalisis dalam dokumen ini adalah :

- Deskripsi dan tujuan *sprint*
- Tujuan *story*
- Data yang akan masuk ke dalam sistem
- Data yang akan dikeluarkan oleh sistem
- Alur kerja dari *story* yang akan diimplementasikan
- Penjabaran kasus yang memungkinkan terjadinya *error* dan penanganannya
- Validasi sistem
- Interaksi dengan sistem lain ( apabila ada )
- Aturan / batasan tambahan yang harus diperhatikan

Masukkan dokumen *Tech Spec* ke dalam drive folder dengan menggunakan penamaan sebagai berikut :

- *Parent Folder* : [NAMA PROJECT] Software Analysis
- Nama folder : TECH SPECS
- Nama berkas : Tech Spec [Nama Project] [Platform]

---

### Dokumen *Technical Test Specification*

Merupakan dokumen kolaborasi antara *System Analyst* dengan *Quality Assurance*. Dokumen ini menggabungkan antara *Tech Spec* dengan *Test Case* agar didapatkan proses yang efisien tanpa mengurangi kualitas dan informasi yang didapatkan dalam kedua dokument tersebut. Pembuatan dokumen ini dapat dilakukan dengan menggunakan *Google Drive Template* ( *New -> Google Sheets -> From a template* )

*Technical Test Spec* dibuat untuk proyek yang sudah biasa dikerjakan dan tidak memiliki tingkat kesulitan khusus.

Di dalam dokumen ini terdapat *sheet Tech Spec* yang akan diisi oleh *System Analyst*.

Masukkan dokumen *Tech Spec* ke dalam drive folder dengan menggunakan penamaan sebagai berikut :

- *Parent Folder* : [NAMA PROJECT] QUALITY
- Nama folder : Technical Tech Spec
- Nama berkas : TTS [Nama Project] [Platform]

---
### Dokumen *Tech Doc*

Kepanjangan dari *Technical Documentation*, dokumen ini berisi penjabaran teknis dari sistem yang telah diimplementasikan. Pembuatan dokumen ini dapat dilakukan dengan menggunakan *Google Drive Template* ( *New -> Google Docs -> From a template* )

Beberapa hal yang perlu dijabarkan dalam dokumen ini adalah :

- Deskripsi & Tujuan modul yang telah dibuat
- Deskripsi & Tujuan *user story* yang ada di dalam modul terkait
- Proses yang berjalan dalam *story* terkait dan dilengkapi dengan diagram proses
- Tampilan terkait proses yang telah dijabarkan dan interaksi yang ada di dalam tampilan tsb
- Basis data yang digunakan dalam implementasi *story* terkait
- Pesan dan kombinasi *error* yang telah diimplementasikan

Masukkan dokumen *Tech Doc* ke dalam drive folder dengan menggunakan penamaan sebagai berikut :

- *Parent Folder* : [NAMA PROJECT] Software Analysis
- Nama folder : TECH DOCS
- Nama berkas : Tech Doc [Nama Project] [Platform]

---