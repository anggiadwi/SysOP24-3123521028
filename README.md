## Jawaban Soal No 1

### Siklus CPU
Siklus CPU, juga dikenal sebagai siklus instruksi, adalah urutan langkah-langkah dasar yang dijalankan oleh CPU untuk mengeksekusi instruksi-instruksi yang diberikan oleh program yang sedang berjalan. Siklus CPU terdiri dari beberapa tahap yang secara berurutan dieksekusi untuk setiap instruksi. Tahap-tahap ini mencakup:

- Fetch :  CPU mengambil instruksi berikutnya dari memori utama atau cache instruksi dan memuatnya ke dalam register instruksi di dalam CPU.

- Decode: Instruksi yang telah diambil kemudian didekode oleh CPU. Ini melibatkan penentuan operasi apa yang harus dilakukan oleh instruksi tersebut, serta lokasi dari operand (data) yang diperlukan.

- Execute :  CPU menjalankan operasi yang ditentukan oleh instruksi. Ini bisa berupa operasi aritmatika, logika, pemindahan data, atau instruksi kontrol lainnya.

### Bahasa Pemrograman dan Compiler

1. Bahasa pemrograman adalah aturan atau sintaks yang digunakan oleh programmer untuk menulis instruksi dan algoritma yang dapat dimengerti oleh komputer.Bahasa pemrograman memungkinkan programmer untuk mengkomunikasikan instruksi kepada komputer untuk melakukan tugas-tugas tertentu, seperti pengolahan data, manipulasi teks, pengambilan keputusan, dan lainnya.Bahasa pemrograman juga menyediakan seperangkat kata kunci, struktur kontrol, dan aturan sintaks yang digunakan untuk menulis program.
Berbagai bahasa pemrograman memiliki tingkat abstraksi yang berbeda, dari yang lebih dekat dengan bahasa mesin seperti bahasa Assembly hingga yang lebih tinggi seperti Python atau Java.

2. Compiler adalah perangkat lunak yang menerjemahkan kode sumber dalam bahasa pemrograman ke dalam bahasa mesin atau kode yang dapat dimengerti oleh komputer.Peran compiler adalah mengubah kode yang ditulis oleh programmer dalam bahasa pemrograman menjadi bentuk yang dapat dijalankan oleh komputer, sehingga memungkinkan eksekusi program.

### Peran Sistem Operasi
Sistem operasi adalah perangkat lunak yang mengelola sumber daya komputer, menyediakan antarmuka antara perangkat keras dan perangkat lunak, serta menyediakan layanan-layanan dasar kepada aplikasi.
Peran sistem operasi adalah menyediakan lingkungan eksekusi yang aman dan terstruktur untuk menjalankan aplikasi, mengatur dan mengelola akses ke sumber daya komputer, serta memberikan layanan-layanan dasar seperti manajemen proses, memori, perangkat input/output, dan file.


## Jawaban Soal No 3
### Menggunkan VM Debian
## Melakukan clone https://github.com/ferryastika/flops-iops

![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/3efd8e3f-3a73-4122-a306-34336db10b62)



## Build Binaries
```sh

  $ make
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/19f60dda-64dd-47be-9461-2a7829e9b945)
 
Analisis: $make berfungsi untuk membaca dan menjalankan file  yang berisi aturan-aturan tentang cara membangun (compile) dan mengatur proyek perangkat lunak.

## Cleaning Old Build
```sh
$ make clean
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/ed3c358b-8209-4f26-a954-6eb8b3a10783)

Analisis: $make clean berfungsi untuk membersihkan file-file sementara atau hasil kompilasi yang dihasilkan selama proses pembangunan proyek perangkat lunak.
  
## Install Binaries
```sh
$  make install
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/2e2be148-7290-4f5d-a74c-b2eebcb0abd7)

Analisis: Perintah $make install bertanggung jawab untuk menyalin file-file yang telah dikompilasi (misalnya, file biner, file konfigurasi, dll.) ke lokasi yang ditentukan di dalam sistem file.

## Uninstall Binaries
```sh
  $ sudo make uninstall
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/5bbaa957-dc62-4134-8bf6-84e4f6a55b0e)

 Analisis: Jika tersedia, perintah ini akan menghapus perangkat lunak yang telah diinstal sebelumnya menggunakan sudo make install. Namun, tidak semua perangkat lunak menyediakan perintah ini. Jika tidak tersedia, Anda harus menghapusnya secara manual.
## Usage

- ## Percobaan 1
```sh
  $ iops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/8ccdf9f7-6aa6-4576-be93-2b419c26ff9c)
```sh
$ flops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/42b8e8d5-3f6b-4197-8aa8-ddcc282cce72)


- ## Percobaan 2
```sh
$ iops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/0c514093-b7f3-46ee-912e-83ce1af4c835)

```sh
$ flops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/584c1e1c-0cdb-49da-9214-f0c9ec88d441)

- ## Percobaan 3
```sh
$ iops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/eb69cc2e-f655-41f5-ba70-8eef66e18190)

```sh
$ flops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/2d42ddb7-66bc-443d-ad19-76dfeace0864)

- ## Percobaan 4
```sh
$ iops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/78935865-8c03-400a-a5f6-f737e2df00b2)

```sh
$ flops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/df445241-df5f-4c5e-9203-556e78d47f9e)

- ## Percobaan 5
```sh
$ iops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/cbd7c8f1-0700-4466-b022-c5a742891979)

```sh
$ flops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/f0ebc190-bc4e-423f-85c9-26ed0242a26d)

Analisis: Kedua perintah ini berguna untuk mengevaluasi kinerja sistem, terutama dalam konteks kinerja komputasi paralel. Mereka membantu pengguna untuk memahami seberapa efisien sistem dalam menangani operasi masukan/keluaran atau operasi floating point, yang dapat berguna dalam pengembangan dan penyetelan aplikasi yang memerlukan komputasi intensif.

![WhatsApp Image 2024-03-18 at 12 05 00_3d652453](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/ec869ae7-ef83-4cc9-909a-4df5ec6f9188)
Kesimpulan:
Kesimpulannya, hasil dari kedua perintah tersebut memberikan gambaran tentang kinerja sistem dalam menangani operasi masukan/keluaran (IOPS) dan operasi matematika floating-point (FLOPS). Semakin tinggi nilai yang diperoleh, semakin baik kinerja sistem dalam aspek yang diukur. Namun, untuk mendapatkan gambaran yang lebih lengkap, perlu dilakukan analisis lebih lanjut dan pembandingan dengan standar kinerja atau hasil percobaan sebelumnya.








