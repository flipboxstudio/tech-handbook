# Panduan untuk *Quality Assurance*
Bagian ini berisi mengenai panduan untuk melakukan testing dengan baik, deskripsi dokumen, proses dan kesepakatan yang berlaku di Flipbox.

---
### *Automated Testing*

Tes otomatis dilakukan dengan menggunakan *supertest* untuk API testing dan *artilerry.io* untuk stress testing.

Beberapa hal yang perlu diperhatikan dalam melakukan pembuatan tes otomatis adalah :

- Pastikan data yang dibutuhkan tersedia, apabila diperlukan buat data dummy terlebih dahulu
- Pastikan skenario yang dibuat sudah mencakup berbagai kondisi, meliputi *positive case* , *negative case*  dan validasi data masuk/keluar ataupun data kosong
- Pastikan bahwa komunikasi selalu terjalin baik dengan developer untuk menghindari miskomunikasi dan automated testing bisa diselesaikan sebelum development PR

---
### *Manual Testing & Test Case Document*

Tes manual dilakukan dengan menggunakan dokumen *Test Case* untuk panduan langkah langkah testing. 

Tes manual dilakukan oleh pengembang setelah melakukan *Pull Request* untuk kemudian dikonfirmasi oleh QA. Sebelum *sprint* berakhir, QA akan memastikan kembali seluruh pekerjaan yang diselesaikan sudah memenuhi kondisi yang tertera di dalam dokumen *Test Case*

Beberapa hal yang perlu diperhatikan dalam melakukan pembuatan tes manual adalah :

- Pastikan skenario yang dibuat sudah mencakup berbagai kondisi, meliputi *positive case* , *negative case* , *corner cases* dan validasi data masuk/keluar ataupun data kosong.
- Masukkan dokumen yang telah dibuat ke dalam drive folder dengan menggunakan penamaan sebagai berikut : 
	- *Parent Folder* : [NAMA PROJECT] QUALITY
	- *Test Case Folder* : Test Case Sprint X
	- Nama berkas : Test Case [Nama Project] [Platform]
	- Atur dokumen berdasarkan tanggal pengisian

---
### Dokumen *Technical Test Specification*

Merupakan dokumen kolaborasi antara *Quality Assurance* dengan *System Analyst*. Dokumen ini menggabungkan antara *Tech Spec* dengan *Test Case* agar didapatkan proses yang efisien tanpa mengurangi kualitas dan informasi yang didapatkan dalam kedua dokument tersebut. Pembuatan dokumen ini dapat dilakukan dengan menggunakan *Google Drive Template* ( *New -> Google Sheets -> From a template* )

*Technical Test Spec* dibuat untuk proyek yang sudah biasa dikerjakan dan tidak memiliki tingkat kesulitan khusus.

Di dalam dokumen ini terdapat *sheet Test Case* yang akan diisi oleh *Quality Assurance*.

Masukkan dokumen *Tech Spec* ke dalam drive folder dengan menggunakan penamaan sebagai berikut :

- *Parent Folder* : [NAMA PROJECT] QUALITY
- Nama folder : Technical Tech Spec
- Nama berkas : TTS [Nama Project] [Platform]

---
### Dokumen *User Manual*

Manual penggunaan sistem dibuat sebelum sistem dirilis ke pengguna. Manual penggunaan berisi beberapa hal utama yaitu :

- Garis besar kegunaan sistem
- *Screenshot* dari halaman sistem
- Penjelasan mengenai kegunaan dan fungsi yang terkandung dalam halaman tersebut

Masukkan dokumen manual penggunaan sistem ke dalam drive folder dengan menggunakan penamaan sebagai berikut :

- *Parent Folder* : [NAMA PROJECT] QUALITY
- Nama berkas : User Manual [Nama Project] [Platform]
- Jika dibutuhkan, masukkan berkas ke dalam folder bernama *User Manual*

---
Bacaan tambahan ( gunakan akun Flipbox untuk akses Udemy *course* ) :

- [Panduan Penggunaan Fabric](https://github.com/flipboxstudio/tech-handbook/blob/develop/fabric-guide.md)