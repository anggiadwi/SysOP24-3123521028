## Tugas Pendahuluan
1.Apa yang dimaksud redirection?
Redirection adalah proses mengalihkan aliran masukan atau keluaran dari atau ke suatu sumber daya tertentu di dalam sistem operasi atau lingkungan perintah. Dalam konteks sistem operasi atau lingkungan perintah seperti Unix, Linux, dan Windows Command Prompt, redirection digunakan untuk mengontrol aliran data antara program, file, atau perangkat lainnya.
2. Apa yang dimaksud pipeline?
Pipeline adalah konsep dalam sistem operasi dan lingkungan perintah yang memungkinkan output dari satu perintah atau program untuk menjadi masukan dari perintah atau program berikutnya secara berurutan.
3. Apa yang dimaksud perintah di bawah ini : echo, cat, more, sort, grep, wc, cut, uniq

- echo: Perintah echo digunakan untuk mencetak teks atau variabel ke layar atau ke output standar. 
- cat: Perintah cat (concatenate) digunakan untuk menggabungkan dan menampilkan isi dari satu atau beberapa file ke output standar (biasanya terminal). Ini juga dapat digunakan untuk membuat file baru atau menggabungkan beberapa file menjadi satu.
- more: Perintah more digunakan untuk menampilkan isi dari sebuah file secara bertahap pada terminal. Ini memungkinkan pengguna untuk melihat isi file satu layar pada satu waktu dan melanjutkan ke baris berikutnya dengan menekan spasi.
- sort: Perintah sort digunakan untuk mengurutkan baris-baris teks dari sebuah file atau dari input standar. Ini dapat mengurutkan baris berdasarkan urutan alfanumerik atau berdasarkan kriteria tertentu yang ditentukan oleh pengguna.
- grep: Perintah grep digunakan untuk mencari teks tertentu dalam file atau input standar. Ini mencocokkan pola teks yang diberikan oleh pengguna dan menampilkan baris-baris yang cocok.
- wc: Perintah wc (word count) digunakan untuk menghitung jumlah baris, kata, dan karakter dalam sebuah file atau input standar. 
- cut: Perintah cut digunakan untuk memotong dan mengekstrak bagian tertentu dari baris-baris teks dalam sebuah file atau dari input standar.
- uniq: Perintah uniq digunakan untuk menghapus baris-baris yang duplikat dari sebuah file atau dari input standar. Ini berguna untuk membersihkan dan memproses data yang memiliki duplikat.

## PERCOBAAN

## Percobaan 1: File Descriptor
### 1.Output ke layar (standar output), input dari system (kernel)
```sh
$ ps
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/2ae9f5bb-7b5a-44f2-80e4-bda013c73c35)

Analisis:Perintah ps adalah perintah di sistem operasi Unix dan Unix-like (termasuk Debian) yang digunakan untuk menampilkan informasi tentang proses yang sedang berjalan di sistem. 

### 2.Output ke layar (standar output), input dari keyboard (standard input)
```sh
$ cat
 hallo, apa khabar
 hallo, apa khabar
 exit dengan ^d
 exit dengan ^d
 [Ctrl-d]
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/13514241-35c5-427b-954a-6f13bb1c63c9)

Analisis:Perintah cat untuk menampilkan isi dari satu atau beberapa file ke output standar (biasanya terminal), ini menunjukkan beberapa teks yang dicetak ke terminal. Ketika Anda mencetak "hallo, apa khabar" dua kali, itu hanya mencetak string tersebut ke output terminal. Kemudian, Anda mencetak "exit dengan ^d" dua kali, yang menunjukkan instruksi kepada pengguna untuk keluar dengan menekan Ctrl + D.

