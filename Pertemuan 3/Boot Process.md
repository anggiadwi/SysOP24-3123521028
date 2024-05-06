### Boot Process:
![Untitled Diagram drawio](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/8138467d-3ef3-475e-8a7a-be24f9d65aab)


Penjelasan:



  1.Saat komputer dinyalakan, prosesor diaktifkan oleh BIOS (Basic Input/Output System). BIOS bertanggung jawab untuk melakukan inisialisasi awal pada sistem, termasuk mengaktifkan dan mempersiapkan prosesor agar siap untuk menjalankan perintah-perintah yang diberikan oleh sistem operasi. Dengan kata lain, prosesor dimulai atau diaktifkan oleh BIOS saat proses booting komputer dimulai.

2. POST (Power-on Self Test) adalah serangkaian tes otomatis yang dilakukan oleh komputer saat pertama kali dinyalakan. Tujuan dari POST adalah untuk memeriksa dan memastikan bahwa semua komponen utama dalam sistem, seperti prosesor, memori, kartu grafis, dan penyimpanan, berfungsi dengan baik. Jika ada masalah dengan salah satu komponen, POST akan menghasilkan kode kesalahan atau bunyi bip tertentu sebagai indikasi masalah yang perlu diperbaiki sebelum proses booting sistem operasi dimulai. Dengan demikian, POST membantu memastikan bahwa komputer dapat berfungsi dengan baik sebelum melanjutkan ke tahap selanjutnya dalam proses booting.

3. Windows Boot Manager adalah program boot loader yang digunakan pada sistem operasi Windows. Tugas utamanya adalah mengelola proses booting sistem, yaitu memilih dan memuat sistem operasi yang akan dijalankan pada komputer. Ketika komputer dinyalakan, Windows Boot Manager muncul dan memberikan opsi bagi pengguna untuk memilih sistem operasi yang ingin dimuat, jika ada lebih dari satu sistem operasi terinstal. Setelah pengguna memilih sistem operasi yang diinginkan, Windows Boot Manager akan memulai proses booting untuk memuat sistem operasi tersebut ke dalam memori dan menjalankannya.
4. Windows Boot Loader adalah bagian dari Windows Boot Manager yang bertanggung jawab langsung untuk memuat sistem operasi Windows ke dalam memori komputer saat proses booting. Ini adalah komponen yang menjalankan instruksi-instruksi yang diperlukan untuk memulai kernel sistem operasi dan menginisialisasi proses booting. 
5. Loading Windows Kernel, terutama ntoskrnl.exe, adalah tahap penting dalam proses booting sistem operasi Windows. Ntoskrnl.exe adalah singkatan dari "NT Operating System Kernel," yang merupakan inti dari sistem operasi Windows. Saat proses booting, setelah Windows Boot Loader memuat berkas-berkas sistem yang diperlukan, seperti sistem file dan driver, kernel Windows (ntoskrnl.exe) dimuat ke dalam memori.
6. Windows Executable adalah format berkas yang digunakan oleh sistem operasi Windows untuk menyimpan program yang dapat dijalankan (executable program). Format berkas ini memiliki ekstensi .exe dan dapat berisi kode program, data, dan sumber daya lain yang diperlukan oleh program tersebut.
7. Winlogon.exe adalah proses sistem yang sangat penting yang bertanggung jawab atas manajemen login pengguna dan mengatur urutan perhatian yang aman (SAS), yang mencakup tindakan seperti mengunci komputer atau memulai Task Manager. Ini juga berperan dalam mengelola desktop aman, di mana operasi sensitif seperti memasukkan sandi atau prompt UAC (User Account Control) terjadi.
Sebagai salah satu proses awal yang dimulai selama boot, winlogon.exe memastikan bahwa pengguna dapat login secara aman ke sistem dan memulai sesi pengguna, memberikan landasan bagi proses dan layanan lainnya untuk berjalan dalam sesi tersebut. Oleh karena itu, winlogon.exe dianggap sebagai salah satu komponen awal yang penting dalam urutan booting Windows.

**Mengidentifikasi Laptop melalui aplikasi CPU-Z**

- Spesifikasi CPU
  
![1](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/a21202a2-05ac-43fb-b541-59d5341bf111)

Analisis:

Tab CPU memuat informasi prosesor, core speed, dan cache.

- prosesor : menggunakan processor Intel core i5 4200u Menampilkan nama dari processor yang digunakan pada laptop atau komputer

- core speed : kecepatan clock pada saat ini pada inti prosesor adalah 798.10 MHz dan bus speed yang menghubungkan prosesor ke 
  memori dan perangkat lain adalah 99.76 MHz

- cache : L1 data memiliki ukuran "2 x 32 KByte 8-way", L2 inst. memiliki ukuran "4 x 32 KByte 8-way", level 2 mememili ukuran "2 x 256 KBytes 8-way", level 3 memiliki ukuran " 3 MBytes 12-way" laptop ini menggunakan 2 cores dan 1 soket.

![2](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/12c1978d-856b-4ab9-b657-9ca9d2f29988)

Analisis:
- Tab mainboard memuat informasi matherboaerd, bios, dan graphi interface

- motherboard manufacturer yaitu Hewlett -Packard, menggunakan model 2166, spesifikasi bus yaitu PCI-Express 2.0 (5.0 GT/S), chipset motherboard menggunakan Intel Haswell-ULT  REV. 09 dan Southbridge Intel H8x/P8 REV. C1.

- BIOS menggunakan brand Insyde, versi F.67, dan dibuat pada 11/26/2014

![3](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/889761bc-9a76-4781-a8c0-fda328252d55)

Analisis:
- tab memory memuat informasi general dan timings

- general laptop ini menngunakan type memory DDR3 yang berukuran 4 GBytes

- Timings clok speed memori 665.1 MHz dengan rasio FSB dan DRAM adalah 1:5

![4](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/a4a4ba05-33ef-4698-9c1f-ff034f3abd68)

Analisis:
tab SPD memuat informasi memory slot selection pada laptop ini terpasang 1 slot memory yang berukuran 2 GBytes, model manuf SK Hynik

![5](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/3b53cc29-887a-49c0-8edc-27014d3d322e)

Analisis:
tab Graphiscs memuat informasi GPU dan kapasitas memory laptop ini menggunaka GPU Intel HD Graphics Family dengan Hewlett-Packard

![6](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/471b9acd-748f-448e-b5bc-a8c3ad85146a)

Analisis:
tab Bench memuat informasi bahwa laptop ini menggunakan bancmark versi 17.01.64
![7](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/5634c90e-3e08-4260-b99b-6413674c19ec)

Analisis:
tab about memuat informasi tentang CPUID dan laptop ini menggunakan Microsoft Windows 10 Professional (x64), version 21H2, Build 190044.1415 Directx 12.0
