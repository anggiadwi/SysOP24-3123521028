## Perbedaan Pararel Concurrent dan Pararel-Concurrent

![file1](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/1a9dfe6b-24b1-4d5a-9b04-bb91ed7eaccc)


Perbedaan antara paralel, konkuren, dan paralel-konkuren (paralel-concurrent) dalam Sistem Operasi adalah sebagai berikut:

### **Paralel (Parallel)**

- **Definisi:** Paralelisme adalah teknik di mana beberapa proses atau tugas dijalankan secara bersamaan pada beberapa prosesor atau inti CPU yang berbeda.

- **Tujuan:** Meningkatkan kinerja dengan memecah tugas besar menjadi tugas-tugas yang lebih kecil yang dapat dijalankan secara bersamaan.

- **Implementasi:** Memerlukan perangkat keras dengan beberapa prosesor atau inti CPU.

- **Contoh:** Pengolahan data besar dalam sistem superkomputer, di mana satu tugas dipecah menjadi beberapa sub-tugas yang dijalankan secara bersamaan pada banyak prosesor.

- **Contoh pada Gambar:**
   - Task 1 dijalankan di Core 1.
   - Task 2 dijalankan di Core 2.
   - Kedua tugas berjalan secara bersamaan dan independen pada inti CPU yang terpisah.

- **Kelebihan:** Mengurangi waktu eksekusi total dengan menjalankan tugas secara simultan pada perangkat keras yang berbeda.

### **Konkuren (Concurrent)**

- **Definisi:** Konkurensi adalah teknik di mana beberapa proses atau tugas dikelola secara bersamaan oleh satu prosesor. Prosesor tersebut berpindah-pindah di antara tugas-tugas ini untuk memberikan kesan bahwa mereka berjalan secara bersamaan.

- **Tujuan:** Meningkatkan responsivitas dan efisiensi dengan memungkinkan beberapa tugas berjalan "bersamaan" melalui penjadwalan cerdas.

- **Implementasi:** Dapat dilakukan pada sistem dengan satu prosesor melalui penggunaan thread, pengalihan konteks, dan penjadwalan tugas.

- **Contoh:** Aplikasi GUI di mana antarmuka pengguna tetap responsif sementara operasi latar belakang seperti pemrosesan data atau pengambilan data dari jaringan berjalan secara "bersamaan".

- **Contoh pada Gambar:**
  - Core 1 menangani Task 1.1, Task 1.2, Task 1.3, Task 1.4, dan Task 1.5 secara bergantian.
  - Core 2 menangani Task 2.1, Task 2.2, Task 2.3, Task 2.4, dan Task 2.5 secara bergantian.
  - Meskipun sub-tugas ini tidak benar-benar berjalan bersamaan, mereka diproses dengan cepat secara bergantian sehingga tampak berjalan bersamaan.

- **Kelebihan:** Meningkatkan responsivitas dan efisiensi penggunaan CPU dengan memungkinkan banyak sub-tugas berbagi waktu prosesor.

### **Paralel-Konkuren (Parallel-Concurrent)**

- **Definisi:** Kombinasi dari paralelisme dan konkurensi di mana beberapa tugas besar dijalankan secara bersamaan pada beberapa prosesor (paralelisme), dan setiap tugas besar mungkin terdiri dari beberapa sub-tugas yang dijalankan secara bersamaan atau bergantian (konkurensi).

- **Tujuan:** Menggabungkan keuntungan dari paralelisme dan konkurensi untuk memaksimalkan kinerja dan responsivitas.

- **Implementasi:** Memerlukan perangkat keras dengan beberapa prosesor serta teknik penjadwalan cerdas untuk mengelola tugas dan sub-tugas.

- **Contoh:** Sistem server web yang menggunakan beberapa prosesor untuk menangani banyak permintaan (paralel), sementara setiap permintaan mungkin dikelola oleh beberapa thread yang berjalan "bersamaan" untuk menangani operasi I/O atau komputasi.

- **Contoh pada Gambar:**
    - Core 1 menangani sub-tugas dari Task 1 (Task 1.1, Task 1.2, Task 1.3, Task 1.4, Task 1.5).
    - Core 2 menangani sub-tugas dari Task 2 (Task 2.1, Task 2.2, Task 2.3, Task 2.4, Task 2.5).
    - Setiap inti CPU menjalankan sub-tugas dari tugas yang berbeda secara bersamaan, dan sub-tugas ini dapat diproses secara konkuren dalam inti yang sama.