### 3.Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
```sh
$ mkdir mydir
$ mkdir mydir **(Terdapat pesan error)**
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/6641f929-64e1-4927-b18b-3c1b522fe5a0)

Analisis: jika anda mendapatkan pesan error saat mencoba menjalankan perintah mkdir mydir di Debian, kemungkinan besar ada beberapa penyebab yang mungkin terjadi.

- Perizinan yang Tidak Mencukupi: Jika Anda tidak memiliki izin yang cukup untuk membuat direktori di lokasi yang ditentukan, Anda akan mendapatkan pesan error.
- Direktori yang Sudah Ada: Jika direktori dengan nama yang sama sudah ada di lokasi yang dituju, maka Anda akan menerima pesan kesalahan. 
- Lokasi yang Tidak Valid: Jika lokasi yang Anda tentukan tidak valid atau tidak dapat diakses (misalnya, mencoba membuat direktori di dalam direktori yang tidak ada), Anda akan mendapatkan pesan error. 
- Kuota Penyimpanan Penuh: Jika kuota penyimpanan penuh, sistem tidak akan dapat membuat direktori baru. 
- Kesalahan Sistem atau Perangkat Keras: Terkadang, pesan error mungkin disebabkan oleh masalah sistem atau perangkat keras.
- Kesalahan Tersirat: Pesan error mungkin memberikan petunjuk lebih lanjut tentang penyebab spesifik dari kegagalan pembuatan direktori.

## Percobaan 2: Pembelokan(redirection)
### 1. Pembelokan Standar Output
```sh
 $ cat 1> myfile.txt
 Ini adalah teks yang saya simpan ke file myfile.txt
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/aad99d4c-1b71-4bcc-b423-0ea03bcda3f9)

Analisis :ketika menjalankan perintah cat 1> myfile.txt dalam Debian dan kemudian memasukkan teks melalui keyboard (misalnya "Ini adalah teks yang saya simpan ke file myfile.txt"), teks tersebut akan disimpan dalam file myfile.txt di direktori kerja saat ini.


### 2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
```sh
 $ cat 0< myfile.txt
 $ cat myfile.txt```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/7c339da3-3f4f-4c2e-9ce9-9e90f3fdb400)

Analisis: ketika menjalankan perintah cat 0< myfile.txt dalam Debian, cat akan membaca konten dari file myfile.txt dan mencetaknya ke output standar (biasanya terminal).Hasilnya akan sama dengan menjalankan cat myfile.txt, karena pada dasarnya keduanya melakukan hal yang sama: membaca isi file myfile.txt dan mencetaknya ke output standar.

### 3. Pembelokan standar error untuk disimpan di file
```sh
 $ mkdir mydir (Terdapat pesan error)
 $ mkdir mydir 2> myerror.txt
 $ cat myerror.txt
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/6733adad-a79f-4c41-ba28-cd747078e800)

Analisis:dengan menjalankan perintah-perintah tersebut, Anda mencoba membuat direktori "mydir", dan jika ada pesan kesalahan, itu akan ditangkap dan disimpan dalam file myerror.txt. Kemudian, Anda mencetak isi file myerror.txt untuk melihat pesan kesalahan tersebut.

### 4. Notasi 2>&1 : pembelokan standar error(2>) adalh identik dengan file descriptor 1.
```sh
 $ ls filebaru (Terdapat pesan error)
 $ ls filebaru 2> out.txt
 $ cat out.txt
 $ ls filebaru 2> out.txt 2>&
 $ cat out.txt
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/48495a89-5815-47c8-96d2-f5f4b5d32348)

Analisis: dengan menjalankan perintah-perintah tersebut, Anda mencoba untuk menangkap pesan kesalahan yang dihasilkan oleh perintah ls dan menyimpannya dalam file out.txt. Jika ada kesalahan, Anda dapat melihatnya dengan menjalankan perintah cat out.txt. 

