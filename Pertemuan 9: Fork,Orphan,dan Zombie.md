
## FORK,ORPHAN,DAN ZOMBIE

![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/abc63d9a-1d8b-467e-a642-3e73bd52021b)

Analisis: 
$ git clone https://github.com/ferryastika/operatingsystem.git: Perintah ini digunakan untuk mengkloning repositori "operatingsystem" dari GitHub ke direktori lokal Anda.
$ cd operatingsystem: Perintah ini digunakan untuk pindah ke direktori "operatingsystem" yang baru saja Anda kloning.
$ ls: Perintah ini digunakan untuk menampilkan daftar file dan direktori di direktori saat ini, dalam hal ini, direktori "operatingsystem".

```
$ su root
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install g++
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/f3fdaec0-0831-4b5e-9c87-9d42759752e8)

![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/cf1a6af2-967a-4d6d-8786-15fd422695ae)

Analisis:

Perintah di atas adalah sebagai berikut:

$ su root: Perintah ini digunakan untuk beralih ke akun superuser (root) di sistem Linux. Ini memungkinkan Anda untuk menjalankan perintah dengan hak akses superuser.
$ sudo apt update: Perintah ini digunakan untuk memperbarui daftar paket yang tersedia dari repositori paket yang terpasang pada sistem Anda. Ini akan memperbarui informasi tentang paket-paket yang ada sehingga Anda dapat menginstal versi terbaru dari paket-paket tersebut.
$ sudo apt upgrade: Perintah ini digunakan untuk meng-upgrade semua paket yang telah diinstal ke versi terbaru yang tersedia dari repositori paket yang terpasang pada sistem Anda.
$ sudo apt install g++: Perintah ini digunakan untuk menginstal paket g++, yang merupakan kompiler C++ untuk Linux. Ini akan memasang semua paket yang diperlukan untuk menginstal dan menjalankan g++ di sistem Anda.

- Kembali menjadi User
```sh
$ login [username]
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/028bdbbd-0434-43eb-9bbb-ec157575b2bb)

Analisis:
Perintah $ login [username] digunakan untuk melakukan login ke sistem dengan akun pengguna yang ditentukan. 

-Masuk ke cd operatingsystem
```sh
$ cd operatingsystem
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/64323030-181f-427b-8a6a-1877adecffa3)

Analisis:
Perintah $ cd operatingsystem digunakan untuk berpindah ke direktori operatingsystem.

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

Analisis: 
Perintah $ nano [namafile].cpp digunakan untuk membuka atau membuat file baru dengan menggunakan editor teks nano. Setelah membuka file, pengguna dapat memasukkan kode program atau melakukan pengeditan pada file tersebut.

- kemudian simpan file dengan ctrl+x
- mengubah file.cpp menjadi file
```sh
$ g++ [namafile].cpp -o [namafile]
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/d8999293-51b5-4857-a6a3-af4ed0157105)

Analisis:Perintah $ g++ [namafile].cpp -o [namafile].exe digunakan untuk mengkompilasi kode sumber C++ yang disimpan dalam file [namafile].cpp menjadi sebuah file eksekusi yang dapat dijalankan. 

- kemudian menjalankan kode
```sh
$ ./[namafile]
```
- hasil
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/958f2012-3dc7-4df3-85dd-737fe05617c3)

Analisis:Perintah $ ./[namafile].exe digunakan untuk menjalankan file eksekusi yang telah dikompilasi sebelumnya.

```sh
fork02.cpp
```
- Masukkan ke compiler
```sh
$ nano [namafile].cpp
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/a819e3d7-e9e3-45d3-aa19-d4c8ee9ce8ae)

Analisis: Perintah $ nano [namafile].cpp digunakan untuk membuka atau membuat file baru dengan menggunakan editor teks nano.

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

Analisis:Kode menggunakan fork() untuk membuat proses baru.
Saat fork() dipanggil, sistem akan membuat salinan dari proses pemanggilan. Proses salinan ini disebut sebagai anak, sedangkan proses pemanggilan asli disebut sebagai induk.Kedua proses akan mengeksekusi pernyataan dalam loop while secara independen satu sama lain.Setiap proses akan menampilkan PID-nya sendiri menggunakan getpid().Nilai variabel x akan terus bertambah di setiap proses, namun proses anak dan induk memiliki salinan variabel x yang terpisah satu sama lain.



- kemudian simpan file dengan ctrl + x
- mengubah file.cpp menjadi file
```sh
   $ g++ [namafile].cpp -o [namafile]
```
- kemudian menjalankan kode
```sh
$ ./[namafile]
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/b098d0ef-8e64-4ad5-9580-663be992c0b4)

