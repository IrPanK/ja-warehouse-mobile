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