###  5. Notasi 1>&2(atau>&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
```sh
$ echo “mencoba menulis file” 1> baru
$ cat filebaru 2> baru 1>&
$ cat baru
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/88001e73-8e93-4710-8242-87a2d3c94753)

Analisis:

- $ echo “mencoba menulis file” 1> baru:
Ini adalah perintah untuk menulis teks "mencoba menulis file" ke dalam file bernama "baru". Penulisan dilakukan dengan menggunakan output redirection 1>, yang mengarahkan output dari perintah echo (STDOUT) ke file "baru".

- $ cat filebaru 2> baru 1>&:
Perintah ini memiliki kesalahan sintaks, karena tidak ada target yang ditentukan untuk mengalihkan output kesalahan (STDERR) atau output standar (STDOUT). Penggunaan 1>& dan 2> tanpa target adalah sintaks yang tidak valid. Oleh karena itu, perintah ini akan menghasilkan pesan kesalahan sintaks dan tidak akan berhasil menangkap atau menampilkan apa pun.

- $ cat baru:
Dalam perintah ini, cat mencetak isi dari file "baru" ke output standar, yang dalam hal ini adalah terminal. Jika perintah echo sebelumnya berhasil menulis teks ke dalam "baru", Anda akan melihatnya dengan menjalankan perintah ini. Namun, jika "baru" kosong, maka Anda tidak akan melihat keluaran apa pun.

###  6.  Notasi>>(append)
```sh
$ echo “kata pertama” > surat
$ echo “kata kedua” >> surat
$ echo “kata ketiga” >> surat
$ cat surat
$ echo “kata keempat” > surat
$ cat surat
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/c4077fc1-f058-4738-9f85-725531523ac4)

Analisis:

- $ echo “kata pertama” > surat:
Ini adalah perintah untuk menulis teks "kata pertama" ke dalam file bernama "surat". Penulisan dilakukan dengan menggunakan output redirection >, yang mengarahkan output dari perintah echo (STDOUT) ke file "surat". Jika file "surat" sudah ada sebelumnya, kontennya akan ditimpa dengan teks baru.

- $ echo “kata kedua” >> surat:
Perintah ini menulis teks "kata kedua" ke dalam file "surat" dengan menggunakan output redirection >>. Tanda >> digunakan untuk menambahkan teks ke akhir file "surat" tanpa menghapus konten sebelumnya.

- $ echo “kata ketiga” >> surat:
Ini adalah perintah yang sama dengan sebelumnya, yang menambahkan teks "kata ketiga" ke akhir file "surat".

- $ cat surat:
Perintah ini digunakan untuk mencetak isi dari file "surat" ke output standar, yang dalam hal ini adalah terminal. Dengan menjalankan perintah ini, Anda akan melihat semua teks yang ditambahkan sebelumnya ke dalam "surat".

- $ echo “kata keempat” > surat:
Perintah ini kembali menulis teks "kata keempat" ke dalam file "surat", tetapi menggunakan output redirection >. Ini akan menimpa semua konten sebelumnya dalam file "surat" dengan teks baru.

- $ cat surat:
Perintah ini digunakan untuk mencetak isi dari file "surat" ke output standar. Namun, setelah perintah sebelumnya, isi "surat" akan diganti dengan "kata keempat" saja.

### 7. Notasi here document (<<++....++) digunakan sebagaii pembatas input dari keyboard. Perhatikan bahwa tanda pembtas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris.
```sh
$ cat <<++
Hallo, apa kabar?
Baik-baik saja?
Ok!
++
$ cat <<%%%
Hallo, apa kabar?
Baik-baik saja?
Ok!
%%%
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/df91566c-ac76-409b-980e-4b8649ac5fba)

Analisis: Perintah cat <<++ dan cat <<%%% adalah contoh dari penggunaan heredoc dalam shell script. Heredoc adalah cara untuk menulis blok teks panjang di dalam skrip shell tanpa harus menggunakan tanda kutip ganda atau tunggal.

### 8. Notasi-(input keyboard) adalah input dari keyboard. Artinya menampilkan file 1,kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi "-" berarti menyelipkan input dari keyboard
```sh
$ cat myfile.txt – surat
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/7791b522-34f2-4ee2-aecb-7fafe93311dc)

 Analisis:Dengan perintah di atas, cat akan menggabungkan isi dari myfile.txt dan surat, lalu menampilkannya di terminal.

