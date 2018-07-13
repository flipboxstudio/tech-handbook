# Kolaborasi dan Review menggunakan *Pull Request*

Bagian ini berisi tentang proses _Pull Request_ yang berjalan di Flipbox, tata cara dan kesepakatan yang berlaku. 

---
### *Main Cast*

Dalam proses _Pull Request_ ini terdapat tiga peran utama, yakni:
- **Captain**: *Code reviewer & decision maker* (pengembang utama).
- **QA**: *Feature/function reviewer*.
- **Member**: *Developer* (pengembang).

![](https://i.imgur.com/qNyLVwx.png)

### *Pull Request Manifesto @ Flipbox*

1. Tidak boleh ada proses development di dalam *branch* `develop` atau `master` - kedua *branch* tersebut hanya berfungsi untuk `merge, test & release` fitur yang sudah stabil
2. Segera buat *Pull Request* setelah *branch* dibuat dan *remote push* sudah dilakukan.
3. *Pull Request* akan ditolak apabila ditemukan konflik dalam kode. Pengembang harus menyelesaikan konflik tersebut dan memastikan tidak ada konflik dalam *Pull Request*
4. Lakukan penamaan *branch* sesuai kesepakatan bersama ( lihat Ketentuan *Branching* )
5. *Branch* `hotfix` akan menghasilkan *Pull Request* ke *branch* `master` dan *branch* `develop`
7. Pengembang utama sebaiknya melakukan proses `merge` di repositori lokal. Khusus untuk branch `story` sebaiknya dilakukan *preserve commit history* dengan melakukan proses `git merge --no-ff`. Untuk branch lain silahkan `merge & squash` menggunakan `git merge --squash`
8. Pengembang utama yang memiliki akses *push* ke `master` dan `develop` harus mengatur proses `release` aplikasi dan memungkinkan untuk membuat *branch* `release` dengan beberapa permintaan pekerjaan tambahan sebelum akhirnya akan dilakukan `merge` ke `develop` dan `master`


### Ketentuan *Branching*

Pilihan nama *branch* yang dapat digunakan adalah

- **story**/[nomor redmine] [deskripsi]

>  Untuk *Story* yang dirasa terlalu besar, pecah ke dalam *Task* yang lebih kecil untuk kemudian di merge ke *branch* `story` sebelum melakukan *Pull Request* ke *branch* `develop`

- **task**/[nomor redmine] [deskripsi]
- **improvement**/[nomor redmine] [deskripsi]
- **bug**/[nomor redmine] [deskripsi]
- **hotfix**/[nomor redmine] [deskripsi]

**Notes**

Untuk repository yang tidak akan mengalami banyak pengembangan ( one and done ), harap menggunakan branching berikut

- **master**  : cukup jelas
- **develop** : hasil pengembangan dari branch `latest` akan di-merge kesini
- **latest** : seluruh pengembangan akan dilakukan di branch ini dan PR akan dibuat ke `develop`
 
### Konsep Git

- Gunakan pesan *commit* yang relevan dan masukkan *tag* yang sesuai. 
	- [ADD] deskripsi penambahan berkas yang dilakukan
	- [UPDATE] deskripsi *update* yang dilakukan
	- [FIX] deskripsi perbaikan yang dilakukan
- [Git Cheatsheet](https://www.git-tower.com/blog/git-cheat-sheet/)
- [Rewrite Commit History](https://git-scm.com/book/id/v2/Git-Tools-Rewriting-History)
- [Squash Published Commits](https://stackoverflow.com/questions/5667884/how-to-squash-commits-in-git-after-they-have-been-pushed)

