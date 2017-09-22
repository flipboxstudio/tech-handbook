# Panduan Android Development (*MVVM Starter*)
Berikut merupakan panduan dalam mengembangkan proyek android menggunakan [MVVM Starter](https://github.com/flipboxstudio/mvvm-starter).
#### Konten:
1. Environment
2. Recommended Library
3. Packaging & Naming
4. App Flow
5. Git procedure
---
## 1. Environment
Default environment & utility tools:
- Android Studio
- Minimal versi sdk 18
- Target versi sdk 25
- Zeplin
- Marvel
---
## 2. Recommended Library
Selain default library yang digunakan di mvvm starter, [Kumpulan library](https://github.com/flipboxstudio/tech-handbook/blob/develop/android-recommended-library.md) berikut mungkin akan digunakan tergantung dari desain & kebutuhan proyek.

---

## 3. Packaging & naming
### Packaging
Berikut merupakan default package dalam mvvm starter.
```
Application file
data/
 - /events/
 - /local/
   - /contracts/
 - /remote/
   - /contracts/
   - /retrofit/
models/
utils/
 - /constants/
viewmodels/
 - /inputs/
 - /outputs/
view/
 - /activities/
 - /adapters/
 - /customviews/
 - /fragments/
```
Package yang digunakan terdiri dari 4 package utama yakni:
- **data**: berisi file yang berhubungan dengan proses pengambilan data (local/remote)
- **models**: berisi file model (custom object) yang digunakan dalam proyek.
- **utils**: berisi file utility penunjang proses.
- **viewmodels**: berisi file view model yang digunakan sebagai penunjang data binding dalam proyek.
- **view**: berisi file yang berhubungan dengan proses pengolahan, menampilkan data, & mengontrol alur aplikasi.

Terdapat beberapa sub package yang digunakan dan masing-masing memiliki fungsi tersendiri, yakni:
- **data/events**: berisi file yang digunakan sebagai event.
- **data/local/**: berisi file yang digunakan untuk mengakses konten storage local.
- **data/local/contracts/**: berisi file interface untuk mengakses storage local.
- **data/remote/**: berisi file yang digunakan untuk mengakses konten di storage remote/server.
- **data/remote/contracts/**: berisi file interface untuk mengakses storage remote/server.
- **data/remote/retrofit/**: berisi file retrofit untuk network utility.
- **utils/constants/**: berisi file yang menampung variable static untuk digunakan dalam proyek.
- **viewmodels/inputs/**: berisi file interface setter/input untuk view model.
- **viewmodels/outputs/**: berisi file interface getter/output untuk view model.
- **view/activities/**: berisi file activity yang digunakan dalam proyek.
- **view/adapters/**: berisi file adapter yang digunakan dalam proyek.
- **view/customviews/**: berisi file object view yang dikustomisasi untuk keperluan proyek.
- **view/fragments/**: berisi file fragment yang digunakan dalam proyek.

### Naming
Masing - masing package memiliki aturan dalam penamaan file yang ada didalamnya untuk memudahkan identifikasi & kegunaan, yakni:
- **data/**: `<Nama>DataManager.java` (ex: `SyncDataManager.java`.
- **data/events**: `<Nama>Event.java` (ex: `LoginSuccessEvent.java`).
- **data/local/**: `<Nama>Storage.java` (ex: `AddressStorage.java`).
- **data/local/contracts/**: `<Name>Contract.java` & penamaan metode crud ialah (Add, Get, Edit, Remove) (ex: `UserContract.java`).
- **data/remote/**: `<Nama>API.java` (ex: `AddressAPI.java`).
- **data/remote/contracts/**: `<Nama>Contract` & penamaan metode crud ialah (Create, Read, Update, Delete) (ex: `AddressContract.java`).
- **viewmodels/**: `<Nama>VM.java` (ex: `ProfileVM.java`).
- **viewmodels/inputs/**: `<Nama>Input.java` (ex: `OrderInput.java`).
- **viewmodels/outputs/**: `<Nama>Output.java` (ex: `OrderOutput.java`).
- **view/activities/**: `<Nama>Activity.java` (ex: `ProfileActivity.java`).
- **view/adapters/**: `<Nama Adapter><Nama Component>Adapter.java` (ex: `NewsListViewAdapter.java`).
- **view/customviews/**: `Custom<Nama>.java` (ex: `CustomTextView.java`).
- **view/fragments/**: `<Nama>Fragment.java` (ex: `LoginFragment.java`).

Selain itu, dalam proyek terdapat file resource, berikut aturan penamaan untuk masing-masing file di resource.
- **activity**: `activity_<Nama activity>.xml` (ex: `activity_profile.xml`).
- **fragment**: `fragment_<Nama Fragment>.xml` (ex: `fragment_login.xml`).
- **list item**: `cell_<Nama Layout>_<Nama Komponen>.xml` (ex: `cell_news_list.xml`).
- **menu**: `menu_<Nama Activity/Fragment>.xml` (ex: `menu_login.xml`).

Untuk kasus file yang tak punya aturan penamaan, by default mengikuti aturan penamaan `<Object><Predicate>.java/xml` atau default name yang diberikan.

Selain penamaan file, penamaan variable & method juga memiliki aturan yakni:
- **layout variable**: `<Komponen>_<Nama>` (ex: `tv_person_name`), menggunakan lower case & underscore sebagai pemisah kata.
- **class variable**: `<Komponen><Nama>` (ex: `tvPersonName`), menggunakan camelBack notation.
- **class method**: `<Predicate><Nama>` (ex: `getPersonName`), menggunakan camelBack notation.

Beberapa aturan lainnya yang perlu diperhatikan ialah:
- Menggunakan code style dari  [Flipbox](https://gist.github.com/sakadigital/41b4be80ab92234a48e0) (Automatic reformat & arrange code).
- Jika nama terlalu panjang, bisa menggunakan akronim (ex: textView = tv).
- Hindari nama yang kompleks & panjang.
---

## 4. App Flow
Hubungan alur dalam app yang saat ini digunakan.
![](https://i.imgur.com/XqBTXAU.png)

Selain itu, dalam mengembangkan produk terdapat beberapa aturan yang dianjurkan untuk dipatuhi, yakni:
**Visual**
  - Buat reusable component.
  - Kumpulkan warna/ukuran/kata dalam satu file (ex: values/colors.xml).

**Activity/Fragment**
  - Implementasi BaseMethod.java.
  - Paham & ikuti lifecycle.
  - Buat activity untuk flow placeholder (jika terasa gemuk silahkan pisahkan).
  - Tipe activity yang digunakan Fragments holder, ViewPager holder, & UI container.

**Model & ViewModel**
  - Representasi obyek dari properti dan logika bisnisnya.
  - Model dianjurkan berbentuk plain old java object (POJO).
  - Buat ViewModel untuk setiap model/fragment.

**View**
  - Gunakan two way data binding.
  - Gunakan designtime attributes.

**Constant**
  - File S.java untuk variable String yang nilainya mungkin akan berubah.
  - File I.java untuk variable konstan dalam Integer.
  - File K.java untuk variable konstant selain Integer (ex: Key value).
  - Gunakan String.format untuk kebutuhan format daripada operator "+".
---

## 5. Git procedure
Untuk meminimalisir terjadinya bug & memaksimalkan kualitas produk & code, dalam pengembangan proyek diimplementasikan **Merge/Pull Request** flow. Dalam flow ini terdapat tiga peran utama, yakni:
- **Captain**: Code reviewer & decision maker.
- **QA**: Feature/function reviewer.
- **Member**: Developer.

![](https://i.imgur.com/qNyLVwx.png)

Berikut merupakan aturan untuk penggunaan git dalam repositori proyek flipbox.
1. JANGAN MELAKUKAN PUSH ke `master` atau `develop`.
2. Jika Merge/Pull Request memiliki Conflict pada branch tujuan maka akan ditolak.
3. `hotfix` akan membuat Merge/Pull Request ke `master` dan `story`.
4. Untuk penamaan branch gunakan prefix : `story` , `task` , `bug` , `hotfix`
-- extra --
5. Untuk branch `story` yang besar harap dipecah menjadi beberapa branch `task` lalu merge ke `story` sebelum membuat merge ke `develop`
6. Captain harus merge di lokal. Tidak disarankan menggunakan web GUI. Hapus sumber branch di remote setelah merge.
7. Captain satu-satunya yang dapat memanajemen release. Captain bisa saja membuat branch `release` yang berisi permintaan tambahan ke developer sebelum di merge ke `develop` dan `master`.