## Percobaan 3: Pipe(pipeline)
### 1. Operator Pipa(|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
```sh
$ who
$ who | sort
$ who | sort –r
$ who > tmp
$ sort tmp
$ rm tmp
$ ls –l /etc | more
$ ls –l /etc | sort | more
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/b3990dfc-1f8c-4512-bb27-505d4d0d04ff)

![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/ba366166-0ad0-4478-964f-1ad4d7ca0b53)

![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/eee39e1d-81a0-4538-b0e6-f505d04f6330)

Analisis:

- $ who:
 Perintah ini digunakan untuk menampilkan informasi tentang pengguna yang saat ini login ke sistem.
 
- $ who | sort:
 Perintah ini menggunakan output dari perintah who sebagai input untuk perintah sort. Ini akan mengurutkan output dari perintah who berdasarkan urutan alfabetis dari nama pengguna.
 
- $ who | sort –r:
 Ini hampir sama dengan perintah sebelumnya, namun opsi -r digunakan untuk mengurutkan secara terbalik (berdasarkan urutan alfabetis dari nama pengguna secara terbalik).
 
- $ who > tmp:
 Perintah ini akan mengalihkan output dari perintah who ke file bernama "tmp".
 
- $ sort tmp:
 Perintah ini akan mengurutkan isi dari file "tmp" yang berisi output dari perintah who. Ini akan mencetak hasil pengurutan ke terminal.
 
- $ rm tmp:
 Ini adalah perintah untuk menghapus file "tmp" yang telah dibuat sebelumnya.
 
- $ ls –l /etc | more:
 Perintah ini akan menampilkan daftar isi dari direktori "/etc" dengan rincian informasi menggunakan format panjang, dan kemudian mengalihkan outputnya ke perintah more untuk memungkinkan penampilan per halaman.
 
- $ ls –l /etc | sort | more:
 Perintah ini melakukan hal yang sama dengan perintah sebelumnya, namun sebelum ditampilkan dengan more, output dari perintah ls -l /etc diurutkan menggunakan perintah sort.
-

### 2. Untuk membelokkan standart output ke file,digunakan operator">"
```sh
$ echo hello
$ echo hello > output
$ cat output
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/9af69a76-96d9-4ecd-a10d-ab1a4a0030ae)

Analisis:  secara keseluruhan, urutan perintah tersebut mencetak kata "hello" di terminal, kemudian menulis kata "hello" ke dalam file "output", dan akhirnya mencetak isi dari file "output" di terminal lagi.

###3. Untuk menambahkan output ke file digunakan operator"> >"
```sh
$ echo bye >> output
$ cat output
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/71232622-0bed-42dc-bd6c-0d680a552d54)
Analisis:

- $ echo bye >> output:
Ini adalah perintah yang menambahkan teks "bye" ke akhir file "output" menggunakan operator append >>. Ini akan menambahkan "bye" sebagai baris baru di bawah "hello" dalam file "output".

- $ cat output:
Ini adalah perintah yang digunakan untuk mencetak isi dari file "output" ke output standar (biasanya terminal). Ketika dieksekusi setelah perintah sebelumnya, itu akan mencetak isi dari file "output", yang akan mencakup teks "hello" (dari perintah sebelumnya) diikuti oleh "bye" (dari perintah terakhir) di baris terpisah.

### 4. Untuk membelokkan standart input digunakan operatort "<"
```sh
$ cat < output
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/b69f43d0-3d7c-4298-9b93-2a6742c0ca2f)

Analisis:

