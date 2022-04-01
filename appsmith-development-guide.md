# Panduan Appsmith Development (*Web Dashboard*)
Berikut merupakan panduan dalam mengembangkan *web dashboard* menggunakan [Appsmith](https://docs.appsmith.com/).
#### Konten:
1. Environment
2. Design Guideline
3. Naming
4. Flow
5. Tips & Trick
6. Known Problem
---
## 1. Environment

Bagian environment [Appsmith](https://docs.appsmith.com/) yang wajib untuk dipahami secara berurutan antara lain:
1. Widgets
2. Queries/JS
3. Properties
4. Canvas
5. Data Sources
6. Git (Beta)
7. Dependencies
8. Pages
---
## 2. Design Guideline

![](https://i.imgur.com/jEUlb6W.png)
Secara default komponen utama UI terdiri atas 4 bagian, yaitu:
### Header
Bagian yang berisikan informasi terkait identitas dashboard dan terbagi atas tiga komponen, yaitu:
1. Logo
2. Judul
3. Versi (opsional)

![](https://i.imgur.com/UW9g2HH.png)

### Filter
Bagian yang berisikan komponen untuk melakukan filter data yang akan ditampilkan dan terbagi atas tiga komponen utama, yaitu:
1. Filter waktu (tanggal mulai dan berakhir)
2. Tombol terapkan filter
3. Tombol unduh semua data

![](https://i.imgur.com/sC5oMxi.png)

Jika ada permintaan untuk menambahkan filter pada field lain maka dapat ditambahkan dalam bagian ini.

### Table
Bagian yang berisikan komponen untuk menampilkan data yang tersimpan berdasarkan filter dan terbagi atas tiga komponen utama, yaitu:
1. Judul
2. Daftar data
3. Tombol tambah data (opsional)

![](https://i.imgur.com/RRaPbhk.png)

Komponen tabel pada bagian ini diatur hanya menampilkan fitur kolom cari dan *pagination by server*.

### Download popup
Bagian yang berisikan komponen untuk menampilkan semua data yang tersimpan berdasarkan filter dan terbagi atas empat komponen utama, yaitu:
1. Modal Popup
2. Judul
3. Tombol tutup
4. Daftar data

![](https://i.imgur.com/S6nE71u.png)

Komponen tabel pada bagian ini diatur hanya menampilkan fitur *download* dan *pagination*.

---

## 3. Naming
Masing - masing *widget* memiliki aturan dalam penamaan untuk memudahkan identifikasi & kegunaan, yakni:
- **Text**: `txt_<Nama>/txt_<Nama>_<Akronim Deskripsi>` (ex: `txt_title`, `txt_count_lbl`).
- **Select**: `dd_<Nama>` (ex: `dd_status`).
- **Checkbox**: `cb_<Nama>` (ex: `cb_reason`).
- **DatePicker**: `dp_<Nama>` (ex: `dp_created`).
- **Divider**: `div_<Nama>` (ex: `div_assessment`).
- **FilePicker**: `fp_<Nama>` (ex: `fp_document`).
- **Modal**: `mdl_<Nama>` (ex: `mdl_edit`).
- **Table**: `tbl_<Nama>` (ex: `tbl_data`).
- **Button**: `btn_<Nama>` (ex: `btn_save`).

Untuk kasus file yang tak punya aturan penamaan, by default mengikuti aturan penamaan `<Nama Komponen>_<Nama>_<Akronim Deskripsi>`.

Selain itu, penamaan komponen dalam modal, tinggal menambahkan nama dari modal setelah nama/identifikasi komponennya.
`<Nama Komponen>_<Nama Modal>_<Nama>_<Akronim Deskripsi>` (ex: `txt_download_title`).

Selain penamaan komponen widget, penamaan fungsi di javascript object,  query, dan API juga memiliki aturan yakni:
- **javascript object**: `<Fungsi><Nama>` (ex: `parseStatus`), menggunakan camelBack notation.
- **query/API**: `<Predicate><Nama>` (ex: `getPatientDetail`), menggunakan camelBack notation.

Beberapa aturan lainnya yang perlu diperhatikan ialah:
- Jika nama terlalu panjang, bisa menggunakan akronim (ex: edit data pasien = edp).
- Hindari nama yang kompleks & panjang.
---

## 4. Flow
Alur dalam *web dashboard* secara default terdiri dari 2 alur, yakni:

**Pembacaan Data**
  - Akses halaman.
  - Penerapan Filter.
  - Unduh data.

**Perubahan Data**
  - Pencarian data.
  - Menampilkan rincian data.
  - Menyimpan data

Untuk alur lainnya ditambahkan dan disesuaikan dengan kebutuhan bisnis.

---

## 5. Tips & Trick
Berikut daftar saran yang sebaiknya dilakukan saat melakukan pengembangan:
1. **Duplicate before create**, sebelum membuat dashboard/komponen baru pastikan untuk mengecek apa yang sudah ada untuk menghindari kondisi buat dari awal.
2. **One person at a time**, sebelum fitur *multiplayer editing* rilis jangan edit dashboard secara bersamaan.
3. **Git only for automated test**, berhubung masih beta dan fiturnya terbatas, git hanya digunakan untuk kebutuhan integrasi automated test ke pipeline azure.
4. **Stable internet connection is a must**, untuk kesehatan mental yang lebih baik.
5. **FormIO is our buddy**, ikutin aturan formio ketika ubah data dari databasenya.
6. **Oh Serverless, my angel**, query lambat/bermasalah/banyak/kompleks, pindahkan ke serverless...fitur datasources bermasalah, pindahkan ke serverless...hidup bermasalah, *go get some help dude*.
7. **level of abyss**, jika memanggil query/api secara serial, jangan lebih dari 7 anak/rantai, 8 keatas potensi ketemu penunggu appsmith-nya tinggi (ex: 1->2->3->4->5->6->7-> \\(-w-\\) ).
8. **Appsmith is prime suspect before your code**, bug aneh? silakan cek bagian **known problem** dan [forum curhat](https://github.com/appsmithorg/appsmith/issues) terlebih dahulu.
9. **Start with few request**, minimalisir pemanggilan query/api saat pertama kali load dashboard dengan memastikan menonaktifkan *run query on page load* pada api yang tidak perlu dipanggil pertama kali.
10. **Beware of Smart BSON**, fitur yang membantu tapi dalam beberapa kasus jangan lupa dimatikan (ex: mengirim data string yang isinya angka semua).
11. **Set Default Value**, ketika akan menampilkan data atau logic pada komponen widget pastikan untuk memberikan default value berupa *empty string*, 0 atau sesuai jenis fieldnya untuk menghindari masalah aneh.

---

## 6. Known Problem
Berikut daftar masalah yang teridentifikasi sebagai bug/anomaly/error aneh yang ditemukan dalam pengembangan:
1. Jika data yang diquery telah mencapai 800 data keatas akan kena error wrong date format di datasource mongodb pada field yang berisi data tipe date.
2. Urutan kolom pada widget table tidak mengikuti urutan key value pada return response kode yang telah diterapkan sehingga harus mengurutkan secara manual melalui widgetnya.
3. Fitur geser komponen widget lain di canvas tidak bekerja ketika memindahkan banyak komponen widget sekaligus.
4. Animasi loading pada widget button berhenti duluan sebelum proses dalam metode *on click* selesai semua.
5. Public share perlu dimatikan dan nyalakan kembali untuk tetap bekerja ketika deploy dengan fitur git terpasang.

Silakan tambahkan kesini jika menemukan bug/anomaly/error aneh terbaru dan tambahkan label **[Solved]** jika tidak pernah terjadi lagi atau ada pemberitahuan masalah tersebut telah diselesaikan.