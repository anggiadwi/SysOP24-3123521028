## Perbedaan RICS dan CICS

Fokus utama dari RICS adalah pada sistem komunikasi real-time yang mendukung transfer data dan informasi secara langsung dan tepat waktu antara berbagai entitas atau komponen dalam sebuah sistem. RICS digunakan dalam konteks di mana komunikasi real-time diperlukan, seperti dalam sistem kontrol industri, jaringan sensor, telekomunikasi, dan IoT (Internet of Things).Sedangkan Fokus utama dari CICS adalah pada sistem pengolahan transaksi yang menangani sejumlah besar transaksi bisnis dalam lingkungan mainframe. CICS digunakan terutama dalam aplikasi bisnis yang memerlukan pemrosesan transaksi besar-besaran, seperti perbankan, penjualan ritel, perusahaan asuransi, dan sektor keuangan lainnya.

- Fungsi dan Fitur:
RICS: RICS menyediakan fitur dan fungsi yang dirancang khusus untuk mendukung komunikasi real-time, seperti mekanisme pengiriman pesan, manajemen kejadian, sinkronisasi data, dan toleransi kesalahan. Ini juga dapat mencakup protokol komunikasi real-time seperti MQTT, OPC UA, dan lainnya.
CICS: CICS menyediakan fitur dan fungsi yang terkait dengan pengelolaan transaksi, termasuk pemrosesan batch, pemrosesan online, manajemen memori, manajemen keamanan, pemantauan kinerja, dan sebagainya.

- Lingkungan Operasional:
RICS: RICS dapat beroperasi dalam berbagai lingkungan, termasuk sistem embedded, jaringan komputer, sistem real-time, dan IoT.
CICS: CICS terutama dioperasikan dalam lingkungan mainframe IBM, meskipun ada penerapan CICS yang berjalan pada platform non-mainframe.

## Hubungan Arsitektur CPU dengan Arsitektur OS
Arsitektur CPU dan arsitektur sistem operasi memiliki keterkaitan yang erat dan saling mempengaruhi dalam pengembangan sistem komputer yang efisien dan andal. Perubahan dalam arsitektur CPU dapat mempengaruhi cara sistem operasi diimplementasikan, dan sebaliknya, peningkatan dalam sistem operasi dapat memanfaatkan fitur-fitur baru yang disediakan oleh CPU.

**-Instruksi dan Operasi CPU:** Arsitektur CPU menentukan set instruksi dan operasi dasar yang dapat dilakukan oleh CPU. Sistem operasi kemudian harus ditulis atau disesuaikan agar kompatibel dengan set instruksi yang didukung oleh CPU tersebut. Misalnya, jika CPU mendukung instruksi SIMD (Single Instruction, Multiple Data), sistem operasi dan aplikasi dapat memanfaatkan fitur ini untuk meningkatkan kinerja pemrosesan data paralel.

**-Mode dan Pengaturan CPU:** Arsitektur CPU memiliki mode operasi yang dapat dikonfigurasi oleh sistem operasi. Misalnya, mode pengguna (user mode) dan mode supervisor (kernel mode) adalah mode operasi yang umum pada CPU modern. Sistem operasi menggunakan mode supervisor untuk menjalankan tugas-tugas yang memerlukan akses langsung ke perangkat keras dan memastikan keamanan dan integritas sistem.

**-Penjadwalan dan Manajemen Sumber Daya:** Arsitektur sistem operasi bergantung pada fitur-fitur yang disediakan oleh CPU untuk melakukan penjadwalan proses, manajemen memori, manajemen perangkat I/O, dan manajemen sumber daya lainnya. CPU dengan fitur-fitur seperti multiple core, hyperthreading, dan cache memory memungkinkan sistem operasi untuk mengimplementasikan strategi penjadwalan yang lebih canggih dan efisien.

**-Interrupt dan Exception Handling:** CPU memiliki mekanisme untuk menghandle interrupt dan exception, yang digunakan oleh sistem operasi untuk menanggapi peristiwa luar biasa seperti permintaan I/O, kesalahan, atau interupsi perangkat keras. Sistem operasi harus dapat memprogram dan mengelola interrupt dan exception dengan baik untuk memastikan kinerja sistem yang stabil dan andal.

**-**Interaksi dengan Perangkat Keras:**** Arsitektur sistem operasi bergantung pada antarmuka perangkat keras (hardware interface) yang disediakan oleh CPU. Ini termasuk instruksi-instruksi untuk berinteraksi dengan perangkat keras, seperti mengirimkan dan menerima data dari perangkat I/O, mengakses memori, dan melakukan operasi lainnya.

**-**Optimasi Kinerja:**** Sistem operasi sering melakukan optimasi kinerja yang spesifik untuk arsitektur CPU tertentu. Hal ini dapat mencakup strategi penjadwalan yang dioptimalkan untuk jumlah core tertentu, pengaturan cache yang dioptimalkan, dan pemanfaatan fitur-fitur khusus CPU lainnya.

## FORK

![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/abc63d9a-1d8b-467e-a642-3e73bd52021b)

```
$ su root
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install g++
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/f3fdaec0-0831-4b5e-9c87-9d42759752e8)

![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/cf1a6af2-967a-4d6d-8786-15fd422695ae)

- Kembali menjadi User
```sh
$ login [username]
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/028bdbbd-0434-43eb-9bbb-ec157575b2bb)

-Masuk ke cd operatingsystem
```sh
$ cd operatingsystem
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/64323030-181f-427b-8a6a-1877adecffa3)

```sh
fork01.cpp
```
-Masuk ke compiler
```sh
$ nano [namafile].cpp
```

-memasukkan kode fork01.cpp
```sh
using namespace std;

