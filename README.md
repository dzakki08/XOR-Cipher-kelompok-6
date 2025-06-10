
# XOR Cipher Sederhana
**XOR Cipher** adalah metode enkripsi simetris sederhana yang menggunakan operasi logika **XOR (Exclusive OR)** antara data dan kunci untuk mengubah pesan menjadi bentuk terenkripsi. Karena sifat XOR yang reversibel, data dapat didekripsi kembali dengan menggunakan kunci yang sama. XOR Cipher dikenal karena kecepatannya, efisiensinya, dan kemudahannya untuk diimplementasikan, namun tidak cocok untuk keamanan tingkat tinggi tanpa pengelolaan kunci yang baik.

Aplikasi GUI kriptografi sederhana menggunakan algoritma **XOR Cipher** untuk melakukan enkripsi dan dekripsi data berbasis teks. Proyek ini dikembangkan sebagai bagian dari tugas akhir mata kuliah **Kriptografi** oleh mahasiswa **Informatika Universitas Bengkulu** semester 4.

## 🧠 Deskripsi Proyek

Aplikasi ini menampilkan dua pendekatan enkripsi simetris:

* **XOR Cipher**: algoritma ringan berbasis operasi logika XOR, cocok untuk skenario dengan keterbatasan sumber daya.
* **AES (Advanced Encryption Standard)**: algoritma kriptografi modern yang aman namun lebih kompleks dan memerlukan sumber daya lebih besar.

Dilengkapi dengan antarmuka grafis berbasis **Tkinter**, pengguna dapat dengan mudah:

* Mengonversi teks ke biner
* Melakukan enkripsi XOR
* Melakukan dekripsi XOR
* Melakukan enkripsi dan dekripsi dengan AES

## 👥 Anggota Kelompok

1. Pebi Heriansyah (G1A023003)
2. Arriqoh Firzatullah (G1A023033)
3. Achmad Azza Al Haqi (G1A023037)
4. Reffki Andrea Pratama (G1A023039)
5. Muhammad Farhan Dzakki (G1A023041)

## 📋 Fitur Aplikasi

* ✅ Konversi teks ↔ biner (8-bit/karakter)
* ✅ Enkripsi dan dekripsi menggunakan XOR Cipher
* ✅ Enkripsi dan dekripsi menggunakan AES
* ✅ Validasi input (format biner, kosong, dll)
* ✅ GUI berbasis Python Tkinter
* ✅ Ringan, cepat, dan edukatif

## 🧪 Pengujian

Pengujian dilakukan menggunakan metode **black-box testing**, dengan fokus pada:

* Keakuratan proses enkripsi dan dekripsi
* Validasi input
* Respons antarmuka pengguna

### Contoh Uji XOR Cipher

| Skenario     | Input                                         | Output                           |
| ------------ | ----------------------------------------------| ---------------------------------|
| Enkripsi XOR | "halo", kunci: 1010                           | 11000010110010111100011011000101 |
| Dekripsi XOR | 11000010110010111100011011000101, kunci: 1010 | "halo"                           |

### Contoh Uji AES

| Skenario     | Input                                               | Output                  |
| ------------ | ----------------------------------------------------| ------------------------|
| Enkripsi AES | "HALO", kunci: "INFORMATIKA"                        | p8/1xKw3Npe+tG6Yhhl1Lw==|
| Dekripsi AES | p8/1xKw3Npe+tG6Yhhl1Lw==, kunci: "INFORMATIKA"      | "HALO"                  |

## ⚙️ Teknologi

* **Bahasa Pemrograman**: Python 3
* **Library GUI**: Tkinter
* **Library Tambahan**: `tkinter.messagebox`
* **IDE yang direkomendasikan**: VS Code, PyCharm, atau IDLE

## 📂 Struktur Antarmuka

* Frame menu (navigasi enkripsi/dekripsi)
* Frame input/output
* Tombol aksi: Konversi, Enkripsi, Dekripsi

## 📈 Analisis & Perbandingan

| Aspek         | XOR Cipher                         | AES                               |
| ------------- | ---------------------------------- | --------------------------------- |
| Kecepatan     | Sangat cepat (<0.00003 s)          | Sedikit lebih lambat (\~0.0001 s) |
| Ukuran Output | Sama dengan input                  | Lebih besar (Base64)              |
| Keamanan      | Rendah (kunci harus acak dan unik) | Tinggi (standar industri)         |
| Kompleksitas  | Sangat sederhana                   | Kompleks                          |
| Tujuan        | Edukasi, ringan                    | Produksi, profesional             |

## 📌 Kelebihan

* Ringan dan cepat
* Edukatif untuk pemula kriptografi
* Antarmuka pengguna intuitif
* Validasi input yang baik

## ⚠️ Keterbatasan

* Tidak cocok untuk aplikasi dengan kebutuhan keamanan tinggi
* Tidak mendukung karakter Unicode penuh
* Belum tersedia versi web/mobile

## 📚 Referensi

* Dewi (2024), Erdriani et al. (2023), Lubis (2024), Harahap et al. (2014), Rahim & Nasution (2024), Situmeang et al. (2023)

## 💡 Saran Pengembangan

* Dukungan Unicode penuh
* Ekspor/Impor data dari/ke file
* Clipboard auto-copy hasil enkripsi
* Mode tema gelap/terang
* Porting ke platform web (Flask/Streamlit)
