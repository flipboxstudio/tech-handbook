# Panduan dan konsep dasar Programming

Bagian ini berisi rangkuman dan referensi dasar dasar pemrograman yang wajib dipahami oleh seluruh tim teknis Klinik Pintar.

---
### Konsep Clean Code

Konsep *Clean Code* mempunyai beberapa penafsiran dan karakteristik, di antaranya :

- **Kode tersebut harus mudah dipahami**
	- Memiliki alur kerja/pertukaran data yang jelas dan konsisten
	- Kolaborasi antar *class* atau berkas harus mudah dipahami
	- Tanggung jawab dan fungsi dari setiap berkas harus mudah untuk dipahami. Jangan membuat fungsi yang terlalu kompleks apabila tidak dibutuhkan.
	- Fungsi atau *method* yang ada di dalam sebuah berkas harus mudah dipahami
	- Tujuan, penamaan dan fungsi dari setiap variabel ataupun baris mudah dipahami dan mudah dibaca
	- Kode harus mudah dibaca, tambahkan komentar di bagian yang cukup kompleks atau kurang stabil (lihat bagian *readable code*)
	
- **Kode tersebut harus mudah diubah**
	- Kelas dan fungsinya harus dijaga agar tetap kecil dan bertanggung jawab pada sebuah pekerjaan tertentu (*single responsibility principle*)
	- Kelas harus memiliki API yang jelas dan mudah dipahami / mudah dibaca
	- Kelas dan fungsinya harus berjalan dengan sebagai mana mustinya dan proses yang ada di dalamnya mudah untuk ditebak
	- Mempunyai *unit test* atau diatur sedemikian rupa agar memudahkan pembuatan tes.
	- Tes yang tersedia mudah dipahami dan mudah untuk diubah
	- Redundansi kode harus dijaga seminimal mungkin (*DRY principle*) agar kode dapat tetap berjalan dengan konsisten ketika terjadi perubahan di suatu tempat
	- Dependensi yang ada di dalam kode harus dijaga seminimal mungkin untuk mengurangi resiko kesalahan akibat perubahan dependensi


> "Clean Code is a code that is written by someone who cares" - **Michael Feathers**

Bacaan tambahan :

[Clean Code : A Handbook of Agile Software Craftmanship](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)