#include <iostream>
#include <sys/types.h>
#include <unistd.h>


/* getpid() adalah system call yg dideklarasikan pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
   pid_t mypid;
   uid_t myuid;
   for (int i = 0; i < 3; i++) {
   	mypid = getpid();
   	cout << "I am process " << mypid << endl;
   	cout << "My parent process ID is " << getppid() << endl;
   	cout << "The owner of this process has uid " << getuid()
   << endl;
/* sleep adalah system call atau fungsi library
yang menghentikan proses ini dalam detik
*/
   sleep(3);
   }
return 0;
}
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/9dc12365-59a2-4a83-a9ee-b67bd426bd00)

- kemudian simpan file dengan ctrl+x
- mengubah file.cpp menjadi exe
```sh
$ g++ [namafile].cpp -o [namafile].exe
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/d8999293-51b5-4857-a6a3-af4ed0157105)

- kemudian menjalankan kode
```sh
$ ./[namafile].exe
```
- hasil
  ![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/f6572437-91dc-4b42-9c82-005326d2a329)

```sh
fork02.cpp
```
- Masukkan ke compiler
```sh
$ nano [namafile].cpp
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/a819e3d7-e9e3-45d3-aa19-d4c8ee9ce8ae)

- Memasukkan kode fork02.cpp
```sh
      #include <iostream>
#include <sys/types.h>
#include <unistd.h>
using namespace std;


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
   pid_t childpid;
   int x = 5;
   childpid = fork();

   while (1) {
   	cout << "This is process ID" << getpid() << endl;
   	cout << "In this process the value of x becomes " << x << endl;	
   	sleep(2);
   	x++;
   }
   return 0;
}
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/74807299-c3b1-48c5-bb1f-5d26a15230f3)

- kemudian simpan file dengan ctrl + x
- mengubah file.cpp menjadi .exe
```sh
   $ g++ [namafile].cpp -o [namafile].exe
```
- kemudian menjalankan kode
```sh
$ ./[namafile].exe
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/c5468e52-d50b-4dd8-921a-2b804fe3b622)

- untuk menghentikan proses tekan ctrl + c
```sh
fork03.cpp
```
- Masuk ke compiler
```sh
$ nano [namafile].cpp
```
- memasukkan kode fork03.cpp
```sh
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
   pid_t childpid;
   childpid = fork();
   for (int i = 0; i < 5; i++) {
   	cout << "This is process " << getpid() << endl;
   	sleep(2);
   }
   return 0;
}
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/ab909a68-8ace-4bbf-80d1-83ba662b373b)

- kemudian simpan file dengan ctrl + x
- mengubah file.cpp menjadi .exe
```sh
$ g++ [namafile].cpp -o [namafile].exe
```
- kemudian menjalankan kode
```sh
$ ./[namafile].exe
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/4bc4ccea-9cf7-4443-8c5b-01bd188b25f7)


```sh
Orphan
```
-Masuk ke compiler
```sh
$ nano [namafile].c
```
- memasukkan kode orphan
```sh
 #include <stdio.h>
#include <sys/types.h>
#include <unistd.h>

int main()
{
   // fork() Create a child process

   int pid = fork();
   if (pid > 0)
   {
   	//getpid() returns process id
   	// while getppid() will return parent process id
   	printf("Parent process\n");
   	printf("ID : %d\n\n",getpid());
   }
   else if (pid == 0)
   {
   	printf("Child process\n");
   	// getpid() will return process id of child process
   	printf("ID: %d\n",getpid());
   	// getppid() will return parent process id of child process
   	printf("Parent -ID: %d\n\n",getppid());

   	sleep(10);

   	// At this time parent process has finished.
   	// So if u will check parent process id 
   	// it will show different process id
   	printf("\nChild process \n");
   	printf("ID: %d\n",getpid());
   	printf("Parent -ID: %d\n",getppid());
   }
   else
   {
   	printf("Failed to create child process");
   }
   
   return 0;
}

/* https://www.includehelp.com/c-programs/orphan-process.aspx */
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/7771cea0-1479-4e97-8586-4d1a73558b1a)

- kemudian simpan file dengan ctrl + x
- mengubah file.cpp menjadi exe
```sh
   $ g++ [namafile].c -o [namafile].exe
```
- kemudian menjalankan kode
```sh
$ ./[namafile].exe
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/55145fac-c102-4a97-8e63-58d6c56d879e)

- untuk menghentikan proses tekan ctrl + c
```sh
Zombie
```
- masuk ke compiler
```sh
$ nano [namafile].c
```
- memasukkan kode zombie
```sh
        #include <iostream>
#include <sys/types.h>
#include <unistd.h>
using namespace std;


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
   pid_t childpid;
   int x = 5;
   childpid = fork();

   while (1) {
   	cout << "This is process ID" << getpid() << endl;
   	cout << "In this process the value of x becomes " << x << endl;	
   	sleep(2);
   	x++;
   }
   return 0;
}
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/a7c03651-778e-49ae-9139-a630914e6526)

- kemudian simpan file dengan ctrl + x
- mengubah file.cpp menjadi .exe
```sh
   $ g++ [namafile].c -o [namafile].exe
```
- kemudian menjalankan kode
```sh
$ ./[namafile].exe
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/927daf71-07b3-4fa6-84a9-27e5b90511a5)

  - untuk menghentikan proses tekan ctrl + c
  
  
      








