## Perbedaan RISC dan CISC:

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
