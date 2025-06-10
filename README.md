## 🔐 Apa Itu XOR Cipher?

*XOR Cipher* adalah algoritma enkripsi berbasis *operasi logika XOR (Exclusive OR)*. XOR sendiri adalah operasi logika dasar dalam komputer, yang sering digunakan untuk manipulasi data pada tingkat bit.

Algoritma ini tergolong *stream cipher, yaitu teknik enkripsi yang bekerja **bit per bit* atau *karakter per karakter* terhadap data, berbeda dengan block cipher seperti AES yang memproses data dalam blok besar.

---

## ⚙ Prinsip Dasar XOR

Operasi XOR bekerja seperti ini:

| A (bit) | B (bit) | A XOR B |
| ------- | ------- | ------- |
| 0       | 0       | 0       |
| 0       | 1       | 1       |
| 1       | 0       | 1       |
| 1       | 1       | 0       |

*Sifat penting XOR:*

* A XOR B = C dan C XOR B = A
  Artinya, jika kita mengenkripsi A dengan B menghasilkan C, maka kita bisa mendekripsi C dengan B untuk mendapatkan A kembali.
  Inilah alasan *XOR sangat cocok untuk enkripsi simetris* (satu kunci digunakan untuk enkripsi dan dekripsi).

---

## 📌 Langkah-langkah Algoritma XOR Cipher dalam Program

### 1️⃣ Konversi Teks ke Biner

Sebelum dilakukan XOR, teks biasa (plaintext) harus dikonversi ke bentuk *biner 8-bit per karakter*.

#### Contoh:

plaintext
Teks: A
Kode ASCII: 65
Biner 8-bit: 01000001


Dalam program:

python
def teks_ke_biner(teks):
    return ''.join(format(ord(char), '08b') for char in teks)


---

### 2️⃣ XOR Bit-per-Bit antara Plaintext dan Kunci

Setelah dikonversi, pesan biner akan dienkripsi dengan kunci biner menggunakan operasi XOR:

#### Jika:

* *Pesan* = 01000001 (A)
* *Kunci* = 10101010
* Maka:

plaintext
01000001
XOR
10101010
---------
11101011


Jika panjang kunci *lebih pendek* dari pesan, kunci akan diulang secara siklik:

python
bit_kunci = kunci_biner[i % len(kunci_biner)]


Dalam program:

python
def xor_cipher(pesan_biner, kunci_biner):
    hasil = ''
    for i in range(len(pesan_biner)):
        bit_pesan = int(pesan_biner[i])
        bit_kunci = int(kunci_biner[i % len(kunci_biner)])
        hasil += str(bit_pesan ^ bit_kunci)
    return hasil


---

### 3️⃣ Hasil XOR = Ciphertext (Biner)

Ciphertext disimpan dalam format biner. Untuk membacanya kembali dalam bentuk teks, proses dekripsi harus dilakukan.

---

### 4️⃣ Dekripsi XOR = XOR Ulang dengan Kunci yang Sama

Karena XOR bersifat reversibel, kita cukup XOR-kan kembali ciphertext dengan kunci biner yang sama untuk mendapatkan kembali plaintext dalam bentuk biner:

plaintext
Ciphertext: 11101011
XOR
Kunci     : 10101010
-----------------------
Plaintext : 01000001 → ASCII → 'A'


Program akan mengonversi hasil biner ini kembali ke teks:

python
def biner_ke_teks(biner):
    chars = [biner[i:i+8] for i in range(0, len(biner), 8)]
    return ''.join(chr(int(char, 2)) for char in chars)


---

## 📦 Contoh Lengkap Proses

### Misal:

* *Plaintext*: HI
* ASCII dari H dan I → 72, 73
* Biner:

  * H → 01001000
  * I → 01001001
    → 0100100001001001

### Kunci: 1010 (4-bit, akan diulang)

* Diulang menjadi: 1010101010101010

### XOR:

plaintext
Pesan     : 0100100001001001
Kunci     : 1010101010101010
Hasil XOR : 1110001011100011


### Dekripsi:

plaintext
Cipher    : 1110001011100011
XOR Kunci : 1010101010101010
Hasil     : 0100100001001001 → "HI"


---

## ✅ Kelebihan Algoritma XOR Cipher

| Kelebihan                    | Penjelasan                                                               |
| ---------------------------- | ------------------------------------------------------------------------ |
| 🔸 Simpel dan cepat          | Hanya menggunakan operasi logika dasar, sangat cepat dan efisien.        |
| 🔸 Simetris                  | Enkripsi dan dekripsi pakai algoritma yang sama.                         |
| 🔸 Ringan untuk sistem kecil | Cocok untuk validasi teks, QR code, atau sistem mikro.                   |
| 🔸 Ideal untuk edukasi       | Membantu mahasiswa memahami prinsip enkripsi dasar secara visual/logika. |

---

## ❌ Kelemahan Algoritma XOR Cipher

| Kelemahan                             | Penjelasan                                                              |
| ------------------------------------- | ----------------------------------------------------------------------- |
| ⚠ Rentan terhadap serangan           | Jika kunci pendek atau berulang, mudah diretas dengan teknik statistik. |
| ⚠ Tidak ada integritas data          | XOR tidak bisa mendeteksi perubahan data atau manipulasi ciphertext.    |
| ⚠ Tidak cocok untuk produksi         | Tidak bisa digunakan untuk sistem yang membutuhkan keamanan tinggi.     |
| ⚠ Tidak mendukung karakter non-ASCII | Unicode/emoji bisa menyebabkan error saat konversi ke biner.            |

---

## 📚 Kesimpulan

Algoritma XOR Cipher:

* *Sangat cocok untuk pembelajaran dasar kriptografi.*
* Menunjukkan cara kerja enkripsi simetris yang reversibel.
* Namun, *tidak cukup aman* untuk digunakan dalam sistem modern yang memerlukan proteksi serius, kecuali dalam implementasi *one-time pad* dengan kunci sepanjang pesan yang digunakan sekali.

---

