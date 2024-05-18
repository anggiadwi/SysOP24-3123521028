## TUGAS THREADS
**1. Berikan tiga contoh pemrograman di mana multhithreading memberikan kinerja yang lebih baik daripada solusi dengan satu thread.**

Jawab:
a. Server Web yang melayani setiap permintaan dalam thread terpisah.

b. Aplikasi yang diparalelkan seperti perkalian matriks di mana bagian yang berbeda dari matriks dapat dikerjakan secara paralel.

c. Program GUI interaktif seperti debugger di mana sebuah thread digunakan untuk memantau masukan pengguna, thread lain mewakili aplikasi yang sedang berjalan, dan thread ketiga memantau kinerja.


**2. Apa dua perbedaan antara user-level threads dan kernel-level threads? Dalam situasi apa salah satu jenis lebih baik daripada yang lain?**

Jawab:
a. Thread tingkat pengguna tidak diketahui oleh kernel, sedangkan kernel
mengetahui thread kernel.

b. Pada sistem yang menggunakan pemetaan M:1 atau M:N, thread pengguna dijadwalkan oleh pustaka thread dan kernel menjadwalkan thread kernel.

c. Thread kernel tidak perlu dikaitkan dengan proses sedangkan setiap thread pengguna milik sebuah proses. Thread kernel umumnya lebih mahal untuk dipelihara daripada thread pengguna karena harus diwakili dengan struktur data kernel.

**3. Jelaskan tindakan yang diambil oleh kernel untuk beralih koteks antara kernel-level threads**

Jawab:
Peralihan konteks antar thread kernel biasanya memerlukan penyimpanan nilai register CPU dari thread yang sedang di-switch out dan pemulihan register CPU dari thread baru yang dijadwalkan.

**4. Sumber daya apa yang digunakan ketika sebuah thread dibuat? Bagaimana perbedaannya dengan sumber daya digunakan ketika sebuah proses dibuat?**

Jawab:
Karena sebuah thread lebih kecil dari sebuah proses, pembuatan thread biasanya menggunakan sumber daya yang lebih sedikit daripada pembuatan proses. Membuat sebuah proses memerlukan pengalokasian blok kontrol proses (PCB), sebuah struktur data yang cukup besar. PCB mencakup peta memori, daftar file yang terbuka, dan variabel lingkungan. Mengalokasikan dan mengelola peta memori biasanya merupakan kegiatan yang paling memakan waktu. Membuat baik thread pengguna atau thread kernel melibatkan pengalokasian struktur data kecil untuk menyimpan set register, tumpukan, dan prioritas.

**5. Anggaplah sistem operasi memetakan user-level threads ke kernel menggunakan model banyak-ke-banyak dan pemetaan dilakukan melalui LWP. Selain itu,sistem memungkinkan pengembang untuk membuat real-time threads untuk digunakan dalam sistem real-time. Apakah perlu mengikut real-time thread ke LWP?Jelaskan**

Jawab:
Ya. Waktu sangat penting untuk aplikasi real-time. Jika sebuah thread ditandai sebagai real-time tetapi tidak terikat ke LWP, thread tersebut mungkin harus menunggu untuk dipasang ke LWP sebelum berjalan. Pertimbangkan jika sebuah thread real-time sedang berjalan (terpasang ke LWP) dan kemudian diblokir (misalnya harus melakukan I/O, didahului oleh thread real-time dengan prioritas lebih tinggi, menunggu kunci eksklusi bersama, dll.) Saat thread real-time diblokir, LWP yang terpasang padanya telah diberikan ke thread lain. Ketika thread real-time dijadwalkan untuk berjalan lagi, pertama-tama ia harus menunggu untuk dipasang ke LWP. Dengan mengikat LWP ke thread real-time Anda memastikan thread tersebut dapat berjalan dengan penundaan minimal setelah dijadwalkan.







