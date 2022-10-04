# Panduan untuk *Quality Assurance*
Bagian ini berisi mengenai panduan untuk melakukan testing dengan baik, deskripsi dokumen, proses dan kesepakatan yang berlaku di Klinik Pintar.

---
### *Quality Assurance Workflow*

Alur *Quality Assurance* yang dilakukan saat ini adalah sebagai berikut:
1. Membuat dokumen tes untuk masing-masing *user story* pada sprint terkait
2. Melakukan PR Review dan memastikan sistem yang dibangun sudah sesuai dengan *acceptance criteria*
3. Membangun *E2E Automation Test* untuk setiap *user story* yang sudah masuk kedalam *staging server*
4. Melakukan Demo/UAT untuk masing-masing *user story* pada saat *sprint review*
5. Membuat *Release Notes* untuk setiap *user story* / *bugfix* ketika melakukan release ke *production server* 

---
### Dokumen Tes

Dokumen tes dibuat dengan menggunakan *Azure DevOps - Test Plan*.
Beberapa hal yang perlu diperhatikan dalam melakukan pembuatan dokumen tes adalah:

- Pastikan setiap *sprint* memiliki 1 *test plan*. Setiap *test plan* akan berisi *test suite* sebanyak *user story* pada *sprint* terkait. Setiap *test suite* akan berisi beberapa *test case* berdasarkan *acceptance criteria* dan skenario yang dibutuhkan untuk mengatasi berbagai kondisi.
- Pastikan skenario yang dibuat sudah mencakup keseluruhan kondisi, baik *positive case*, *negative case*, *corner case*. Akan lebih baik jika dengan mempertimbangkan salah satu atau beberapa dari teknik *testing* berikut *Boundary Value Analysis*, *Equivalence Partitioning*, *Decision Table*, *State Transition Diagram*, atau *Error Guessing*

---
### *Manual Test*

Tes manual dilakukan berdasarkan dokumen tes untuk panduan langkah langkah *testing*. 
Tes manual dilakukan oleh pengembang setelah melakukan *Pull Request* untuk kemudian dikonfirmasi oleh QA. Setelah terkonfirmasi, *Pull Request* akan *merge* ke *staging server*. dan QA akan memulai untuk membangun *E2E Automation Test* pada *staging server*

Sebelum *sprint* berakhir, QA akan memastikan kembali seluruh pekerjaan yang diselesaikan sudah memenuhi kondisi yang tertera di dalam dokumen tes

---
### *E2E Automation Test*

*E2E Automation Test* dibangun dengan menggunakan framework *[CodeceptJS](https://codecept.io/)*.
Beberapa hal yang perlu diperhatikan dalam melakukan pembuatan *E2E Automationt Test* adalah :

- Pastikan *E2E Automation Test* yang dibangun menggunakan format *Behaviour Driven Development* dengan *Gherkin Syntax*
- Pastikan *E2E Automation Test* yang dibangun berdasarkan dokumen tes dan dapat dijalankan berulang kali
- Sebelum menjalankan *E2E Automation Test*, Pastikan data yang dibutuhkan tersedia, apabila diperlukan buat data *dummy* terlebih dahulu
- Selain berdasarkan dokumen tes (per *sprint*), disarankan untuk membangun *E2E Automation Test* per modul juga untuk mempermudah dalam melakukan *regression test*

Lihat deskripsi selengkapnya di [Panduan E2E AT Development](https://github.com/medigoid/tech-handbook/blob/master/e2e-automate-test-development.md)

---

### *Bug Report Procedure*

Ketika tim QA menemukan bugs atau ada yang harus diimprove di dalam aplikasi, ada *standar report* yang harus diperhatikan: 

*BUG*
- *Severity* : berisi level tingkatan resiko atau seberapa pengaruh bugs terhadap sistem
- *Priority* : berisi level prioritas bug untuk diperbaiki
- *Steps to Reproduce* : berisi step by step bagaimana mendapatkan bugs tersebut.
- *Actual Result*	: berisi output dari step yang dijalankan.
- *Expected Result*	: berisi output yang semestinya (yang benar)
- *Extra Information*	: bisa berupa *screenshot* atau *credential* yang digunakan untuk testing

*IMPROVEMENT*
- *What to improve*	: bagian apa saja yang harus di improve
- *How to improve*	: menjelaskan bagaimana itu harus di improve

---
  
### *Review PR (Pull Request) Flow* 

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

### *Release Notes* 

*Release Notes* dibuat dengan menggunakan *[Docs Klinik Pintar](https://docs.klinikpintar.id/doc/release-notes-VnZ2Q4m4iC)* pada menu *Product* > *Release Notes*.
Beberapa hal yang perlu diperhatikan dalam melakukan pembuatan *Release Notes* adalah:

- Penamaan judul *Release Notes* menggunakan format **[Nama Platform] - Release [Tanggal Release] (Version [Versi Platform])**. Sebagai contoh: **Klinik OS - Release 1 April 2022 (Version 1.16.0)**
- Outline dari *Release Notes* adalah sebagai berikut:
	- [H1] Apa yang baru?
		- [H2] Modul - Fitur 1
	- [H1] Apa yang berubah?
		- [H2] *Improvements*
			- [H3] *Improvements* Modul 1 - Keterangan *Improvements*
		- [H2] *Fixes*
			- [H3] *Fixes* Modul 1 - Keterangan *Fixes*
- Pastikan untuk menambahkan *screenshot* gambar atau gif untuk menjelaskan langkah - langkah menjalankan fitur baru atau *improvements* fitur lainnya
- Setelah *Release Notes* selesai dibuat, pastikan untuk memberi info kepada *stakeholder* terkait atau bagikan dokumen *Release Notes* melalui Klinik Pintar *Google Chat Space General* pada thread *Release Notes*

---

Bacaan tambahan ( gunakan akun Klinik Pintar untuk akses Udemy *course* ) :