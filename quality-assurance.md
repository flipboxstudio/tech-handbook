# Panduan untuk *Quality Assurance*
Bagian ini berisi mengenai panduan untuk melakukan testing dengan baik, deskripsi dokumen, proses dan kesepakatan yang berlaku di Klinik Pintar.

---
### *Automated Testing*

Tes otomatis dilakukan dengan menggunakan *supertest* untuk API testing dan *artilerry.io* untuk load testing.

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

### *RULES Untuk Report Bugs*

Ketika tim QA menemukan bugs atau ada yang harus diimprove di dalam aplikasi, ada *standar report* yang harus diperhatikan: 

*BUGS*
- *How to Reproduce*	: berisi step by step bagaimana mendapatkan bugs tersebut.
- *Actual Result*	: berisi output dari step yang dijalankan.
- *Expected Result*	: berisi output yang semestinya (yang benar)
- *Extra Information*	: bisa berupa *screenshot* atau *credential* yang digunakan untuk testing

*IMPROVEMENT*
- *What to improve*	: bagian apa saja yang harus di improve
- *How to improve*	: menjelaskan bagaimana itu harus di improve

---
  
### FLOW REVIEW *PR (PULL REQUEST)* 

Peran tim *Quality Assurance* dalam *Pull Request* adalah untuk me-review fitur baru atau bugfix berjalan sebagaimana mestinya sebelum merge ke develop atau master. Beberapa hal yang perlu diperhatikan dalam *Pull Request* ini adalah:

- Pastikan tidak ada *Conflict* di dalam *Pull Request* tersebut. Jika ada *Conflict* beritahukan ke developer terkait untuk segera resolve *Conflict* . 
- Pipeline *Passed* (berlaku untuk semua *Pull Request*).
- Jika pipeline *Failed* karena *API test script*, cek kembali *test script* apakah masih relevan atau perlu *update*
- Apabila menggunakan *Server Latest* untuk *testing pull request* , pastikan branch terkait berada di paling atas
- *Pull Request* baru bisa di merge oleh tim QA setelah mendapatkan *Approval* dari *QA* yang diassign dan *Captain* dari tim dev yang ditunjuk untuk *review code*
- Ketika *merge* branch, pastikan ceklis bagian *Close Source Branch*

Tim *QA* juga berhak melakukan *Decline Pull Request* dengan ketentuan sebagai berikut:

- Tidak ada *File Changes* di dalam *Pull Request* (*File Changes 0*).
- *File Duplicate*. Jika terdapat 2 PR berisi *file changes* yang sama, maka salah satu dapat di *Decline*. Dan pastikan bahwa terdapat penjelasan *pull request* yang di *decline* terkait atau sama dengan *pull request* mana.
- Jumlah *file changes* terlalu banyak. Ada ketentuan maksimal jumlah *file changes* dalam 1 *Pull Request* :
	- *Web dan IOS : +/- 50 file changes*
	- *Android     : +/- 30 file changes*
- Tidak ada *description* didalam *pull request*. Minimal harus ada *Commit messages* 
- Sebelum melakukan *decline*, komunikasikan terlebih dahulu dengan developer yang bersangkutan. 


---

Bacaan tambahan ( gunakan akun Klinik Pintar untuk akses Udemy *course* ) :

- [Panduan Penggunaan Fabric](https://github.com/medigoid/tech-handbook/blob/develop/fabric-guide.md)
