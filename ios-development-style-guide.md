# vip-starter
sebuah proyek iOS menggunakan Arsitektur VIP (View Interactor Presenter)

### Cara penggunaan
instal template dari [clean-swift.com](https://clean-swift.com/) setelah download template tersebut buka directory template di terminal dan `make install_templates` untuk instal template, untuk menghasilkan  `scene` baru : `New File` -> `iOS` -> `Clean Swift` -> `Scene` -> `Masukkan Nama Scene Anda`

### `Library` yang digunakan:
* Fabric
* Crashlytics

* Alamofire ( networking )
* AlamofireImage ( request image from server )
* ModelMapper ( mapping model )
* PKHUD ( Loading View )

## VIP
VIP adalah satu set Xcode Templates untuk menghasilkan komponen Clean Architecture.

#### Key Points VIP Cycle

* `ViewController` menerima aktivitas pengguna, membuat objek permintaan, mengirimkannya ke `Interactor`.
* Interactor melakukan beberapa pekerjaan dengan `request`, membangun objek respon, dan mengirimkannya ke presenter.
* Presenter memformat data dari `response`, dan membangun `view model object` dan mengirimkan ke `ViewController`.
* `ViewController` menampilkan hasil yang ada di `ViewModel` ke pengguna.

![vip cycle](https://cdn-images-1.medium.com/max/2000/1*QV4nxWPd_sbGhoWO-X7PfQ.png)

## VIP Component

#### View Controller
* ViewController containts display logic
* `ViewController` berisi `display logic`
* untuk bikin `scene` baru : `New File` -> `iOS` -> `Clean Swift` -> `Scene` -> `Input Scene Name`
* Terapkan `UIViewController` atau `Base__ViewController`
* Terapkan `UITableViewController`, `UICollectionViewController`, atau `UIWebViewController` jika dibutuhkan
* Terapkan `BaseFormViewController` untuk `scene` berbasis form
* Gunakan `xib`, jangan menggunakan  `storyboard`.

#### Interactor

* `Interactor` berisi `Bussiness Logic`
* Gunakan `worker` jika dibutuhkan
* Menunggu permintaan dari `ViewController` dan mengirimkan respon ke `presenter`

#### Presenter

* Berisi `ViewLogic`
* Memformat ulang data dari `interactor` dan mengirimkan ke `ViewController`.

#### View

* Gunakan `xib` atau `by code`
* Jangan menaruh `bussiness logic` disini

#### Model

* Representasi dari objek dengan propertinya
* Gunakan `ModelMapper`

#### Router

* Mengarahkan ke `scene` berikutnya
* Mengirim data ke `ViewController` lain

# Group dan Penamaan

```
[Optional] Core
- Assets.xcassets
- LaunchScreen.storyboard
- AppDelegate.swift
Base
Models
Scenes
- YourSceneName
Services
Worker
```
| Nama Group | Deskripsi |
| ---------- | ----------- |
| Core | File inti dari proyek xcode seperti `Assets.xcassets`, `LaunchScreen.storyboard`, `AppDelegate.swift` |
| Base | Kelas dasar, yang berguna untuk meminimalkan kode |
| Models | Berisi struktur data yang akan digunakan untuk manajemen data |
| Scenes | Berisi VIP Components yang membangun `Scene` |
| Services | `Global Helper` yang tidak berhubungan dengan logika bisnis |
| Worker | `Global Helper` spesifik untuk logika bisnis |
```
