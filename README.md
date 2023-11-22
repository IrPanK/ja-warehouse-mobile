# Link API: https://irfan-kamil-tugas.pbp.cs.ui.ac.id/

# TUGAS 7

1.  Apa perbedaan utama antara stateless dan stateful widget dalam konteks pengembangan aplikasi Flutter?

    Perbedaan utamanya adalah pada mengelola dan merender perubahan data. Stateless widget tidak memiliki state yang dapat berubah setelah diinisialisasi sehingga akan merender widget yang sama setiap kali. Sedangkan Stateful widget memiliki state yang dapat berubah seiring waktu sehingga dapat merender ulang ketika state berubah.

2.  Sebutkan seluruh widget yang kamu gunakan untuk menyelesaikan tugas ini dan jelaskan fungsinya masing-masing.

    -   ShopCard. Untuk membuat card yang dapat ditekan dan akan menampilkan pesan SnackBar ketika ditekan
    -   MyHomePage. Mmerupakan halaman utama dari aplikasi, berisi daftar item yang akan ditampilkan dalam widget ShopCard
    -   MyApp. Widget utama yang menginisialisasi aplikasi Flutter
    -   Material. Memberikan latar belakang warna pada card
    -   InkWell. Memberikan area yang responsif terhadap sentuhan dan akan menampilkan SnackBar saat ditekan
    -   Container. Mengelola layout dalam card dan menjadi tempat untuk ikon dan text
    -   Scaffold. Kerangka utama halaman, termasuk AppBar dan konten halaman
    -   AppBar. Menampilkan judul aplikasi (seperti navbar)
    -   SingleChildScrollView. Scrollable widget yang memungkinkan kontennya discroll jika diperlukan
    -   GridView.count. Tata letak grid yang digunakan untuk menampilkan item secara terstruktur

3.  Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial)

    -   Inisiasi folder bernama ja_warehouse_mobile
    -   Jalankan `flutter create .`
    -   Buat menu.dart dan pindahkan (cut) kode `class MyHomePage` dan `class _MyHomePageState` dari main.dart ke menu.dart
    -   Tambahkan `import 'package:flutter/material.dart';` pada menu.dart
    -   Tambahkan `import 'package:ja_warehouse_mobile/menu.dart';` pada main.dart
    -   Ubah `MyHomePage` menjadi stateless widget
    -   Tambahkan class ShopItem di menu.dart dengan atribut name, icon, dan backgroundColor
    -   Tambahkan item yang merupakan ShopItem pada MyHomePage
    -   Ubah \_MyHomePageState build dengan item tadi yang akan merender ShopCard
    -   Buat stateless widget ShopCard yang merender card dan menampilkan snackbar pada saat di klik
    -   Atur nama, icon, dan backgroundColor card sesuai dengan item

---

# TUGAS 8

1. Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement(), disertai dengan contoh mengenai penggunaan kedua metode tersebut yang tepat!

    - Navigator.push(): Melakukan penambahan halaman baru ke stack navigasi, sehingga pengguna dapat kembali ke halaman sebelumnya. Metode ini digunakan jika ingin membuat user dapat kembali ke halaman sebelumnya (back).

    ```dart
        Navigator.push(context, MaterialPageRoute(builder: (context) => ItemFormPage()));
    ```

    - Navigator.pushReplacement(): Melakukan penggantian halaman saat ini dengan halaman yang baru, sehingga pengguna tidak dapat kembali ke halaman sebelumnya. Metode ini digunakan jika ingin membuat user tidak ingin ke halaman sebelumnya (redirect karena brute force routing).

    ```dart
        Navigator.pushReplacement(context, MaterialPageRoute(builder: (context) => ItemFormPage()));
    ```

2. Jelaskan masing-masing layout widget pada Flutter dan konteks penggunaannya masing-masing!

    - ShopCard: Sebagai button atau card untuk menunjukkan hal yang dapat dilakukan

    - LeftDrawer: Sebagai widget untuk menampilkan drawer

    - Drawer: Sebagai tempat drawer di sisi kiri halaman yang berupa menu/navigasi

    - Form: Sebagai wadah bagi beberapa input field widget

    - TextFormField: Menampilkan input teks

    - SingleChildScrollView: Membuat child widget di dalamnya menjadi scrollable jika melebihi ukuran layar

    - ElevatedButton: Tombol yang memiliki efek elevation ketika ditekan

    - AlertDialog: Menampilkan alert dialog atau seperti modal

3. Sebutkan apa saja elemen input pada form yang kamu pakai pada tugas kali ini dan jelaskan mengapa kamu menggunakan elemen input tersebut!

    - Menggunakan elemen TextFormField, karena elemen tersebut dapat didekorasi, diberi validasi, dan menerima string maupun integer, walaupun integer perlu di parse dahulu

4. Bagaimana penerapan clean architecture pada aplikasi Flutter?

    - Penerapannya dengan membagi-bagi kode ke folder/lapisan yang terpisah, setiap folder merepresentasikan fungsinya masing-masing. Untuk sekarang terdapat screens dimana untuk kode yang akan ditampilkan dan widgets untuk bagian kode yang berfungsi sebagai widget/elemen.

