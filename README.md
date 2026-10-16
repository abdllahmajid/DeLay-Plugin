# DeLay Plugin — Panduan Pengguna

Plugin Photoshop untuk alur kerja **sablon (screen printing)**: membuat channel warna, memasang tanda register, membuat halftone, dan menyusun beberapa film dalam satu lembar supaya hemat kertas.

Gratis. Berjalan di **Mac** dan **Windows**.

---

## 1. Syarat

- Adobe Photoshop **2022 (versi 23.3) atau lebih baru**
- Aplikasi **Creative Cloud Desktop** sudah terpasang dan Anda sudah login
- Mac atau Windows

## 2. Cara memasang

1. Unduh file plugin berekstensi **`.ccx`**.
2. Tutup Photoshop kalau sedang terbuka.
3. **Klik dua kali** file `.ccx`. Aplikasi Creative Cloud Desktop akan terbuka dan memulai pemasangan.
4. Akan muncul peringatan bahwa plugin **belum diverifikasi oleh Adobe**. Ini wajar: plugin ini dibagikan langsung oleh pembuatnya, bukan lewat Adobe Marketplace. Lanjutkan pemasangan hanya kalau file diunduh dari sumber resmi pembuat.
5. Buka Photoshop, lalu pilih menu **Plugins → DeLay Plugin**. Panel akan muncul.

Kalau panel tidak muncul di menu Plugins, cek bagian *Masalah umum* di bawah.

## 3. Isi panel

Semua tombol ada di kategori **Sablon**. Klik tombol untuk menjalankan, dan dialog pengaturan akan tampil.

### Buat Channel Kaos
Membuat **spot color channel** bernama "Kaos" dengan warna pilihan Anda dan solidity 100%.

1. Buka file desain (mode RGB atau CMYK).
2. Klik tombolnya, lalu pilih warna di color picker dan klik OK.

Tidak bisa dipakai untuk dokumen bermode Bitmap atau Indexed Color.

### Auto Register Spot
Memasang **tanda register** (bullseye di pojok, tanda silang di tengah) di strip atas dan bawah **setiap channel**, lengkap dengan nama channel. Setelah itu canvas disesuaikan ke ukuran kertas final.

1. Buka dokumen yang sudah punya spot channel.
2. Klik tombolnya, lalu pilih ukuran kertas (A4, F4, A3, A3+, atau isi sendiri). Tombol ⇄ menukar orientasi.
3. Centang atau kosongkan opsi **Watermark (Branding Nama)** sesuai kebutuhan.
4. Klik **Buat Register**.

> Script ini **mengubah dokumen yang sedang aktif**. Simpan salinan dulu sebelum menjalankannya.
> Ukuran canvas diubah tanpa skala. Kalau kertas lebih kecil dari desain beserta register, bagian yang berlebih akan terpotong.

### Auto Raster Studio
Mengubah channel yang Anda centang menjadi **halftone (titik raster)**.

1. Buka dokumen dengan channel warna.
2. Isi **resolusi output** (default 300 ppi).
3. Centang channel yang mau di-raster, lalu atur **LPI**, **sudut**, dan **bentuk titik** (Round, Ellipse, Diamond, Line) untuk masing-masing. Sudut dan bentuk sudah terisi default untuk channel CMYK.
4. Klik **PROCESS**.

Hasilnya dokumen baru bernama `HASIL_RASTER_xxxxxx` dengan mode yang sama seperti dokumen asli. Channel asli seperti RGB atau CMYK tetap utuh, dan hanya channel yang Anda centang yang diganti hasil raster. Dokumen asli tidak diubah.

Di dokumen RGB, channel Red, Green, dan Blue tidak dicentang secara default.

### Layout Film Hemat Kertas
Menyusun **beberapa film (channel)** dalam **satu lembar** kertas supaya sisa kertas kosong terpakai. Kalau satu lembar tidak cukup, otomatis dibuat lembar ke-2, ke-3, dan seterusnya.

1. Buka dokumen yang channel dan register-nya sudah jadi. Kalau ada beberapa dokumen terbuka, channel dari semuanya muncul di daftar.
2. Klik tombolnya, lalu pilih channel yang mau disusun. Channel di dokumen aktif sudah terpilih otomatis. Gunakan Ctrl atau Shift + klik untuk memilih beberapa.
3. Pilih ukuran kertas cetak film. Atur jarak antar film dan jarak tepi kertas. Isi tepi kertas sesuai area yang tidak bisa dicetak oleh printer Anda.
4. Opsi:
   - **Pilih orientasi kertas otomatis**: mencoba portrait dan landscape, lalu memilih yang paling hemat.
   - **Boleh memutar film 90°**: lebih hemat, tetapi film yang diputar harus diputar kembali saat dipasang di screen.
   - **Garis potong tipis**: garis hairline di sekeliling tiap film untuk memandu pemotongan.
5. Klik **Susun Layout**.

Hasilnya dokumen baru bernama `Layout_Film_1_dari_N`. Setiap film berada di layer sendiri sehingga posisinya masih bisa digeser. Di akhir proses muncul ringkasan jumlah lembar yang dihemat.

Hal yang perlu diketahui:
- Script mengasumsikan film **hitam di atas putih** (hitam = tinta). Kalau film Anda terbalik, akan muncul peringatan.
- Seleksi yang sedang aktif di dokumen akan hilang.
- Dokumen asli tidak diubah isinya.

**Contoh alur kerja:** siapkan channel warna → Auto Register Spot → Layout Film Hemat Kertas → cetak. Auto Raster Studio dipakai kalau desain butuh efek halftone.

## 4. Memperbarui plugin

Unduh file `.ccx` versi terbaru dan pasang dengan cara yang sama seperti langkah pemasangan di atas.

## 5. Mencopot plugin

Di Photoshop, buka **Plugins → Manage Plugins...** (membuka Creative Cloud Desktop), pilih DeLay Plugin, lalu uninstall. Nama menu bisa sedikit berbeda antar versi Photoshop.

## 6. Masalah umum

**Panel tidak ada di menu Plugins.**
Pastikan Photoshop Anda versi 23.3 atau lebih baru dan pemasangan lewat Creative Cloud Desktop sudah selesai. Tutup lalu buka kembali Photoshop.

**Tombol diklik tapi tidak terjadi apa-apa.**
Pastikan ada dokumen yang terbuka di Photoshop. Dialog kadang muncul di belakang jendela lain, jadi cek juga jendela Photoshop yang tersembunyi. Kalau masih bermasalah, tutup lalu buka kembali Photoshop.

**Muncul peringatan "belum diverifikasi Adobe".**
Normal untuk plugin yang dibagikan langsung di luar Marketplace.

**Hasil Layout Film terlihat terbalik atau kacau.**
Cek bahwa film berupa hitam di atas putih. Coba juga dengan satu channel dulu untuk memastikan hasilnya sesuai.

**Muncul pesan error.**
Catat isi pesan error-nya, lalu laporkan ke pembuat plugin bersama versi Photoshop dan sistem operasi (Mac atau Windows) yang Anda pakai.

---

Dibuat oleh abdllahmajid.
