
Siklus CPU, juga dikenal sebagai siklus instruksi, adalah urutan langkah-langkah dasar yang dijalankan oleh CPU untuk mengeksekusi instruksi-instruksi yang diberikan oleh program yang sedang berjalan. Siklus CPU terdiri dari beberapa tahap yang secara berurutan dieksekusi untuk setiap instruksi. Tahap-tahap ini mencakup:
## Ilustrasi dalam CPU
![reg drawio](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/61b6b7a9-7aec-410b-ad2d-fda9727b52c1)

CPU terdiri dari Control Unit, Accumulator, dan Arithmetic Logic Unit (ALU).
Register lain seperti Program Counter (PC), Current Instruction Register (CIR), Memory Address Register (MAR), dan Memory Data Register (MDR) juga ada.

- Fetch :  CPU mengambil instruksi berikutnya dari memori utama atau cache instruksi dan memuatnya ke dalam register instruksi di dalam CPU.

- Decode: Instruksi yang telah diambil kemudian didekode oleh CPU. Ini melibatkan penentuan operasi apa yang harus dilakukan oleh instruksi tersebut, serta lokasi dari operand (data) yang diperlukan.
- 
- Execute :  CPU menjalankan operasi yang ditentukan oleh instruksi. Ini bisa berupa operasi aritmatika, logika, pemindahan data, atau instruksi kontrol lainnya.

## Langkah -langkah dalam CPU

![fetch first 1 drawio (1)](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/02ba1252-34cf-4e2d-874b-032f78a708ae)

-Program Counter berfungsi sebagai register yang menyimpan alamat memori dari instruksi berikutnya yang akan dieksekusi oleh CPU.

![fetch first 1 drawio](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/e006f329-9357-4338-a8f9-4af8d16c2c83)

-Alamat memori disimpan dalam register MAR, konten dari alamat memori dimuat ke dalam MDR, dan instruksi disimpan di CIR. Program Counter meningkat sebesar 1.

![fetch first 3 drawio](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/ea967b3a-284b-4d06-819c-c57230a2cea2)



![FIRST INT drawio](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/ccc943bf-2ad0-458d-9657-46f1d7b3efe8)

-Dekode Instruksi (Decode Instruction):
Instruksi "LOAD 10" telah diuraikan. Unit kontrol membuka jalur yang sesuai dalam CPU untuk melaksanakan instruksi "LOAD".

-Masukkan Instruksi ke Unit Kontrol (Enter Instruction into Control Unit):
Instruksi "LOAD 10" sudah didekode dan dimasukkan ke dalam unit kontrol. Unit kontrol menyiapkan jalur yang diperlukan untuk menjalankan instruksi tersebut.

-Eksekusi Instruksi LOAD 10:
CPU mengambil data dari alamat memori 10. Alamat tersebut disimpan dalam Memory Address Register (MAR). Isi dari alamat memori 10 kemudian diambil dan disimpan dalam Memory Data Register (MDR).

-Simpan Nilai ke Akumulator (Store Value into Accumulator):
Isi dari MDR, yang merupakan nilai dari alamat memori 10, dipindahkan ke dalam Akumulator. Sekarang, nilai dari alamat memori 10 telah tersimpan dalam Akumulator dan dapat digunakan untuk operasi selanjutnya.

Setelah instruksi pertama dilakukan maka selanjutnya adalah fetch instruksi ke dua.
![SEC IND drawio](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/8b6ad0b5-89be-4d57-b333-254228dd92a3)
Setelah Program Counter menunjukkan alamat memori yang baru, langkah berikutnya adalah menyalin alamat memori tersebut ke Memory Address Register (MAR). Setelah itu, konten dari alamat memori 101 diambil dan disimpan ke dalam Memory Data Register (MDR). Instruksi yang terdapat di alamat memori 101 juga disimpan di Current Instruction Register (CIR). Setelah itu, Program Counter akan bertambah 1 untuk menunjukkan instruksi selanjutnya.

![8 drawio](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/ff0e4a07-f51a-4b54-8c6f-8b1df12f7ac9)
Lakukan dekode instruksi kedua dengan cara yang sama seperti instruksi pertama dan teruskan ke Unit Kontrol. Setelah Unit Kontrol memahami bahwa instruksi ini adalah operasi penambahan (add), instruksi add diteruskan ke Unit Logika Aritmetika (ALU). Salin isi Akumulator ke ALU. Salin alamat memori 11 ke Register Alamat Memori (MAR) karena akan mengambil data dari alamat tersebut. Salin isi dari alamat memori 11 ke Register Data Memori (MDR). Transfer data dari MDR ke Akumulator. ALU akan menambahkan angka 3 dengan 2 dan menampilkan kembali hasilnya ke Akumulator untuk menjaga total running.

![fetch third drawio](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/b898d702-5c0f-4790-9a37-6284f2de79e8)
Alamat memori 102 dipindahkan ke Memory Address Register (MAR), sementara isi dari alamat memori tersebut disalin ke dalam Memory Data Register (MDR). Instruksi yang ada di alamat memori 102 juga dipindahkan ke Current Instruction Register (CIR). Setelah itu, Program Counter akan meningkat menjadi 103. Pada tahap ini, seringkali terdapat instruksi "halt" atau "stop" yang menandakan akhir dari program.

![decode third drawio](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/0bc61d70-e7c1-429b-bbed-ad6fd59e32c7)
Dekode instruksi ketiga dan simpan instruksi tersebut dalam Unit Kontrol. Karena instruksinya adalah untuk menyimpan hasil ke alamat memori 12, salin alamat memori 12 ke Memory Address Register. Kemudian, hasil dari Akumulator dipindahkan ke Memory Data Register, dan dari situ, akan dipindahkan ke lokasi memori 12. Dengan demikian, program ini selesai dieksekusi.








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








