🚀 Implementasi Algoritma: Konvolusi Citra & Optimasi Strassen

Selamat datang di repositori proyek implementasi algoritma! Repositori ini berisi kumpulan program bahasa C yang mendemonstrasikan konsep Kompleksitas Algoritma, Rekursi (Divide & Conquer), serta Alokasi Memori Dinamis melalui studi kasus praktis berdasarkan landasan teori komputasi.

📂 Daftar File & Deskripsi

| Nama File | Deskripsi Program | Kompleksitas Teoretis |
| perkalian_matriks.c | Implementasi dasar alokasi memori dinamis dan logika 7 perkalian Strassen untuk matriks 2x2. | $O(n^{\log_2 7}) \approx O(n^{2.81})$ |
| strassen.c | Implementasi tingkat lanjut Strassen (Divide & Conquer) secara rekursif untuk matriks 4x4. | $O(n^{2.81})$ |
| konvolusi.c | Pemrosesan citra digital (Image Blurring) menggunakan operasi Nested Loop (Konvolusi Kernel). | $O(w \times h \times c \times k^2)$ |

Catatan: Konsep dan batasan memori (Stack Pointer & Heap) pada program ini diimplementasikan berdasarkan panduan analisis memori arsitektur.

🛠️ Persiapan Lingkungan Dasar (Prerequisites)

Sebelum mulai mengkompilasi dan menjalankan program, pastikan sistem Anda memenuhi syarat berikut:

Compiler C (GCC)

Linux/macOS: Biasanya sudah terpasang atau dapat diinstal via sudo apt install build-essential (Linux) atau xcode-select --install (macOS).

Windows: Dapat menggunakan MinGW, MSYS2, atau WSL (Windows Subsystem for Linux).

Library Tambahan (Khusus Konvolusi)

Pastikan file stb_image.h dan stb_image_write.h berada di dalam folder yang sama dengan file kode C.

File Input Gambar

Siapkan sebuah gambar berformat PNG dan ubah namanya menjadi input.png. Simpan di folder yang sama tempat kode kompilasi dijalankan.

💻 Panduan Eksekusi Langkah-demi-Langkah

Ikuti instruksi di bawah ini dengan membuka Terminal (Linux/macOS) atau Command Prompt / PowerShell (Windows), lalu arahkan ke direktori penyimpanan file kode ini menggunakan perintah cd.

1. Menjalankan perkalian_matriks.c (Strassen 2x2)

Program ini akan mengalokasikan memori, mengisi matriks dengan angka acak (0-9) secara otomatis, dan menghitung hasil perkaliannya menggunakan 7 rumusan Strassen.

Langkah Kompilasi:

gcc perkalian_matriks.c -o perkalian_matriks



Langkah Eksekusi:

# Pengguna Linux / macOS:
./perkalian_matriks

# Pengguna Windows:
perkalian_matriks.exe



2. Menjalankan strassen.c (Strassen Rekursif 4x4)

Program ini menguji efisiensi rekursi dalam memecah matriks yang lebih besar menjadi sub-matriks kecil, memprosesnya, lalu menggabungkannya kembali menjadi matriks hasil akhir.

Langkah Kompilasi:

gcc strassen.c -o strassen



Langkah Eksekusi:

# Pengguna Linux / macOS:
./strassen

# Pengguna Windows:
strassen.exe



3. Menjalankan konvolusi.c (Filter Citra Blur)

Program ini menguji looping tingkat tinggi (nested loop O(n^2)) secara visual. Pastikan input.png dan header files sudah tersedia.

Langkah Kompilasi:
(Flag -lm ditambahkan untuk menautkan library matematika bawaan pada lingkungan berbasis Unix).

gcc konvolusi.c -o konvolusi -lm



Langkah Eksekusi:

# Pengguna Linux / macOS:
./konvolusi

# Pengguna Windows:
konvolusi.exe



Hasil Akhir: Jika terminal menampilkan pesan "Proses selesai. Cek output_blur.png", silakan buka folder Anda. Anda akan menemukan file gambar baru (output_blur.png) yang sudah berhasil diberi efek blur.

🧹 Penanganan Error Umum (Troubleshooting)

gcc: command not found 👉 Artinya compiler C belum terinstal di sistem Anda. Silakan instal GCC terlebih dahulu sesuai OS Anda.

fatal error: stb_image.h: No such file or directory 👉 Pastikan header file (stb_image.h dan stb_image_write.h) benar-benar ada di dalam folder yang sama persis dengan konvolusi.c.

Program konvolusi langsung keluar / gagal 👉 Hal ini umumnya terjadi karena program tidak dapat menemukan file gambar. Pastikan gambar yang Anda siapkan benar-benar bernama input.png (perhatikan ekstensi file yang ganda, seperti input.png.png akibat pengaturan Windows yang menyembunyikan ekstensi).
