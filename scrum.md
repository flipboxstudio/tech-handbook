# Panduan SCRUM

Bagian ini berisi tentang proses SCRUM yang berjalan di Klinik Pintar, dan penerapannya di sistem kolaborasi yang digunakan

---
### SCRUM @ Klinik Pintar


SCRUM di Klinik Pintar terbagi ke dalam beberapa proses utama

- **_Backlog Refinement_** : This event is the act of breaking down and further defining Product Backlog items into smaller more precise items to ensures the items at the top of product backlog are ready for the next sprint.
- **_Sprint Planning_** : During Sprint Planning we answer three important questions: 

    - Why is this Sprint Valuable? 
    - What can be done this Sprint? 
    - How will the chosen work get done?

- **_Sprint_** : The purpose of the Daily Scrum is to inspect progress toward the Sprint Goal and adapt the Sprint Backlog as necessary, adjusting the upcoming planned work. The developers are allowed to adjust their plan to achieve the Sprint Goal outside Daily Scrum as well. Often, they meet throughout the day for more detailed discussions.
- **_Daily Standup_** : The purpose of the Daily Scrum is to inspect progress toward the Sprint Goal and adapt the Sprint Backlog as necessary, adjusting the upcoming planned work. The developers are allowed to adjust their plan to achieve the Sprint Goal outside Daily Scrum as well. Often, they meet throughout the day for more detailed discussions.
- **_Sprint Review_** : Scrum Team Members convey the results of the process during the Sprint in accordance with the Sprint Goal that was agreed upon during the Sprint Planning (Demo Session). 
- **_Sprint Retrospect_** : The main purpose of the Sprint Retrospective is to plan ways to increase quality and effectiveness. It is an opportunity to inspect and adapt the process the Scrum Team has been using to build the
increments.

---
### Azure Devops @ Klinik Pintar

Dalam proses menjalankan SCRUM, Klinik Pintar menggunakan sistem kolaborasi yang bernama Azure Devops. Berikut adalah hal hal penting yang harus dipahami dalam penggunaan Azure Devops

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

- ***P0***
- ***P1***
- ***P2***
- ***P3***

Selengkapnya dapat dilihat di dokumen [Priority Level Structure](https://docs.klinikpintar.id/share/98226c2f-0dcb-4079-a5f7-717c39cb7a22)