### 5.Pembelokan standart input dan standar output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebgian standart input dan output
```sh
$ cat < output > out
$ cat out
$ cat < output >> out
$ cat out
$ cat < output > output
$ cat output
$ cat < out >> out (Proses tidak berhenti)
[Ctrl-c]
$ cat out
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/a9b80ed6-d878-4571-9bd8-eb8311a97de3)
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/b228a1d0-38e5-4f9a-a9fc-92333d2c3d7c)

Analisis:

- $ cat < output > out:
 Ini adalah perintah yang mencetak isi dari file "output" ke output standar (STDOUT) dan kemudian menuliskannya ke dalam file "out". Penggunaan < digunakan untuk mengarahkan isi file "output" ke input perintah cat, dan > digunakan untuk mengalihkan output dari perintah cat ke file "out".
- $ cat out:
 Ini adalah perintah yang mencetak isi dari file "out" ke output standar (STDOUT), yang berisi teks yang sama dengan file "output".
 -$ cat < output >> out:
 Perintah ini mencetak isi dari file "output" dan menambahkannya ke akhir file "out". Penggunaan < digunakan untuk mengarahkan isi file "output" ke input perintah cat, dan >> digunakan untuk menambahkan output perintah cat ke file "out".
- $ cat out:
 Ini adalah perintah yang mencetak isi dari file "out" ke output standar (STDOUT). Setelah perintah sebelumnya, "out" akan berisi dua salinan dari teks yang sama.
- $ cat < output > output:
Perintah ini mencetak isi dari file "output" dan menimpanya dengan output yang sama. Ini artinya isi dari file "output" tetap tidak berubah.
- $ cat output:
 Ini adalah perintah yang mencetak isi dari file "output". Karena tidak ada perubahan yang dilakukan pada file "output" dalam perintah sebelumnya, isi file "output" tetap sama seperti sebelumnya.
- $ cat < out >> out:
 Ini adalah perintah yang mencoba untuk membaca isi dari file "out" dan menambahkannya ke akhir file "out". Namun, karena menggunakan file yang sama sebagai input dan output (out), ini akan menyebabkan proses berulang tak hingga. Tanda Ctrl-c digunakan untuk menghentikan proses.
- $ cat out:
 Ini adalah perintah yang mencetak isi dari file "out". Karena proses sebelumnya telah dihentikan, isi file "out" akan tetap sama seperti 
sebelumnya, yaitu dua salinan teks yang sama.

## Percobaan 4: Filter
### 1. Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
```sh
 $ w –h | grep <user>
 $ grep <user> /etc/passwd
 $ ls /etc | wc
 $ ls /etc | wc –l
 $ cat > kelas1.txt
 Badu
 Zulkifli
 Yulizir
 Yudi
 Ade
 [Ctrl-d]
 $ cat > kelas2.txt
 Budi
 Gama
 Asep
 Muchlis
 [Ctrl-d]
 $ cat kelas1.txt kelas2.txt | sort
 $ cat kelas1.txt kelas2.txt > kelas.txt
 $ cat kelas.txt | sort | uniq
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/5611e094-fa54-442d-bcdc-a2dc089e3709)
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/74ab414f-986f-42e2-b3dc-d9e9aae288ef)

Analisis:

- $ w –h | grep <user>:
Ini adalah perintah untuk menampilkan informasi login pengguna yang sedang aktif, dengan opsi -h untuk menyembunyikan header, lalu menggunakan grep untuk mencari pengguna tertentu. Namun, sintaks penggunaan grep ini tidak benar. Karakter "<" dan ">" tidak diperlukan di sini. Jika Anda ingin mencari pengguna tertentu, Anda harus menggantikan "<user>" dengan nama pengguna yang sebenarnya.

- $ grep <user> /etc/passwd:
Ini adalah perintah untuk mencari nama pengguna tertentu di file /etc/passwd. Namun, seperti sebelumnya, penggunaan <user> di sini tidak benar. Anda harus menggantikannya dengan nama pengguna yang ingin Anda cari.

- $ ls /etc | wc:
Ini adalah perintah untuk menampilkan jumlah baris, kata, dan byte dari output ls /etc. Namun, karena tidak ada pipa (|) yang digunakan di sini, perintah ini hanya akan mencetak jumlah baris, kata, dan byte dari file /etc sendiri, bukan hasil dari ls /etc.

- $ ls /etc | wc –l:
Ini adalah perintah yang benar untuk menghitung jumlah file atau direktori dalam direktori /etc. Perintah ini menggunakan ls /etc untuk menampilkan daftar file dan direktori di /etc, lalu menggunakan wc -l untuk menghitung jumlah baris dalam output tersebut, yang akan memberikan jumlah file atau direktori dalam direktori /etc.

- $ cat > kelas1.txt ... dan $ cat > kelas2.txt ...:
Ini adalah perintah untuk membuat dua file teks baru, "kelas1.txt" dan "kelas2.txt", dengan menggunakan perintah cat dan mengisi konten file secara interaktif. Setelah konten dimasukkan, karakter Ctrl-d digunakan untuk mengakhiri proses penulisan file.

