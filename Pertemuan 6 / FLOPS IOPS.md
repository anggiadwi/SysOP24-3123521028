## Melakukan clone https://github.com/ferryastika/flops-iops

![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/3efd8e3f-3a73-4122-a306-34336db10b62)

Analisis: Git akan membuat salinan dari repositori "flops-iops" yang tersedia di GitHub ke dalam direktori lokal di komputer pengguna. Ini memungkinkan pengguna untuk memiliki salinan penuh dari repositori tersebut di komputer lokal mereka untuk digunakan, modifikasi, atau pengembangan lebih lanjut.


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

Analisis:  digunakan untuk menjalankan program atau perintah iops64 dengan argumen jumlah CPU yang ada di sistem. 

```sh
$ flops64 $(nproc)
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/42b8e8d5-3f6b-4197-8aa8-ddcc282cce72)

Analisis: digunakan untuk menjalankan program atau perintah flops64 dengan argumen jumlah CPU yang ada di sistem. Program atau perintah ini mungkin terkait dengan pengukuran atau pengujian kinerja komputasi berbasis CPU, seperti menghitung jumlah operasi floating-point per detik (FLOPS).


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







