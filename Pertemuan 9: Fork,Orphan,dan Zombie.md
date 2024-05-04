
## FORK,ORPHAN,DAN ZOMBIE

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


## Producer Consumer Problem
- Producer Consumer Problem dalam sistem operasi melibatkan dua jenis proses: produsen, yang menghasilkan data atau barang, dan konsumen, yang mengambil barang dari produsen. Keduanya berinteraksi melalui buffer bersama, bertujuan untuk mengatur produksi dan konsumsi agar tidak terjadi situasi buffer penuh atau kosong.
- Penyelesaiannya memanfaatkan teknik sinkronisasi seperti semafor atau mutex untuk mengawasi akses ke buffer, sambil memastikan efisiensi dan mencegah deadlock. Masalah ini memiliki banyak aplikasi dalam sistem operasi dan pemrograman paralel, di mana koordinasi antara proses-paroses paralel sangat penting untuk menghindari kekurangan atau kelebihan sumber daya.