[High Quality Code for Better Programmer](https://www.butterfly.com.au/blog/website-development/clean-high-quality-code-a-guide-on-how-to-become-a-better-programmer)

[Clean Code for Javascript](https://github.com/ryanmcdermott/clean-code-javascript)


---
### Konsep Readable Code

Hal yang cukup sering dilupakan pengembang adalah bahwa kode yang mereka kembangkan akan digunakan kembali suatu hari nanti, mungkin oleh orang lain. Banyak kasus muncul ketika kode lama dibuka kembali, dibutuhkan waktu untuk memahami ataupun mengingat ulang bagaimana kode tersebut dibuat. Waktu tersebut dapat diminimalisir apabila kode yang dibuat mudah untuk dibaca dan dipahami. 

Prinsip prinsip untuk membuat kode yang mudah dibaca adalah :

- Konsistensi dalam tata cara pembuatan kode, di antaranya :
	- Spasi vs tab
	- Peletakan { }
	- Ikuti kesepakatan yang berlaku di dalam tim
- Penamaan *files & folders* yang konsisten :
	- Peletakan berkas di dalam *folder* yang relevan dan mudah dipahami
	- Konvensi penamaan (CamelCase, snake-case, etc)
	- Ikuti kesepakatan yang berlaku di dalam tim
- Masukkan komentar dan dokumentasi di tempat yang membutuhkan penjelasan tambahan
- Hindari pembuatan fungsi / baris yang kompleks dan membutuhkan waktu tambahan untuk dipahami.
- Hindari spasi / tab yang terlalu menjorok (*deep nesting*) karena akan menyulitkan pemahaman fungsi dan tujuan kode

> "Always code as if the person who ends up maintaining your code is a violent psychopath who knows where you live. Code for readability" - **John F Woods**

Bacaan lebih lanjut :

[The Art of Readable Code](https://www.amazon.com/Art-Readable-Code-Practical-Techniques/dp/0596802293)

[Write Elegant Code](https://code.tutsplus.com/articles/writing-elegant-and-readable-code--mobile-21514)

[Write Cleaner Code](https://www.codeschool.com/blog/2015/09/29/10-ways-to-write-cleaner-code/)

---
### Konsep SOLID, KISS & DRY


**KISS** :  Keep It Simple and Straightforward!

Konsep KISS menyatakan bahwa kode yang dibuat harus sederhana dan mudah dipahami tanpa mengorbankan kualitas hasil akhir pengerjaan kode.

Beberapa hal yang harus diperhatikan dalam penerapan konsep KISS adalah :

- *methods & classes* harus dibuat sesederhana mungkin.
- Hindari kompleksitas dalam kondisi perulangan dan percabangan (*nested/complex loop & conditional*)
- Hindari solusi yang terlalu kompleks atau kode yang terlalu singkat namun sulit untuk dibaca. Jangan pula mengorbankan performa demi mendapatkan baris kode yang mudah dibaca. Cari keseimbangan antara keduanya.

**DRY** : Don’t Repeat Yourself!

Apabila sebuah blok kode sudah digunakan beberapa kali ( +- 3 kali ) dalam sebuah proyek, buatlah *reusable/helper method* dan hapus duplikasi yang terjadi.

**SOLID**

- **Single responsibility** : Sebuah *class* hanya boleh memiliki 1 tanggung jawab. Jangan membuat sebuah *class* yang terlalu kompleks dan melakukan banyak hal sekaligus.
> **Contoh** : sebuah layanan ojek online mungkin bisa membuat kelas `AntarJemput` untuk memodelkan proses bisnisnya. Namun akan lebih baik apabila kelas tersebut dipecah menjadi `Antar` yang bertanggung jawab dengan pengantaran pengguna menuju tujuan dan `Jemput` yang bertanggung jawab untuk fungsi penjemputan pengguna dari tempat asal sehingga apabila ada optimalisasi dalam proses `Jemput` , fungsi yang mengimplementasi kelas `Antar` menjadi relatif lebih aman

- **Open for extension but closed for modification** : Fungsi atau kegunaan dalam sebuah entitas seharusnya bisa ditambahkan tanpa harus mengubah isi dari entitas tersebut ( *Open Closed* )
> Contoh : sebuah `Truk` memiliki fungsi `jumlahVolumeBarang` yang memiliki parameter *List* barang barang yang ada di dalam `Truk` tersebut. Fungsi `jumlahVolumeBarang` bertugas untuk menghitung volume masing masing barang kemudian menjumlahkan keseluruhan volume. Apabila terdapat jenis barang baru dengan rumus volume baru, maka `jumlahVolumeBarang` harus diperbarui. Seharusnya ada implementasi `hitungVolume` di dalam barang sehingga untuk barang tertipe apapun, `jumlahVolumeBarang` tidak harus diperbarui karena hanya akan menjumlahkan hasil dari `barang.hitungVolume()`

- **Liskov substitution principles** : Sebuah *object* seharusnya dapat diganti oleh *object subtype* tanpa mengubah keluaran dari sebuah program ( *Design by Contract* )
> Contoh : sebuah fungsi `antarPenumpang` memiliki parameter *Kendaraan* yang memiliki fungsi `rem`. *Liskov subtitution* menyatakan bahwa semua jenis *Kendaraan* (`Odong Odong`, `Bemo`)harus mengimplementasikan `rem` dengan tujuan yang sama ( menurunkan kecepatan ).

- **Interface segregation principles** : *Interface* yang spesifik dan kecil lebih baik daripada *Interface* besar yang menyebabkan *class* harus menerapkan fungsi yang tidak dibutuhkan.

- **Dependency inversion principle** : Detail harusnya bergantung pada abstraksi. Seharusnya tidak ada *class* yang bergantung / *depend* dari *class* yang konkrit ( *non abstract* )
> **Contoh** : Fungsi `antarPenumpang` dalam kelas `Antar` mungkin bisa memiliki parameter/dependensi `Sepeda Motor`. Namun apabila layanan ojek online ingin menambahkan `Bemo` di armadanya tentu harus mengubah isi dari `Antar`. Akan lebih baik apabila parameter dari `antarPenumpang` diubah menjadi `Kendaraan` (*abstract*) sehingga memungkin adanya penambahan tipe armada tanpa harus mengubah fungsi / kelas terkait. 


Bacaan lebih lanjut :

[SOLID : Object Oriented Design](https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)

[SOLID, GRASP and other principles of OOP](https://dzone.com/articles/solid-grasp-and-other-basic-principles-of-object-o)

---
### Konsep OOP

Beberapa konsep utama yang harus dipahami dari sebuah paradigma OOP ( *Object Oriented Programming* ) adalah :

**Everything is an object**

Banyak pihak yang menyebutkan bahwa dalam OOP, semua hal bisa direpresentasikan sebagai `Object`. Hal ini bisa mungkin tidak bisa diimplementasikan dalam beberapa situasi/konsep tertentu ( *primitive variables*, *methods*, etc ). Namun perlu dipahami bahwa dalam pemodelan solusi, hampir sebagian besar masalah dan solusinya dapat direpresentasikan sebagai kumpulan objek yang saling berinteraksi satu sama lain. Oleh karena itu, kemampuan memodelkan masalah menjadi objek dan representasinya menjadi sangat penting dalam pemahaman OOP.

**Encapsulation**

Enkapsulasi menyatakan bahwa implementasi/representasi internal dari sebuah objek seharusnya tidak bisa terlihat dari objek lain.

Enkapsulasi bisa dilakukan dengan cara melakukan pembatasan akses terhadap *accessor* dan *mutator*. ***Accessor*** merupakan sebuah fungsi yang dapat memberikan nilai yang terkandung di sebuah objek. ***Mutator*** adalah sebuah fungsi yang dapat mengubah representasi/nilai internal yang terkandung di dalam sebuah objek.

> **Contoh** : objek `Person` bisa mempunyai *Accessor* `getClothes()` dan *Mutator* `setClothes(...)` untuk mencari tahu dan mengubah pakain yang sedang dikenakannya

**Abstraction**

Abstraksi berhubungan erat dengan enkapsulasi, karena pada dasarnya abstraksi adalah proses pembuatan sebuah objek yang tidak memiliki implementasi nyata dalam *Accessor* ataupun *Mutator* yang dimilikinya. Implementasi tersebut akan diterapkan pada objek yang merepresentasikannya

> **Contoh** : objek `Manusia` memiliki *Accessor* `bisaMembaca` , namun implementasi `bisaMembaca` akan berbeda tergantung objek lain yang merepresentasikan `Manusia`. Budi mungkin `bisaMembaca` ( mengembalikan `true` ) namun Joko bisa saja tidak `bisaMembaca` ( mengembalikan `false` )

**Inheritance**

Secara umum, objek dapat berinteraksi satu dengan yang lainnya dalam hubungan mempunyai (*has a*), menggunakan (*use a*), atau merepresentasikan (*is a*). *Is a* atau representasi adalah sebuah bentuk dari *Interitance* atau pewarisan. Dalam konsep *Inheritance* terdapat istilah *parent/super class* dan *child class*. *Child class* akan mewarisi properti dan fungsi non-privat yang dimiliki oleh *parent/super class*.

> **Contoh** : Kelas `Kendaraan` memiliki properti `roda` dan fungsi `aturKecepatan`. Semua kelas yang menjadi *child class* dari `Kendaraan` akan memiliki `roda` dan fungsi `aturKecepatan` secara otomatis. 

**Polymorphism**

*Polymorphism* bisa dijabarkan atau diartikan sebagai sebuah operasi yang memiliki beberapa jenis implementasi

Beberapa jenis *Polymorphism* adalah :

- *Ad Hoc Polymorphism* atau *Function Overloading* adalah sebuah fungsi yang memiliki nama sama, namun parameter berbeda sehingga bisa memiliki implementasi yang berbeda
> Contoh : fungsi dengan `jumlah` bisa memiliki parameter `angka arab (1-0)` ataupun `angka romawi (I-X)` sehingga implementasi `jumlah(10, 20)` tentunya akan menjadi beda dengan `jumlah (XV, IV)`

- *Parametric Polymorphism* atau *Generic Type* adalah sebuah fungsi atau jenis data yang ditulis secara umum sehingga bisa mengakomodir semua jenis tipe data tanpa terkecuali
> Contoh : kelas `Minuman<T>` dan fungsi `racikMinuman(T)` mempunyai *Generic Type* yang direpresentasikan dalam `T`. Dalam proses representasi `Minuman`, `T` dapat didefinisikan sebagai data berjenis apapun (misal `Kopi` atau `Teh`) dan `racikMinuman` harus menggunakan tipe data yang sama sebagai parameter ( menjadi `racikMinuman(Kopi)` atau `racikMinuman(Teh)`.

- *Subtyping* atau *Function Overriding* adalah sebuah fungsi yang diwariskan dari *parent class* namun dapat didefinisikan berbeda oleh *child class*
> Contoh : kelas `Binatang` mempunyai fungsi `bicara`, namun kelas yang merepresentasikan `Binatang` mungkin mempunyai cara yang berbeda untuk `bicara` ( misalkan `Kucing` `bicara` akan mengembalikan *Meow!* dan `Anjing` `bicara` akan mengembalikan *Woof!* )


Bacaan tambahan ( gunakan akun Klinik Pintar untuk akses Udemy *course* ) :

[Design Pattern Guide](https://www.udemy.com/draft/725258/learn/v4/content)

[OOP on Wikipedia](https://en.wikipedia.org/wiki/Object-oriented_programming)

---
### Konsep Reactive Programming

Beberapa konsep utama yang harus dipahami dari sebuah paradigma *Reactive Programming* adalah :

**Everything is a stream**

Sedikit berbeda dengan konsep OOP yang menggambarkan masalah dan solusinya sebagai objek dan interaksinya, *Reactive Programming* menitikberatkan kepada kejadian dan alur kejadiannya (*stream & events*). Hampir sebagian besar proses dapat digambarkan dalam kumpulan kejadian (*events*) dan alur kejadian dari mulai sampai selesai (*stream*)

Karena perbedaan paradigma ini, *Reactive Programming* sangat cocok apabila diterapkan ke dalam sebuah sistem yang membutuhkan respon secara instan / *real time* karena paradigma ini sangat menitikberatkan kepada kejadian (*event*) dan reaksinya (*response*).

**Subject / Observable**

*Stream* dapat diimplementasikan dengan menginisialisasi sebuah *Subject* (bisa juga disebut *Observable*). *Observable* adalah sebuah objek/data yang dapat dipantau (*observe/subscribed*) oleh sebuah *Observer*. Setiap perubahan dari status data akan langsung diinformasikan kepada seluruh *Observer* yang memantau data *Observable* tersebut.

**Observer**

*Observer* adalah sebuah objek/data yang memantau semua perubahan nilai dari *Subject/Observable*. Setelah *Observer* menyatakan diri siap memantau (*subscribe*) *Observable*, maka *Observer* tersebut sudah memasuki *stream data* yang ada di dalam proses. Setiap ada perubahan status internal di dalam *Subject/Observable* maka *Observer* akan mendapatkan notifikasi sehingga dapat melakukan reaksi yang bersesuaian dengan aksi.

Bacaan lebih lanjut :

[Reactive Programming Introduction](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754)

[ReactiveX](http://reactivex.io/)

---

