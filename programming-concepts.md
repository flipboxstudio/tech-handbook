# Panduan dan konsep dasar Programming

Bagian ini berisi rangkuman dan referensi dasar dasar pemrograman yang wajib dipahami oleh seluruh tim teknis Flipbox.

---
### Konsep Clean Code

Focused

Clear & concise

Readable

Minimal dependencies

Have unit & acceptance test

No redundancy


> "Clean Code is a code that is written by someone who cares" - **Michael Feathers**

Bacaan lebih lanjut :

[TBA](wa.com)

---
### Konsep Readable Code

Comment & Documentation when needed

Consistent style

Consistent naming scheme

Avoid deep nesting

Meaningful file & folder organization

> "Always code as if the person who ends up maintaining your code is a violent psychopath who knows where you live. Code for readability" - **John F Woods**

Bacaan lebih lanjut :

[TBA](https://blog.codinghorror.com/coding-for-violent-psychopaths/)

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
> Contoh :

- **Open for extension but closed for modification** : Fungsi atau kegunaan dalam sebuah entitas seharusnya bisa ditambahkan tanpa harus mengubah isi dari entitas tersebut
> Contoh :

- **Liskov substitution principles** : Sebuah *object* seharusnya dapat diganti oleh *object subtype* tanpa mengubah keluaran dari sebuah program
> Contoh :

- **Interface segregation principles** : *Interface* yang spesifik dan kecil lebih baik daripada *Interface* besar yang menyebabkan *class* harus menerapkan fungsi yang tidak dibutuhkan.
> Contoh :

- **Dependency inversion principle** : Detail harusnya bergantung pada abstraksi. Seharusnya tidak ada *class* yang diturunkan / *derived* dari *class* yang konkrit ( *non abstract* )
> Contoh :


Bacaan lebih lanjut :

[TBA](wa.com)

---
### Konsep OOP

Beberapa konsep utama yang harus dipahami dari sebuah paradigma OOP ( *Object Oriented Programming* ) adalah :

**Everything is an object**

**Encapsulation**

**Abstraction**

**Inheritance**

**Polymorphism**

**Generics**


Bacaan tambahan ( gunakan akun Flipbox untuk akses Udemy *course* ) :

[Design Pattern Guide](https://www.udemy.com/draft/725258/learn/v4/content)

[TBA](http://codebetter.com/raymondlewallen/2005/07/19/4-major-principles-of-object-oriented-programming/)

---
### Konsep Reactive Programming

Beberapa konsep utama yang harus dipahami dari sebuah paradigma *Reactive Programming* adalah :

**Everything is a stream**

**Observer & Observable**

**Subscriber**

Bacaan lebih lanjut :

[TBA](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754)

---