- $ cat kelas1.txt kelas2.txt | sort:
Ini adalah perintah untuk menggabungkan isi dari dua file, "kelas1.txt" dan "kelas2.txt", menggunakan cat, kemudian mengurutkan baris-barisnya menggunakan sort.
$ cat kelas1.txt kelas2.txt > kelas.txt:
Ini adalah perintah untuk menggabungkan isi dari dua file, "kelas1.txt" dan "kelas2.txt", dan menyimpannya dalam file baru bernama "kelas.txt".
-$ cat kelas.txt | sort | uniq:
Ini adalah perintah untuk menampilkan isi dari file "kelas.txt", mengurutkannya menggunakan sort, dan kemudian menggunakan uniq untuk menampilkan baris unik.

## LATIHAN:
### 1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output ke file baru.
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/e803d7c4-ad7b-4523-8386-27737c2a81eb)

Analisis:
-$ who:
Perintah ini menampilkan informasi tentang pengguna yang saat ini login ke sistem.
-$ who | sort:
Perintah ini menggunakan output dari perintah who sebagai input untuk perintah sort. Ini akan mengurutkan output dari perintah who berdasarkan urutan alfabetis dari nama pengguna.
-$ who | sort –r:
Ini hampir sama dengan perintah sebelumnya, namun opsi -r digunakan untuk mengurutkan secara terbalik (berdasarkan urutan alfabetis dari nama pengguna secara terbalik).
-$ who > tmp:
Perintah ini akan mengalihkan output dari perintah who ke file bernama "tmp". Ini akan mencatat informasi pengguna yang saat ini login ke dalam file "tmp".
-$ sort tmp:
Perintah ini akan mengurutkan isi dari file "tmp" yang berisi informasi pengguna yang tercatat sebelumnya dari perintah who. Ini akan mencetak hasil pengurutan ke terminal.
-$ rm tmp:
Ini adalah perintah untuk menghapus file "tmp" yang telah dibuat sebelumnya, yang berisi hasil output dari perintah who.
-$ ls –l /etc | more:
Perintah ini menampilkan daftar isi dari direktori "/etc" dengan rincian informasi menggunakan format panjang, dan kemudian mengalihkan outputnya ke perintah more untuk memungkinkan penampilan per halaman.
-$ ls –l /etc | sort | more:
Perintah ini melakukan hal yang sama dengan perintah sebelumnya, namun sebelum ditampilkan dengan more, output dari perintah ls -l /etc diurutkan menggunakan perintah sort.

### 2.Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/1894d2f4-5d80-4a20-a101-eda827b1ac70)
Analisis:

- $cat /etc/passwd >> file.txt:
Perintah ini membaca isi dari file /etc/passwd menggunakan perintah cat dan kemudian menambahkan isi tersebut ke dalam file file.txt menggunakan operator append >>. Dengan demikian, isi dari /etc/passwd akan ditambahkan ke akhir file file.txt.

- $cat file.txt:
Perintah ini hanya mencetak isi dari file file.txt ke output standar (biasanya terminal). Setelah perintah pertama dieksekusi dan isi dari /etc/passwd ditambahkan ke file.txt, perintah kedua ini akan mencetak isi keseluruhan dari file.txt, termasuk isi dari /etc/passwd yang sudah ditambahkan sebelumnya.

### 3.Urutkan file baru dengan cara membelokkan standard input.
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/acf5de6b-4392-4bc1-9866-4590623bf11b)

Analisis: Ini adalah perintah untuk mengurutkan isi dari file file.txt menggunakan perintah sort. Namun, dalam kasus ini, penggunaan < digunakan untuk mengalihkan isi file file.txt ke input perintah sort. Jadi, perintah ini akan mengambil isi dari file file.txt sebagai input, mengurutkannya, dan mencetak hasil pengurutan ke output standar (biasanya terminal). Tidak akan ada perubahan yang terjadi pada file file.txt itu sendiri, karena perintah ini hanya mengambil isi file sebagai input untuk pengurutan.

### 4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/bcfd75b8-abab-4682-9a31-436d8c8da57b)

Analisis:

- $ cat file.txt > baru.urut:
Perintah pertama ini mengambil isi dari file file.txt menggunakan perintah cat, dan kemudian mengalihkan outputnya ke file baru yang disebut baru.urut menggunakan operator >. Dengan demikian, isi dari file.txt akan disalin ke dalam file baru baru.urut.