5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial)

    - Refaktor kode yang sudah ada. Awalnya hanya berisi main.dart dan menu.dart

    - Buat folder baru widgets dan screens pada folder lib

    - Cut kode tentang ShopCard pada menu.dart dan paste ke file baru shop_card.dart pada folder widgets (jangan lupa update import)

    - Pindahkan menu.dart ke folder screens (jangan lupa update import)

    - Menambah file left_drawer.dart pada widgets dan mengisinya dengan drawer yang bisa navigasi ke home atau item_form

    - Menambah file item_form.dart pada screens dan mengisinya dengan form yang memiliki input untuk nama, banyak barang, deskripsi, harga, dan kategori

    - Tambah left_drawer pada drawer

---

# TUGAS 9

1. Apakah bisa kita melakukan pengambilan data JSON tanpa membuat model terlebih dahulu? Jika iya, apakah hal tersebut lebih baik daripada membuat model sebelum melakukan pengambilan data JSON?

    Bisa, penggunaan fetching tanpa model (parsing dinamis) memiliki kekurangan dan kelebihannya sendiri. Kelebihannya adalah fleksibel dan kode menjadi lebih sederhana. Kekurangannya adalah ketidakpastian tipe data, error yang hanya muncul saat kode dieksekusi, dan sulit untuk didebug. Fetching tanpa model menurut saya lebih cocok jika dipakai untuk fetching API yang responsnya berstruktur dinamis dan sulit untuk dimodelkan. Tetapi untuk konteks tugas ini lebih baik menggunakan tahapan pembuatan model karena dapat menutupi kekurangan fetching tanpa model walaupun perlu tambahan kode yang cukup banyak. Selain itu, respons dari API tugas ini juga sudah ditetapkan atau konsisten.

2. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.

    CookieRequest digunakan untuk menyimpan cookie dan mengirim cookie ke server sehingga server dapat mengenali siapa yang mengirim request ke server. Instance CookieRequest perlu dibagikan ke semua komponen agar penggunaan cookie menjadi konsisten (hanya menggunakan cookie itu saja). Sehingga dapat memengaruhi UX dan clean code.

    UX: Tidak perlu login terus menerus karena cookie tersimpan dan bisa langsung dipakai untuk dikirim ke server

    clean code: Penggunaan kode yang terus menerus saat menggunakan cookie dan mengirim request ke server bisa dikurangin menjadi hanya satu bagian kode saja yang mendefinisikannya, sisanya hanya menggunakan

3. Jelaskan mekanisme pengambilan data dari JSON hingga dapat ditampilkan pada Flutter.

    - Mendapatkan respons dari API (membuat http request)

    - Pemrosesan respons menjadi JSON

    - Mengubah JSON menjadi model

    - Menampilkan data ke UI

4. Jelaskan mekanisme autentikasi dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.

    - Flutter menampilkan form untuk mengisi data login

    - Setelah data diinput dan menekan tombol login, flutter melakukan http request ke Django untuk login dengan data yang sudah diinput

    - Django akan melakukan proses login dan memberikan respons sesuai keberhasilan login

    - Jika berhasil login maka flutter akan melakukan navigasi ke menu

5. Sebutkan seluruh widget yang kamu pakai pada tugas ini dan jelaskan fungsinya masing-masing.

    - FutureBuilder: Menangani hasil dari suatu Future tanpa harus secara eksplisit menangani pengelolaannya. Future disini berguna untuk melakukan operasi asinkron dan salah satu contoh yang dipakai adalah melakukan request ke server

    - ListView: Menampilkan data secara berurutan

    - InkWell: Dapat menambahkan efek respons saat widget tersebut ditekan

    - SizedBox: Menentukan ukuran dari suatu ruang kosong

    - Text: Untuk menampilkan teks

    - Column: Untuk menyusun dan menampilkan child widget secara vertikal

    - ShopCard: Sebagai button atau card untuk menunjukkan hal yang dapat dilakukan

    - LeftDrawer: Sebagai widget untuk menampilkan drawer

    - Drawer: Sebagai tempat drawer di sisi kiri halaman yang berupa menu/navigasi

    - Form: Sebagai wadah bagi beberapa input field widget

    - TextFormField: Menampilkan input teks

    - SingleChildScrollView: Membuat child widget di dalamnya menjadi scrollable jika melebihi ukuran layar

    - ElevatedButton: Tombol yang memiliki efek elevation ketika ditekan

    - AlertDialog: Menampilkan alert dialog atau seperti modal

6. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).

    - Mengubah aplikasi Django, seperti menambah django-app authentication untuk melakukan autentikasi dan menambah view untuk melakukan proses penambahan data

    - Install package provider dan pbp_django_auth

    - Membuat objek Provider yang membagikan instance CookieRequest ke semua komponen

    - Membuat halaman login yang meminta input username & password, dan akan melakukan request ke url auth/login/ untuk proses autentikasi

    - Membuat model item sebagai pemrosesan respons server agar dapat ditampilkan ke UI dan pemrosesan data input untuk melakukan request ke server

    - Membuat halaman item list untuk menampilkan semua item yang ada (fetch ke server). Tiap item hanya menampilkan name, amount, dan description. Jika dipencet maka akan redirect ke halaman item detail

    - Membuat halaman item detail untuk menampilan semua attribut item (fetch ke server)

    - Melakukan routing pada left drawer dan menu ke item list

    - Integrasi item form dengan API untuk menambahkan data ke server

    - Melakukan aksi logout jika menu logout ditekan
