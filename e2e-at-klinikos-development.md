# Panduan E2E AT Klinik OS Development
Berikut merupakan panduan dalam mengembangkan *e2e automation test* menggunakan [Codeceptjs](https://codecept.io/), dan [TestProjectIO](https://testproject.io/).

#### Konten:
1. Environment
2. Execution Guideline
3. Naming
4. Flow
5. Tips & Trick
6. Known Problem

---

## 1. Environment
Bagian environment [Codeceptjs](https://codecept.io/) yang wajib untuk dipahami secara berurutan antara lain:
1. Package
2. Configuration
3. Terminal Command (CLI)
4. Basic Command/Function
5. Debug
6. Retries
7. Conditional Actions
8. Multiple Sessions
9. Page Object
10. Behavior Driven Development

Bagian environment [TestProjectIO](https://testproject.io/) yang wajib untuk dipahami secara berurutan antara lain:
1. Project
2. Adds On
3. Agents
4. Reports
5. Integration
6. Monitor

---

## 2. Execution Guideline
Secara default alur utama pembuatan **e2e automation test** pada *platform* **Klinik OS** mengikuti alur umum **e2e testing** akan tetapi pendekatan *automation* pada modul yang telah dikerjakan akan diterapkan di iterasi berikutnya.

Alur pengujian dilakukan secara berurutan setiap modul dengan melengkapi kebutuhan pendekatan manual, membuat script automation, dan deploy ke server untuk dijalankan secara berkala setiap hari.

Berikut checklist pengujian yang mesti dilakukan beserta statusnya:
### Functional
Daftar teknik/pengujian:
- Unit testing
- Integration testing **(Done - Manual)**
- Smoke testing **(Done - Manual/Automation)**
- Sanity testing **(Done - Manual)**
- Regression testing **(Done - Manual/Automation)**
- Exploratory testing **(Done - Manual)**
- User acceptance testing

### Non Functional
Daftar teknik/pengujian:
- Load testing
- Performance testing
- Stress testing
- Security testing
- Accessibility testing

---

## 3. Naming

### Test script
Penamaan test scipt disimpan dalam folder sesuai fungsinya dan memiliki aturan dalam penmaan unutk memudahkan idenetifikasi & kegunaan, yakni:
  - **Feature**: `nama-modul.feature` (ex: `medical-record.feature`)
  - **Step Definitions**: `nama-modul.js/ts` (ex: `medical-record.js`)
  - **Page Object**: `NamaModul.js/ts` (ex: `MedicalRecord.js`)

Penamaan skenario dalam test script memiliki aturan dalam penamaan untuk memudahkan identifikasi & kegunaan, yakni:
  - **Tag**: `@<Nama/Akronim Modul>-module @<Use Case>` (ex: `@mr-module @create`) 
  - **TCID**: `<Akronim Peran>-<Akrnonim Modul>-<ID>` (ex: `CA-MRM-01`)
  - **Skenario**: `<TCID>: As an <peran>, <aktivitas> <deskripsi/keterangan>` (ex: `<CA-MRM-01>: As a clinic admin, I can create medical record with required data`)

### Widget / UI Components 
Masing - masing *widget/ui components* memiliki aturan dalam penamaan untuk memudahkan identifikasi & kegunaan, yakni:
- **Text/Label**: `txt_<Nama>/txt_<Nama>_<Akronim Deskripsi>` (ex: `txt_title`, `txt_count_lbl`).
- **Text Field**: `tf_<Nama>/tf_<Nama>_<Akronim Deskripsi>` (ex: `tf_email`).
- **Dropdown/Select**: `dd_<Nama>` (ex: `dd_status`).
- **Checkbox**: `cb_<Nama>` (ex: `cb_reason`).
- **Radio Button**: `rb_<Nama>` (ex: `rb_gender`).
- **Button**: `btn_<Nama>` (ex: `btn_save`).
- **Divider**: `div_<Nama>` (ex: `div_assessment`).
- **Section**: `sec_<Nama>` (ex: `sec_clinic`).
- **Table**: `tbl_<Nama>` (ex: `tbl_data`).

Untuk kasus file yang tak punya aturan penamaan, by default mengikuti aturan penamaan `<Nama Komponen>_<Nama>_<Akronim Deskripsi>`.
 
Beberapa aturan lainnya yang perlu diperhatikan ialah:
- Jika nama terlalu panjang, bisa menggunakan akronim (ex: edit data pasien = edp).
- Hindari nama yang kompleks & panjang.

---

## 4. Flow
Alur dalam penyusunan *test script* secara *default* terdiri dari 7 alur/skenario, yakni:

**Pembacaan Data**
  - Akses halaman.
  - Menampilkan rincian data.
  - Mengecek komponen tampilan.
  - Mengecek data.
  - *Pagination* (opsional).

**Penyaringan Data**
  - Akses halaman.
  - Pencarian data.
  - Penerapan filter.
  - Mengecek komponen tampilan.
  - Mengecek data.
  - *Pagination* (opsional).

**Penambahan Data**
  - Akses halaman tambah.
  - Mengecek komponen tampilan.
  - Menambah Data.
  - Mengecek data yang ditambah.

**Perubahan Data**
  - Akses halaman ubah.
  - Mengeccek komponen tampilan.
  - Mengecek data.
  - Merubah data.
  - Membandingkan data yang diubah.

**Penghapusan Data**
  - Akses halmaan hapus.
  - Mengecek komponen tampilan.
  - Menghapus Data.
  - Mengecek Data yang dihapus.

**Pengujian Negatif**
  - Akses halaman.
  - Mengecek komponen tampilan.
  - Membatalkan tambah/ubah/hapus data.
  - Mengecek data tidak tertambah/terubah/terhapus.

**Pengujian visual**
  - Akses halaman.
  - Menghasilkan dan menyimpan data uji.
  - Menangkap dan membandingkan tampilan dengan data uji.

Untuk alur lainnya ditambahkan dan disesuaikan dengan kebutuhan bisnis.

---

## 5. Tips & Trick
Berikut daftar saran yang sebaiknya dilakukan saat melakukan pengembangan:
1. **Duplicate before create**, sebelum membuat script baru pastikan untuk mengecek apa yang sudah ada untuk menghindari kondisi buat dari awal.
2. **Stable internet connection is a must**, untuk kesehatan mental yang lebih baik.
3. **Codeceptjs is prime suspect before your code**, bug aneh? silakan cek bagian **known problem** dan [forum curhat](https://github.com/codeceptjs/CodeceptJS/issues) terlebih dahulu.
4. **Start with small scenario**, pastikan untuk membagi scenario secara kecil untuk memudahkan debugging.
5. **Don't forget waiting time**, selalu gunakan wait untuk semua perintah crud maupun navigasi halaman.
6. **Styling and content first**, pastikan untuk mengecek styling dan konten yang ditampilkan.

---

## 6. Known Problem
Berikut daftar masalah yang teridentifikasi sebagai bug/anomaly/error aneh yang ditemukan dalam pengembangan:
1. Beberapa wording & penamaan komponen masih belum sesuai dengan *use case*, sehingga bisa disesuaikan terlebih dahulu untuk *element locator / xpath* yang akan digunakan.
2. Beberapa modul memiliki *response time* yang tidak menentu, sehingga bisa gunakan rentang waktu 10-30s pada *command* *WaitForElement* / *WaitToHide* agar skenario tetap bisa berjalan.

Silakan tambahkan kesini jika menemukan bug/anomaly/error aneh terbaru dan tambahkan label **[Solved]** jika tidak pernah terjadi lagi atau ada pemberitahuan masalah tersebut telah diselesaikan.