- **Kelebihan:** Menggabungkan manfaat dari paralelisme dan konkurensi untuk memaksimalkan kinerja dan responsivitas, memungkinkan penggunaan optimal dari beberapa inti CPU dan penjadwalan cerdas dari sub-tugas.

## **Ringkasan**
- **Paralel:** Fokus pada menjalankan tugas yang berbeda secara bersamaan pada perangkat keras yang berbeda (prosesor atau inti CPU).

- **Konkuren:** Fokus pada menjalankan beberapa tugas secara bersamaan melalui penjadwalan cerdas pada satu atau beberapa prosesor, memberikan kesan bahwa tugas-tugas tersebut berjalan secara bersamaan.

- **Paralel-Konkuren:** Menggabungkan paralelisme dan konkurensi untuk memaksimalkan kinerja dan responsivitas dengan menjalankan tugas secara bersamaan pada beberapa prosesor dan menggunakan penjadwalan cerdas untuk mengelola sub-tugas.


## **Perbedaan Concurrent dan Serial**

![file2](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/6ddb145b-ee12-4d38-867e-5c0611f98bc7)

Gambar di atas menunjukkan perbedaan antara eksekusi serial dan eksekusi konkuren dari tugas-tugas (tasks).

### **Eksekusi Serial**

- **Deskripsi:** Pada model ini, tugas-tugas dijalankan satu per satu secara berurutan. Tugas berikutnya baru mulai dijalankan setelah tugas sebelumnya selesai.
- **Contoh pada Gambar:**
  - Task 0 dimulai dan diselesaikan terlebih dahulu.
  - Setelah Task 0 selesai, Task 1 dimulai dan diselesaikan.
  - Setelah Task 1 selesai, Task 2 dimulai dan diselesaikan.
- **Karakteristik:**
     - **Waktu Eksekusi:** Setiap tugas harus menunggu tugas sebelumnya selesai sebelum bisa dimulai.

     - **Utilisasi CPU:** Bisa kurang efisien karena setiap tugas dijalankan secara berurutan tanpa ada tumpang tindih eksekusi.

     - **Kelebihan:** Sederhana untuk diimplementasikan dan lebih mudah untuk di-debug karena urutan eksekusi yang jelas.

     - **Kekurangan:** Waktu eksekusi total lebih lama karena tidak ada tugas yang berjalan bersamaan.

### **Eksekusi Konkuren**

- **Deskripsi:** Pada model ini, beberapa tugas dapat dijalankan secara bersamaan, memungkinkan overlap dalam eksekusi tugas-tugas tersebut.
- **Contoh pada Gambar:**
  - Task 0 dimulai terlebih dahulu.
  - Task 1 dimulai sebelum Task 0 selesai, sehingga kedua tugas berjalan secara bersamaan.
  - Task 2 dimulai sebelum Task 1 selesai, menambah tingkat konkuren.
  - Task 3 dimulai sebelum Task 2 selesai, sehingga ada beberapa tugas yang berjalan bersamaan pada satu waktu.
- **Karakteristik:**
   - **Waktu Eksekusi:** Tugas-tugas dapat dijalankan secara bersamaan, mengurangi waktu eksekusi total.

   - **Utilisasi CPU:** Lebih efisien karena tugas-tugas dapat berjalan bersamaan, memaksimalkan penggunaan CPU.

   - **Kelebihan:** Meningkatkan efisiensi dan responsivitas sistem dengan memungkinkan beberapa tugas dijalankan bersamaan.

   - **Kekurangan:** Lebih kompleks untuk diimplementasikan dan di-debug karena adanya tumpang tindih dalam eksekusi tugas-tugas.

### **Ringkasan**

- **Eksekusi Serial:** Tugas-tugas dijalankan satu per satu secara berurutan. Tugas berikutnya dimulai hanya setelah tugas sebelumnya selesai. Cocok untuk sistem yang membutuhkan urutan eksekusi yang jelas dan sederhana, namun kurang efisien dalam hal waktu eksekusi total.

- **Eksekusi Konkuren:** Tugas-tugas dijalankan bersamaan, memungkinkan overlap dalam eksekusi tugas-tugas tersebut. Cocok untuk sistem yang membutuhkan efisiensi dan responsivitas yang tinggi, namun lebih kompleks untuk diimplementasikan dan di-debug.
