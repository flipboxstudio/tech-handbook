# Panduan untuk *Quality Assurance*
Bagian ini berisi mengenai panduan untuk melakukan testing dengan baik, deskripsi dokumen, proses dan kesepakatan yang berlaku di Flipbox.

---
### *Automated Testing*

Tes otomatis dilakukan dengan menggunakan *Katalon Studio* dan *Groovy* sebagai bahasa pemrogramannya.

Beberapa hal yang perlu diperhatikan dalam melakukan pembuatan tes otomatis adalah :

- Masukkan *Test Case* dan *Object Repository* dalam folder yang relevan untuk memudahkan organisasi kode
- Buat *Test Suite* dengan kombinasi beberapa *Test Case* agar menghasilkan tes yang mencakup  keseluruhan skenario
- Gunakan fasilitas *Custom Keywords* untuk pembuatan *reusable function* dan pembuatan kelas *Model*

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

Merupakan dokumen kolaborasi antara *Quality Assurance* dengan *System Analyst*. Dokumen ini menggabungkan antara *Tech Spec* dengan *Test Case* agar didapatkan proses yang efisien tanpa mengurangi kualitas dan informasi yang didapatkan dalam kedua dokument tersebut.

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
- [Java for Tester](https://www.udemy.com/complete-java-for-test-automation/learn/v4/overview)
- [Selenium WebDriver using Java](https://www.udemy.com/selenium-real-time-examplesinterview-questions/learn/v4/overview)
- [Katalon Studio Tutorial](http://toolsqa.com/katalon-studio-tutorial/)