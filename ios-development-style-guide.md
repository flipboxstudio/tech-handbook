# Klinik Pintar iOS Development Style
proyek Klinik Pintar iOS ini menggunakan Arsitektur VIP (View Interactor Presenter) / Clean Swift

### Cara penggunaan
instal template dari [clean-swift.com](https://clean-swift.com/) setelah download template tersebut buka directory template di terminal dan `make install_templates` untuk instal template, untuk menghasilkan  `scene` baru : `New File` -> `iOS` -> `Clean Swift` -> `Scene` -> `Masukkan Nama Scene Anda`

### `Library` yang digunakan:
* Fabric
* Crashlytics
* One Signal
* Alamofire ( networking )
* AlamofireImage ( request image from server )
* ModelMapper ( mapping model )
* PKHUD ( Loading View )
* GooglePlaces
* GoogleMaps
* RxSwift
* RxCocoa

### `Product` yang sekarang ada :
* Klinik Pintar
* IHC Mobile 
* Pasien Pintar (soon)
* RSCM (soon)

## VIP
VIP adalah satu set Xcode Templates untuk menghasilkan komponen Clean Architecture.  
[Sedikit Tutorial tentang VIP (Outdated but worth it to try) ](https://clean-swift.com/clean-swift-ios-architecture/)

#### Key Points VIP Cycle

* `ViewController` menerima aktivitas pengguna, membuat objek permintaan, mengirimkannya ke `Interactor`.
* Interactor melakukan beberapa pekerjaan dengan `request`, membangun objek respon, dan mengirimkannya ke presenter.
* Presenter memformat data dari `response`, dan membangun `view model object` dan mengirimkan ke `ViewController`.
* `ViewController` menampilkan hasil yang ada di `ViewModel` ke pengguna.

![vip cycle](https://cdn-images-1.medium.com/max/2000/1*QV4nxWPd_sbGhoWO-X7PfQ.png)

## VIP Component

#### View Controller
* `ViewController` berisi `display logic`
* untuk bikin `scene` baru : `New File` -> `iOS` -> `Clean Swift` -> `Scene` -> `Input Scene Name`
* Terapkan `UIViewController` atau `Base__ViewController`
* Terapkan `UITableViewController`, `UICollectionViewController`, atau `UIWebViewController` jika dibutuhkan
* Terapkan `BaseFormViewController` untuk `scene` berbasis form
* Gunakan `xib`untuk views, gunakan `storyboard` sebagai routing/navigation.

#### Interactor

* `Interactor` berisi `Bussiness Logic`
* Gunakan `worker` jika dibutuhkan
* Menunggu permintaan dari `ViewController` dan mengirimkan respon ke `presenter`

#### Worker (Optional)
* berisikan async proses seperti parsing/fetching menggunakan API
* mengembalikan data berupa callback/Closures kepada Interactor untuk di proses ke presenter

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

# Unit Testing di VIP Arch

![](https://miro.medium.com/max/964/1*wfKeZOQ7Li8L1oBrCi810A.png) 

#### Key points

* Hal utama yang perlu di test adalah setiap protocol dari VIP (View -> Interactor -> Presenter)

#### Membuat Unit Tests

* Unit testing dapat dibuat dengan cara: File -> New -> File... -> Pilih Unit tests dari template swift
* ini akan menambah 4 komponen utama unit testing, ViewController, Interactor, Presenter, dan Worker
* Menggunakan TDD akan membantu, less debugging.

#### ViewControllerTests

* ViewControllerTests berisikan test yang akan dilakukan kepada interactor, sehingga anda harus melakukan spy terhadap protocol business logic yang ada di interactor

#### InteractorTests

* InteractorTests melalukan test untuk protocol presentation logic yang ada di presenter.
* Bila menggunakan worker kita perlu melalukan test terhadap worker tersebut, dan melakukan pengecekan apakah data yang didapat sesuai yang dibutuhkan.

#### WorkerTests

* WorkerTests, melakukan pengecekan apakah dikembalikan ke interactor atau tidak. gunakan inheritance untuk pengecekan tiap fungsi di worker

#### PresenterTests

* PresenterTests, disini melakukan spy terhadap displayLogic yang ada di View Controller

#### Bacaan tambahan untuk Untuk Testing : 
* [TDD](https://clean-swift.com/test-driven-development-using-clean-architecture-part-1/)
* [Unit Testing](https://medium.com/short-swift-stories/setup-of-a-clean-swift-pattern-helps-writing-unit-tests-6a4d02242e00)

# Catatan Tambahan
* [Mobile Dev Notes](https://dynalist.io/d/SucV2DBiqh6Gfy4U9HA_DuIG)


# Group

```
SupportedFile
Storyboards
CustomViews
Resource
Models
- Category
Scenes
- YourSceneName
Services
Data
Extensions
Singleton

```
| Nama Group | Deskripsi |
| ---------- | ----------- |
| SupportedFile | File config untuk setiap product |
| Storyboards | Berisi file storyboard |
| CustomViews | Berisi view yang dapat digunakan di setiap Scene/View Controller |
| Resource | Berisi file assets dan color serta fonts, taruh setiap warna yang sesuai untuk masing-masing product disini |
| Models | Berisi struktur data yang akan digunakan untuk manajemen data
| Scenes | Berisi VIP Components yang membangun `Scene` |
| Services | `Global Helper` yang tidak berhubungan dengan logika bisnis |
| Data | Berisikan logic local storage, dan setting untuk api request, serta enums |
| Extensions | Berisikan Global extension |
| Singletons | Berisikan Global functions |

# File Penting Bila Melakukan Reskin

```
ColorExtension.swift
FeatureManager.swift
```
| Nama File | Deskripsi |
| ---------- | ----------- |
| ColorExtension.swift | File yang mengatur warna untuk setiap product |
| FeatureManager | File yang mengatur feature dan flow untuk setiap product |
