\#  📄 Dokumentasi Projek: Aplikasi Manajemen Keuangan Pribadi



\## 1. Deskripsi Projek

Aplikasi ini dikembangkan untuk mencatat, melacak, dan mengelola arus kas keuangan pribadi secara terstruktur. Sistem difokuskan pada kemudahan penggunaan sehari-hari dengan menyajikan rekap saldo otomatis serta dasbor riwayat transaksi yang profesional.



\##  2. Tumpukan Teknologi (\*Tech Stack\*)

\*   \*\*Database Terpusat:\*\* Google Sheets

\*   \*\*Platform Aplikasi (Antarmuka \& Logika):\*\* Google AppSheet

\*   \*\*Sistem Logika Visual:\*\* AppSheet \*Format Rules\* (Tanpa skrip eksternal)



\## 3. Fitur Utama

\*   \*\*Manajemen Arus Kas Dinamis:\*\* Sistem pencatatan pemasukan dan pengeluaran yang dilengkapi dengan label/kategori transaksi yang dapat dikustomisasi.

\*   \*\*Dasbor Pemantauan Finansial:\*\* Tampilan halaman utama yang merangkum total kekayaan pengguna saat ini, kalkulasi rekap saldo, dan daftar riwayat aktivitas keuangan.

\*   \*\*Akses Entri Cepat:\*\* Konfigurasi tombol aksi (\*action buttons\*) yang diposisikan langsung di dasbor utama, sehingga entri data transaksi baru dapat dieksekusi seketika tanpa navigasi halaman tambahan.



\## 4. Implementasi Teknis \& Catatan Keputusan (\*ADR\*)



\### 4.1. Sistem Pewarnaan Indikator Transaksi

\*\*Latar Belakang:\*\* Dibutuhkan sistem pembeda visual antara uang masuk dan uang keluar agar mutasi keuangan mudah dibaca sekilas.



\*\*Keputusan Teknis:\*\* Meskipun awalnya dipertimbangkan menggunakan Google Apps Script, keputusan akhir diterapkan dengan menggunakan fitur \*\*Format Rules\*\* bawaan AppSheet. Hal ini bertujuan untuk menjaga aplikasi tetap ringan, menghindari pembatasan limit kuota dari Apps Script, dan menyederhanakan konfigurasi.



\*\*Langkah Konfigurasi Pewarnaan:\*\*

1\.  Buka panel \*Format Rules\* di dalam editor AppSheet.

2\.  Tentukan logika evaluasi pada pengaturan \*\*"If this condition is true"\*\*.

3\.  Terapkan aturan warna berdasarkan logika kondisi:

&#x20;   \*   🟢 \*\*Warna Hijau:\*\* Untuk baris atau nominal transaksi Pemasukan.

&#x20;   \*   🔴 \*\*Warna Merah:\*\* Untuk baris atau nominal transaksi Pengeluaran.

4\.  Petakan ke kolom mana warna ini akan diterapkan melalui pengaturan \*\*"Format these columns and actions"\*\*.



\### 5. Panduan Pemecahan Masalah (\*Troubleshooting\*)

\*   \*\*Warna Transaksi Tidak Muncul/Error:\*\*

&#x20;   Pastikan nama kolom yang dipanggil di dalam formula \*Format Rules\* AppSheet sudah \*\*sama persis\*\* dengan nama \*header\* kolom yang berada di database Google Sheets. Ketidakcocokan satu karakter pun akan membatalkan pe-render-an warna.

\*   \*\*Pengembangan Lanjutan:\*\*

&#x20;   Metode logika \*Format Rules\* di atas juga dapat diduplikasi dan diubah kondisinya untuk fitur pelacakan lain di kemudian hari, misalnya: menyoroti transaksi dengan nominal yang sangat besar atau menandai batas tanggal jatuh tempo pembayaran cicilan.

