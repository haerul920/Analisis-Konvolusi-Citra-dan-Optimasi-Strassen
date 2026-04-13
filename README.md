# 🚀 Implementasi Algoritma: Konvolusi Citra & Optimasi Strassen

Selamat datang di repositori proyek implementasi algoritma! Repositori ini berisi kumpulan program bahasa C yang mendemonstrasikan konsep **Kompleksitas Algoritma**, **Rekursi (*Divide & Conquer*)**, serta **Alokasi Memori Dinamis** melalui studi kasus praktis.

---

## 📂 Daftar File & Deskripsi

| Nama File | Deskripsi Program | Kompleksitas Teoretis |
| :--- | :--- | :--- |
| `perkalian_matriks.c` | Implementasi dasar alokasi memori dinamis dan logika 7 perkalian Strassen untuk matriks 2x2. | $O(n^{\log_2 7}) \approx O(n^{2.81})$ |
| `strassen.c` | Implementasi tingkat lanjut Strassen (*Divide & Conquer*) secara rekursif untuk matriks 4x4. | $O(n^{2.81})$ |
| `konvolusi.c` | Pemrosesan citra digital (*Image Blurring*) menggunakan operasi *Nested Loop* (Konvolusi Kernel). | $O(w \times h \times c \times k^2)$ |

*(Catatan: Konsep dan batasan memori (Stack Pointer & Heap) diimplementasikan berdasarkan panduan analisis algoritma.)*

---

## 🛠️ Persiapan Lingkungan Dasar (*Prerequisites*)

Sebelum mulai mengkompilasi dan menjalankan program, pastikan sistem Anda memenuhi syarat berikut:

1. **Compiler C (GCC)**
   * **Linux/macOS:** Biasanya sudah terpasang atau dapat diinstal via `sudo apt install build-essential` (Linux) / `xcode-select --install` (macOS).
   * **Windows:** Dapat menggunakan MinGW, MSYS2, atau WSL (Windows Subsystem for Linux).
2. **Library Tambahan (Khusus Konvolusi)**
   * Pastikan file header `stb_image.h` dan `stb_image_write.h` **berada di dalam direktori yang sama** dengan file kode C.
3. **File Input Gambar**
   * Siapkan sebuah gambar berformat PNG dan ubah namanya menjadi `input.png`. Simpan di folder yang sama.

---

## 💻 Panduan Eksekusi Langkah-demi-Langkah

Ikuti instruksi di bawah ini dengan membuka **Terminal** (Linux/macOS) atau **Command Prompt / PowerShell** (Windows), lalu arahkan ke direktori penyimpanan file kode ini.

### 1. Menjalankan `perkalian_matriks.c` (Strassen 2x2)
Program ini akan mengisi matriks dengan angka acak (0-9) secara otomatis dan menghitung hasil perkaliannya menggunakan algoritma Strassen dasar.

**Langkah Kompilasi:**
```bash
gcc perkalian_matriks.c -o perkalian_matriks
 ```

**Langkah Eksekusi:**

```Bash
# Pengguna Linux / macOS:
./perkalian_matriks

# Pengguna Windows:
perkalian_matriks.exe
```

### 2. Menjalankan strassen.c (Strassen Rekursif 4x4)
Program ini menguji efisiensi rekursi dalam memecah matriks yang lebih besar menjadi sub-matriks kecil, lalu menggabungkannya kembali (Divide and Conquer).

**Langkah Kompilasi:**

```Bash
gcc strassen.c -o strassen
```
**Langkah Eksekusi:**

```Bash
# Pengguna Linux / macOS:
./strassen

# Pengguna Windows:
strassen.exe
```
### 3. Menjalankan konvolusi.c (Filter Citra Blur)
Program ini menguji efisiensi nested loop secara visual pada pemrosesan piksel gambar.

⚠️ **PERINGATAN:** Pastikan input.png, stb_image.h, dan stb_image_write.h sudah berada di direktori yang sama sebelum melanjutkan.

Langkah Kompilasi:
(Flag -lm ditambahkan untuk melampirkan library matematika bawaan pada beberapa lingkungan Unix).
```Bash
gcc konvolusi.c -o konvolusi -lm
```
Langkah Eksekusi:
```Bash
# Pengguna Linux / macOS:
./konvolusi

# Pengguna Windows:
konvolusi.exe
```
Hasil Akhir: Jika berhasil, terminal akan menampilkan pesan "Proses selesai. Cek output_blur.png". Anda akan menemukan file gambar baru (output_blur.png) di folder tersebut.

## 🧹 Penanganan Error Umum (Troubleshooting)
🔴 gcc: command not found ➔ Artinya compiler C belum terinstal di sistem Anda. Silakan instal GCC (atau MinGW untuk Windows) terlebih dahulu.</br>
🔴 fatal error: stb_image.h: No such file or directory ➔ Pastikan kedua file header stb_image benar-benar ada di dalam folder yang sama persis dengan konvolusi.c.</br>
🔴 Program konvolusi langsung keluar tanpa hasil / pesan ➔ Hal ini terjadi karena program gagal membaca gambar. Pastikan gambar Anda benar-benar bernama input.png dan pastikan ekstensi file tidak ganda (contoh salah: input.png.png).
