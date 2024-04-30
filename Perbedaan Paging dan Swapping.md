## Perbedaan Paging dan Swapping

Paging dan swapping adalah dua teknik yang digunakan dalam manajemen memori pada sistem operasi, tetapi memiliki perbedaan dalam cara dan tujuan penggunaannya.

- Paging:
Paging adalah teknik memori virtual di mana memori fisik dan logis dibagi menjadi blok-blok kecil yang disebut halaman.Setiap program atau proses memiliki tabel halaman sendiri yang digunakan untuk memetakan alamat logis ke alamat fisik.Halaman-halaman ini dimuat ke dalam memori fisik saat dibutuhkan, dan hanya halaman yang diperlukan akan dimuat.Paging memungkinkan untuk mengalokasikan memori secara dinamis dan mengelola ruang memori secara efisien.
- Swapping:
Swapping adalah proses mengalihkan bagian-bagian dari program atau proses dari memori fisik ke penyimpanan sekunder (biasanya hard disk) dan sebaliknya.Ini terjadi ketika memori fisik tidak mencukupi untuk menampung semua program atau proses yang sedang berjalan.Sistem operasi akan menentukan bagian mana dari program atau proses yang tidak aktif atau jarang digunakan, lalu menggantinya dengan bagian yang lebih penting atau lebih aktif.Swapping membantu meningkatkan penggunaan memori fisik dan memungkinkan sistem untuk menjalankan lebih banyak program atau proses daripada yang dapat ditampung oleh memori fisik saja.Jadi, perbedaan utama antara paging dan swapping adalah bahwa paging berkaitan dengan pengelolaan memori virtual di dalam memori fisik, sementara swapping berkaitan dengan mengalihkan bagian-bagian program dari memori fisik ke penyimpanan sekunder dan sebaliknya untuk mengatasi keterbatasan memori fisik.
