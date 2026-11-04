# 📸 Photobooth PPPSDM POM 2026

Proyek photobooth berbasis web dengan tampilan **vintage, Y2K, dan Windows retro**, bertema PPPSDM POM 2026. Antarmukanya dirancang untuk mengambil foto, menyusun photostrip, menambahkan dekorasi, dan mengunduh hasil sebagai PNG.

> **Status: prototipe / perlu perbaikan.** Versi saat ini berasal dari file `PRE-FIX-BACKUP`. Sejumlah bagian JavaScript belum lengkap atau belum terhubung dengan benar, sehingga alur kamera dan pengambilan foto belum dapat dianggap berfungsi penuh.

## ✨ Fitur dalam antarmuka dan kode

- Tampilan retro dengan panel dan tombol bergaya Windows klasik.
- Pilihan filter: Original, Warm Grain, Sepia Y2K, Cyber POM, Mono B&W, dan Y2K Flash.
- Pilihan layout: **4-Strip**, **2×2 Grid**, dan **ID Badge**.
- Tema: **POM Official**, **Vintage Cream**, **Y2K Pastel**, dan **Cyber Lab**.
- Pengaturan caption pada hasil foto.
- Stiker yang dapat diposisikan pada canvas.
- Doodle pen dengan pilihan warna dan ukuran.
- Kode pengambilan hingga empat pose, hitung mundur, retake, dan reset.
- Kode ekspor photostrip ke format **PNG**.

Daftar ini menjelaskan komponen yang tersedia dalam sumber, bukan jaminan bahwa seluruh fitur sudah berjalan. Lihat bagian **Keterbatasan yang diketahui** sebelum mencoba.

## 🛠️ Teknologi

| Bagian | Teknologi |
| --- | --- |
| Struktur | HTML5 |
| Tampilan | CSS dan Tailwind CSS melalui CDN |
| Logika | JavaScript vanilla |
| Pengolahan gambar | HTML Canvas 2D |
| Ikon | Font Awesome 6.4.0 melalui CDN |
| Font | Google Fonts: VT323, Courier Prime, Plus Jakarta Sans |

Tidak ada proses build, package manager, atau backend yang disertakan dalam repository ini.

## 📂 Struktur repository

```text
photobooth-ppsdm/
├── .gitignore
├── index.html       # Halaman, styling, dan logika aplikasi
└── README.md        # Dokumentasi proyek
```

File backup lokal dan file `.env` dikecualikan melalui `.gitignore`.

## 🚀 Menjalankan secara lokal

### Prasyarat

- Git untuk mengunduh repository.
- Python 3 untuk menjalankan server statis pada contoh di bawah.
- Browser dengan dukungan JavaScript dan Canvas.
- Kamera perangkat dan izin browser diperlukan untuk alur pengambilan foto setelah kode kamera diperbaiki.
- Koneksi internet untuk memuat Tailwind CSS, Font Awesome, dan Google Fonts dari layanan eksternal.

### Langkah

1. Clone repository:

   ```bash
   git clone https://github.com/tazzkirahamaliah/photobooth-ppsdm.git
   cd photobooth-ppsdm
   ```

2. Jalankan server statis lokal:

   ```bash
   python3 -m http.server 8000 --bind 127.0.0.1
   ```

3. Buka `http://localhost:8000` di browser.
4. Untuk memeriksa masalah JavaScript, buka **Developer Tools → Console**.
5. Hentikan server dengan **Ctrl+C** di terminal.

Menjalankan server hanya menyajikan file HTML; langkah ini tidak memperbaiki masalah kode yang dicatat di bawah.

## ⚠️ Keterbatasan yang diketahui

- Terdapat potongan JavaScript dan tag penutup duplikat setelah `</html>`. Potongan tersebut berada di luar blok `<script>` yang semestinya.
- Kode merujuk fungsi seperti `runCaptureSequence`, `initCamera`, dan `loopLiveViewport` yang belum didefinisikan dalam versi ini.
- Referensi canvas, elemen kamera, dan beberapa fungsi efek suara belum lengkap. Hal ini dapat memicu error saat halaman dijalankan.
- `renderOutputPhotostrip()` membuat ulang foto contoh ketika jumlah foto kurang dari empat, sehingga perlu diselaraskan dengan alur pengambilan foto satu per satu.
- Kelulusan pemeriksaan sintaks JavaScript tidak menjamin aplikasi bebas dari error runtime. Alur kamera, retake, doodle, dan unduhan belum diverifikasi melalui pengujian browser menyeluruh.
- Aset CDN memerlukan internet; tampilan dapat berbeda ketika layanan eksternal tidak dapat diakses.

## 🔧 Pengembangan berikutnya

- Melengkapi inisialisasi kamera, referensi DOM/canvas, dan fungsi efek suara.
- Memindahkan event listener ke blok script yang benar serta menghapus tag penutup duplikat.
- Menyatukan alur capture manual, retake, reset, dan foto contoh.
- Menguji izin kamera, setiap layout, dekorasi, dan ekspor PNG di browser.

## 📄 Lisensi

Repository ini belum menyertakan file lisensi. Jangan mengasumsikan bahwa kode telah dilisensikan sebagai MIT atau lisensi open-source lainnya.