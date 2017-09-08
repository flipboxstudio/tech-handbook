# Penggunaan Redmine dan SCRUM

Bagian ini berisi tentang proses SCRUM yang berjalan di Flipbox, dan penerapannya di sistem kolaborasi yang digunakan ( Redmine )

---
### SCRUM @ Flipbox

**SCRUM** adalah ...

SCRUM di Flipbox terbagi ke dalam beberapa proses utama

- **_Requirement Gathering_** : Pembuatan konsep awal yang menghasilkan dokumen SRS dan _Backlog_ yang berisi _User Stories_ ( dapat dilihat di bagian Panduan System Analyst )
- **_Sprint Planning_** : Proses perencanaan sprint yang menghasilkan dokumen _Technical Specification_ ( selanjutnya akan disebut _Tech Spec_ )
- **_Pre Grooming_** : Proses diskusi _Tech Spec_ untuk menyamakan pendapat dan meminimalisir resiko salah asumsi
- **_Grooming_** : Proses perencanaan sprint berjalan. Dalam proses ini dilakukan _Poker Planning_ untuk menentukan bobot setiap _Story_ yang telah ditentukan sebelumnya
- **_Sprint_** : Proses pengembangan sistem berdasarkan _Stories_ yang telah ditentukan sebelumnya
- **_Sprint Retrospect_** : Proses evaluasi _Sprint_ sebelumnya. Dalam proses ini akan dilakukan identifikasi masalah dan solusi yang harus dilakukan ke depannya.

---
### REDMINE @ Flipbox

Dalam proses menjalankan SCRUM, Flipbox menggunakan sistem kolaborasi yang bernama REDMINE. Berikut adalah hal hal penting yang harus dipahami dalam penggunaan REDMINE

**JENIS TASK**

- ***Story*** : pekerjaan terkait fitur yang akan dikembangkan
- ***Task*** : pekerjaan kecil pendukung fitur / pecahan *Story* yang akan dikembangkan
- ***Bug*** : pekerjaan terkait ketidaksesuaian atau kesalahan dalam fitur yang telah dikembangkan
- ***Hotfix*** : adalah *Bug* yang muncul saat sistem telah digunakan ( *in production* ) dan harus segera diselesaikan secepatnya. 
- ***Improvement*** : pekerjaan yang akan memperbagus fitur yang telah dikembangkan

**STATUS TASK**

- ***New*** : cukup jelas
- ***In Progress*** : sedang dalam pengerjaan. pengembang diharapkan mencatat waktu pengerjaan melalui fitur *log time / WorkTime*
- ***Resolved*** : pekerjaan sudah selesai dan bisa dilakukan testing oleh QA pada *staging server* atau *beta distribution platform*
- ***Pending*** : pekerjaan ditunda karena ada faktor penghambat
- ***Feedback*** : terdapat hal yang kurang jelas yang harus ditanyakan, diwajibkan untuk meninggalkan komentar/pertanyaan kepada PM
- ***Re-open*** : pekerjaan tidak lulus hasil uji QA dan membutuhkan perbaikan, diwajibkan untuk meninggalkan komentar terkait perbaikan yang dibutuhkan.
- ***Closed*** : pekerjaan lulus hasil uji QA dan siap untuk digunakan.
- ***Rejected*** : pekerjaan tidak akan dikerjakan karena ada beberapa faktor tertentu.

**PRIORITAS TASK**

- ***Low***
- ***Normal***
- ***High***
- ***Urgent***
- ***Immediate***

Selengkapnya dapat dilihat di dokumen [SOP Redmine](https://docs.google.com/presentation/d/1w2kwv066bAktqGxvwLaVD5VkBwsNNFb93iPZj0iJkLA/edit#slide=id.g128f9841ee_0_82)
