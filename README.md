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
