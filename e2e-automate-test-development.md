# Panduan untuk *End to End (E2E) Automation Test Developer*
Bagian ini berisi mengenai panduan untuk membuat kode, menggunakan *third-party tools*, penjelasan alur atau arsitektur dan pustaka yang ada dan/atau digunakan dalam membuat *end to end automation test* di Klinik Pintar.

---
---

## E2E Automation Test : Standar alur dan arsitektur untuk pembuatan *e2e automation test*

*End to end (e2e) testing* merupakan teknik pengujian untuk memastikan bahwa sistem telah berjalan sesuai alur yang telah ditentukan mulai dari awal sampai akhir di Klinik Pintar. *E2E testing* memiliki empat alur utama yang dibagi dalam perencanaan, perancangan, pelaksanaan, dan analisis hasil.

![](https://i.imgur.com/98gApwl.png)

### Perencanaan

Perencanaan merupakan tahap alur untuk menentukan dan membagi tugas, jadwal, dan sumber daya yang akan digunakan untuk melakukan pengujian pada sistem/modul/fitur/pembaruan/perbaikan yang akan dikerjakan.

**Input**:
Dokumen PRD,SRS, dan bentuk dokumentasi lainnya yang bisa menjelaskan sistem/modul/fitur/pembaruan/perbaikan yang akan dikerjakan.

**Output**:
**Story/Bug Card Azure** (*Description, figma, & acceptance criteria included*)

### Perancangan

Perancangan merupakan tahap alur untuk menentukan spesifikasi pengujian, pembuatan kasus uji (*test case*), analisis risiko, analisis penggunaan, dan penjadwalan pengujian dari tiap story/bug card azure yang telah ditentukan.

**Input**:
**Story/Bug Card Azure** (*Description, figma, & acceptance criteria included*)

**Output**:
**Azure Test Plan** (*test cases included*)

### Pelaksanaan

Pelaksanaan merupakan tahap alur untuk mengeksekusi *test cases* yang telah dirancang dan direncanakan pada *azure test plan*, melakukan demo pada *stakeholder* dan mendokumentasikan hasilnya.

**Input**:
**Azure Test Plan** (*test cases included*)

**Output**:
**Azure Test Plan Progress Report** dan uat/demo feedback list

### Analisis Hasil

Analisis hasil merupakan tahap alur untuk menganalisis hasil pengujian, mengevaluasi pengujian, melakukan pengujian tambahan jika diperlukan, merilis *release notes* dan merapikan dokumen *test plan* untuk (iterasi) pengembangan atau pemeliharaan selanjutnya.

**Input**:
**Azure Test Plan Progress Report** dan uat/demo feedback list

**Output**:
**Release Notes** dan *evaluation report*

---

![](https://i.imgur.com/yV3bmoO.png)

Penerapan *e2e testing* di klinik pintar secara teknik menerapkan pendekatan *functional* dan *non functional*. Setiap pendekatan memiliki daftar teknik/pengujian yang disarankan dan bisa digunakan untuk memenuhi kebutuhan layanan.

### Functional
Daftar teknik/pengujian:
- Unit testing
- Integration testing
- Smoke testing
- Sanity testing
- Regression testing
- Exploratory testing
- User acceptance testing

### Non Functional
Daftar teknik/pengujian:
- Load testing
- Performance testing
- Stress testing
- Security testing
- Accessibility testing

Untuk mendapatkan *test coverage* maksimal disarankan untuk menerapkan semua daftar teknik diatas di setiap (iterasi) pengembangan lol :D.

---

Penerapan *e2e testing* di klinik pintar secara eksekusi menerapkan pendekatan *manual* dan *automation* secara berurutan. Sebelum menerapkan pendekatan *automation* diharapkan untuk pengembang memastikan bahwa setiap komponen yang ada dalam pendekatan *manual* telah diterapkan, dilengkapi, atau disepakati.

### Manual
Komponen pendekatan *manual* yang perlu diterapkan dan dipastikan telah ada atau disepakati:
- Test Driven Development/Test Planning
- Test Cases and Scenarios
- Reporting
- Compatibility
- Verification and Validation

### Automation
Komponen pendekatan *automation* yang perlu diterapkan:
- Backend Automation
- Frontend Automation
- Mobile Automation (jika dibutuhkan)

Setiap *platform* pada klinik pintar memiliki kebutuhan dan basis sistem/*tools* yang bisa jadi berbeda sehingga secara standar penerapan *e2e testing* akan lebih dirincikan pada panduan yang telah dibagi berdasarkan *platform* nya.

---
---


## E2E AT Klinik OS : Standar alur dan arsitektur untuk pembuatan *e2e automation test* pada *platform* Klinik OS

Klinik OS merupakan *platform* di Klinik Pintar yang didesain untuk kebutuhan klinik secara khusus dalam menjalankan pelayanan kesehatan. Klinik OS memiliki fitur utama diantaranya fitur pendaftaran, rekam medis, dan pembayaran.

Lihat deskripsi selengkapnya di [Panduan E2E AT Klinik OS](https://github.com/medigoid/tech-handbook/blob/master/e2e-at-klinikos-development.md)

---
---


## E2E AT Website : Standar alur dan arsitektur untuk pembuatan *e2e automation test* pada *platform* Website

Website merupakan *platform* di Klinik Pintar yang didesain untuk kebutuhan perusahaan dalam melakukan *branding* pada pihak luar dan menghubungkannya ke semua layanan yang tersedia.

Lihat deskripsi selengkapnya di [Panduan E2E AT Website](https://github.com/medigoid/tech-handbook/blob/master/e2e-at-website-development.md)

---
---


## E2E AT Supply Chain System : Standar alur dan arsitektur untuk pembuatan *e2e automation test* pada *platform* Supply Chain System

Supply Chain System (SCM) merupakan *platform* di Klinik Pintar yang didesain untuk mengakomodasi layanan *supply chain*. SCM memiliki dua *platform* utama diantaranya, *supply chain management system* dan *catalog*.

Lihat deskripsi selengkapnya di [Panduan E2E AT SCM](https://github.com/medigoid/tech-handbook/blob/master/e2e-at-scm-development.md)

---
---

## E2E AT Corporate & Patient Portal : Standar alur dan arsitektur untuk pembuatan *e2e automation test* pada *platform* Corporate & Patient Portal

Corporate & Patient Portal merupakan *platform* di Klinik Pintar yang didesain untuk kebutuhan perusahaan dalam menyediakan layanan yang dikhususkan pada konsumen/klien perusahaan atau pasien.

Lihat deskripsi selengkapnya di [Panduan E2E AT CPP](https://github.com/medigoid/tech-handbook/blob/master/e2e-at-cpp-development.md)

---
---

## E2E AT Tools : Daftar *tools* yang digunakan untuk pengembangan

- *[CodeceptJS](https://codecept.io/)* (Backend/Frontend Automation)
- *[Monika](https://monika.hyperjump.tech/)* (Monitoring/Trigger)
- *[BetterUptime](https://betterstack.com/better-uptime)* (Monitoring)
- *[TestProjectIO](https://testproject.io/)* (E2E Automation)

---
---