Analisis: 
Pada kode fork02.cpp, kita memiliki program sederhana yang menggunakan fork() untuk membuat proses baru. Setiap proses, baik induk maupun anak, akan menampilkan PID (Process ID) dan nilai variabel x setiap 2 detik.

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
Analisis:
Saat kode dijalankan, fungsi fork() dipanggil, membuat proses anak.
Jika proses anak tercipta, maka proses induk dan proses anak akan menjalankan loop yang mencetak PID mereka sendiri secara bergantian.
Setiap proses mencetak PID-nya sendiri menggunakan getpid() dan menunggu selama 2 detik menggunakan sleep(2).
Loop ini diulangi lima kali, sehingga total akan ada sepuluh cetakan PID (lima dari proses induk dan lima dari proses anak).
- kemudian simpan file dengan ctrl + x
- mengubah file.cpp menjadi file
```sh
$ g++ [namafile].cpp -o [namafile]
```
- kemudian menjalankan kode
```sh
$ ./[namafile]
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/006a2fdd-efd5-40bf-9346-7bbbf2b765b7)

Analisis:Pada kode fork03.cpp, kita memiliki program yang menggunakan fork() untuk membuat proses anak. Setelah proses anak tercipta, kedua proses (induk dan anak) akan mencetak PID mereka sendiri secara bergantian selama lima kali, dengan jeda waktu 2 detik setiap cetakan.

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

Analisis:Saat kode dijalankan, fungsi fork() dipanggil, membuat proses anak.
Jika proses anak tercipta (pid == 0), maka pesan "Child process" akan dicetak, diikuti dengan mencetak PID dan PID induk dari proses anak.
Proses anak kemudian memasuki sleep(10), menghentikan eksekusi selama 10 detik.
Selama proses anak tertidur, proses induk selesai eksekusi.
Setelah 10 detik, proses anak akan mencetak PID-nya dan PID induknya lagi. Karena proses induk sudah selesai, PID induk yang dicetak adalah PID dari proses init, bukan proses induk asli.
Jika proses anak tidak tercipta (pid > 0), maka pesan "Parent process" akan dicetak, diikuti dengan mencetak PID dari proses induk.
Jika gagal membuat proses anak (pid < 0), pesan "Failed to create child process" akan dicetak.
Kode ini memberikan contoh tentang bagaimana proses anak dapat menjadi "anak yatim piatu" atau "anak angkat" setelah proses induk selesai eksekusi. Proses anak tetap berjalan, dikelola oleh proses init (biasanya PID 1), meskipun proses induk sudah selesai.

- kemudian simpan file dengan ctrl + x
- mengubah file.cpp menjadi file
```sh
   $ g++ [namafile].c -o [namafile]
```
- kemudian menjalankan kode
```sh
$ ./[namafile]
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/2d8fce92-cf68-4b17-bcfb-e1f69155b521)


Analisis:Pada kode orphan, kita memiliki program yang menggunakan fork() untuk membuat proses anak. Proses induk kemudian segera selesai eksekusi, sementara proses anak tetap berjalan setelah proses induk selesai.

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

Analisis:
Saat kode dijalankan, fungsi fork() dipanggil, membuat proses anak.
Jika proses anak tercipta, maka proses anak akan menjalankan loop yang mencetak PID-nya sendiri dan nilai x dengan jeda waktu 2 detik.
Proses induk tidak melakukan apapun setelah menciptakan proses anak, sehingga tidak menunggu proses anak selesai.
Karena proses induk tidak menunggu proses anak selesai, maka setelah proses anak selesai dijalankan, namun proses induk belum mengambil status exit dari proses anak, proses anak akan menjadi zombie.
Proses anak akan tetap menjadi zombie sampai proses induk mengambil status exit dari proses anak menggunakan wait() atau waitpid().
Penggunaan wait() atau waitpid() sangat penting untuk menghindari terjadinya zombie processes dalam sistem operasi karena proses zombie dapat menyebabkan penumpukan sumber daya sistem yang tidak perlu.

- kemudian simpan file dengan ctrl + x
- mengubah file.cpp menjadi file
```sh
   $ g++ [namafile].c -o [namafile]
```
- kemudian menjalankan kode
```sh
$ ./[namafile]
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/3e60d87c-7cd1-4c48-adc4-6302445c1d28)


Analisis:
Pada kode zombie, kita memiliki program yang menggunakan fork() untuk membuat proses anak. Namun, perbedaannya dengan kode sebelumnya adalah bahwa tidak ada panggilan ke fungsi wait() atau waitpid() untuk menunggu proses anak selesai. Akibatnya, proses anak akan menjadi zombie setelah selesai dijalankan.

  - untuk menghentikan proses tekan ctrl + c


## Producer Consumer Problem
- Producer Consumer Problem dalam sistem operasi melibatkan dua jenis proses: produsen, yang menghasilkan data atau barang, dan konsumen, yang mengambil barang dari produsen. Keduanya berinteraksi melalui buffer bersama, bertujuan untuk mengatur produksi dan konsumsi agar tidak terjadi situasi buffer penuh atau kosong.
- Penyelesaiannya memanfaatkan teknik sinkronisasi seperti semafor atau mutex untuk mengawasi akses ke buffer, sambil memastikan efisiensi dan mencegah deadlock. Masalah ini memiliki banyak aplikasi dalam sistem operasi dan pemrograman paralel, di mana koordinasi antara proses-paroses paralel sangat penting untuk menghindari kekurangan atau kelebihan sumber daya.