- $ cat baru.urut:
Perintah kedua ini hanya mencetak isi dari file baru.urut ke output standar (biasanya terminal). Setelah perintah pertama dieksekusi dan isi dari file.txt disalin ke dalam baru.urut, perintah kedua akan mencetak isi keseluruhan dari baru.urut.

### 5.Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/5bd486d6-37d7-48b9-a7f9-983f63e05e0e)

Analisis:perintah pertama berhasil membuat direktori "latihan2", sementara perintah kedua mengalami kesalahan dalam mencoba membuat direktori "latihan" dan pesan kesalahan tersebut akan tercatat di dalam file "rmdirerror.txt". Perintah ketiga dan keempat kemungkinan merupakan kesalahan penulisan nama file, karena tidak ada file bernama "rmdirerror" yang dibuat dalam konteks perintah-perintah sebelumnya.

###  6. Urutkan kalimat berikut:
```sh
>jakarta
>bandung
>padang
>surabaya
>padang
>palembang
>lampung
>@@@
Jakarta
Bandung
Surabaya
Padang
Palembang
Lampung
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/415889d1-5cf9-4688-a6fa-9a8d55bea5bc)

Analisis:
Ini adalah contoh penggunaan heredoc dalam perintah sort. Heredoc memungkinkan Anda untuk menuliskan blok teks panjang di dalam skrip shell tanpa harus menggunakan tanda kutip ganda atau tunggal. Dalam hal ini, delimiter yang digunakan adalah @@@.

### 7.Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/4b51738c-822b-4019-b8ec-0c2f315d7f3b)

Analisis: untuk menampilkan jumlah baris, kata, dan karakter (secara berurutan) dari sebuah file, gunakan perintah wc yang dipipakan dengan perintah cat. Hasilnya kemudian bisa ditambahkan ke file menggunakan ‘>>’

### 8.Gunakan perintah dibawah ini dan perhatikan hasilnya.
```sh
 $ cat > hello.txt
 dog cat
 cat duck
 dog chicken
 chicken duck
 chicken cat
 dog duck
 [Ctrl-d]
 $ cat hello.txt | sort | uniq
 $ cat hello.txt | grep “dog” | grep –v “cat”
```
![image](https://github.com/anggiadwi/SysOP24-3123521028/assets/160558458/9bff50b1-262a-4d20-9ebd-4b3489d24695)

Analisis:

- $ cat > hello.txt:
Perintah ini memungkinkan Anda untuk mengetikkan teks secara interaktif dan menyimpannya dalam file bernama hello.txt.

- $ cat hello.txt | sort | uniq:
Perintah ini menggunakan output dari file hello.txt sebagai input untuk perintah sort, yang kemudian mengurutkan baris-baris teksnya, dan outputnya diarahkan ke perintah uniq.
Perintah uniq akan menghilangkan baris-baris yang sama berturut-turut.
Jadi, hasil akhirnya akan mencetak baris-baris teks unik yang diurutkan dari file hello.txt.

- $ cat hello.txt | grep “dog” | grep –v “cat”:
Perintah ini menggunakan output dari file hello.txt sebagai input untuk perintah grep.
Pertama, grep “dog” akan mencari baris-baris yang mengandung kata "dog".
Kemudian, grep –v “cat” akan mencari baris-baris yang tidak mengandung kata "cat".
Jadi, hasil akhirnya akan mencetak baris-baris yang mengandung kata "dog" tetapi tidak mengandung kata "cat".



## LAPORAN RESMI:

1. Analisa hasil percobaan 1 sampai dengan 4, untuk setiap perintah jelaskan tampilannya.

2. Kerjakan latihan diatas dan analisa hasilnya

3. Berikan kesimpulan dari praktikum ini. Kesimpulan Dari Latihan ini saya bisa mengenal fungsi-fungsi dari perintah-perintah dasar linux selain itu saya juga bisa mempraktekkan serta membuktikan secara langsung fungsi dari perintah dasar linux. Dan saya dapat mengetahui bahwa penggunaan Operasi Input dan Output proses dapat dipahami dengan mudah, sesuai dengan kebutuhan.
