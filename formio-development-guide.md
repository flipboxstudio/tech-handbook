# Panduan FormIO Development (*Web Form*)
Berikut merupakan panduan dalam mengembangkan *web form* menggunakan [FormIO](https://help.form.io/intro/overview).
#### Konten:
1. Environment
2. Design Guideline
3. Naming
4. Flow
5. Tips & Trick
6. Known Problem
---
## 1. Environment

Bagian environment maupun komponen dari [FormIO](https://help.form.io/intro/overview) yang wajib untuk dipahami secara berurutan antara lain:
1. Create new form
2. Create new resource
3. Edit form
4. Access
5. Form actions
6. View data
---
## 2. Design Guideline

![](https://i.imgur.com/B2T27LG.png)
Secara default komponen utama UI terdiri atas 2 bagian, yaitu:
### Title
Bagian yang berisikan informasi terkait judul formulir

![](https://i.imgur.com/8Rv4W6T.png)

### Content
Bagian yang berisikan daftar field yang dibutuhkan untuk mengisi data

![](https://i.imgur.com/nG4tTvE.png)

Web formulir yang dibuat selanjutnya akan di-embed dalam halaman publik dari klinik pintar dengan format `https://klinikpintar.id/formulir/<ID Form>` yang mana halaman publik tersebut memiliki dua komponen utama, yaitu:

### Header (logo) 
![](https://i.imgur.com/P0y4SQL.png)

### Footer (informasi layanan, solusi, tentang, dan kontak)
![](https://i.imgur.com/1PNU0Qk.png)

---

## 3. Naming
Format default yang digunakan dalam penamaan api dalam *widget* untuk memudahkan identifikasi & kegunaan dari data yang disimpan adalah:
`<Nama><Akronim Deskripsi>` 
(ex: **nomorWAPasien**, **alamatDokter**).

Jika dalam design-nya menggunakan beberapa *layout components* (ex: panel) dan memiiki field isian yang sama maka dapat menggunakan format:
`<Nama Layout Component><Nama Bagian><Nama><Akronim Deskripsi>`
(ex: **panelPasienNomorWA**, **panelDokterAlamatPraktik**).

Jika dalam design-nya komponen data yang disimpan digunakan sebagai assessment dan tidak memiliki label khusus maka dapat menggunakan format:
`question<Akronim Kategori/Deskripsi><Nomor Pertanyaan>` 
atau
`<Nama Layout Component><Akronim Kategori/Deskripsi><Nomor Pertanyaan>`
(ex: **questionRD1**, **panelDokterRD2**).

Beberapa aturan lainnya yang perlu diperhatikan ialah:
- Menggunakan camelBack notation (ex: panelPasienAlamat).
- Jika nama terlalu panjang, bisa menggunakan akronim (ex: remaja dewasa = RD).
- Hindari nama yang kompleks & panjang.
---

## 4. Flow
Alur dalam *web form* secara default terdiri dari 1 alur, yakni:
**Penambahan Data**
  - Akses halaman.
  - Mengisi formulir.
  - Mengirim data.
  - Mendapatkan notifikasi email/wa (opsional)

Untuk alur lainnya ditambahkan dan disesuaikan dengan kebutuhan bisnis.

---

## 5. Tips & Trick
Berikut daftar saran yang sebaiknya dilakukan saat melakukan pengembangan:
1. **Duplicate before create**, sebelum membuat komponen baru pastikan untuk mengecek apa yang sudah ada untuk menghindari kondisi buat dari awal.
2. **FormIO is prime suspect before your code**, bug aneh? silakan cek bagian **known problem** dan [forum curhat](https://github.com/formio/formio.js/issues) terlebih dahulu.
3. **Refrain edit data from FormIO**, jika isi form nya kompleks dan terhubung dengan dashboard, maka gunakan query untuk lebih aman.
4. **Carefull when you delete component on edit form**, pastikan cek dua kali komponen lainnya sebelum menekan tombol save setelah menghapus komponen.
5. **Test form for playground**, berhubung tidak ada staging server #ehm, maka silakan pergunakan test form untuk bereksperimen.
5. **Test your form in klinik pintar page**, logika form di formio dan halaman klinik pintar beda dan umumnya di halaman klinik pintar lebih banyak bug nya jadi pastikan untuk tes disana.

---

## 6. Known Problem
Berikut daftar masalah yang teridentifikasi sebagai bug/anomaly/error aneh yang ditemukan dalam pengembangan:
1. Ketika edit data, data sebelumnya yang berada di komponen grid tidak ditampilkan dan jika tidak diisi ulang maka form akan mengupdate dengan nilai terbaru dari field edit data yang artinya kosong.
2. Validasi required masih diperiksa walau fieldnya hidden setelah di-embed di halaman klinik pintar.
3. Di versi terbaru dari yang sekarang, webhook memberikan error ketika dipanggil setelah proses submit setelah di-embed di halaman klinik pintar.
4. Di versi terbaru dari yang sekarang, komponen multiple select memberikan  error ketika dimasukan dalam komponen panel setelah di-embed di halaman klinik pintar.
5. Komponen number harus tetap diisi walau tidak required setelah di-embed di halaman klinik pintar.

Silakan tambahkan kesini jika menemukan bug/anomaly/error aneh terbaru dan tambahkan label **[Solved]** jika tidak pernah terjadi lagi atau ada pemberitahuan masalah tersebut telah diselesaikan.