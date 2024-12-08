Nama: Rodiah Hasan Alaydrus
NPM: 4523210098
PBO Kelas A - Prak 10 (Studi Kasus ATM)

Penjelasan Account.java:
Kelas Account adalah model untuk aplikasi ATM yang memiliki atribut seperti nomor akun, PIN, dan saldo. Fitur utama yang ada termasuk credit untuk menambah saldo, debit untuk mengurangi saldo, dan withdraw untuk penarikan dengan syarat saldo minimum Rp50.000. Metode changePin memungkinkan pengguna untuk mengganti PIN dengan memvalidasi PIN lama, mengonfirmasi PIN baru, dan melakukan verifikasi ulang pada nomor akun serta PIN baru demi keamanan tambahan. Semua fitur ini dirancang untuk melindungi data dan memberikan pengalaman pengguna yang aman.

Penjelasan Deposit.java:
Kelas Deposit adalah subkelas dari kelas Transaction yang dibuat khusus untuk mengelola proses setoran uang di aplikasi ATM. Di dalam metode execute, pengguna akan diminta untuk memasukkan jumlah yang ingin disetor melalui input yang diambil menggunakan Scanner. Setelah itu, jumlah tersebut akan ditambahkan ke saldo akun dengan memanggil metode credit dari objek Account. Setelah setoran berhasil dilakukan, informasi saldo terbaru akan ditampilkan kepada pengguna. Fitur ini dirancang agar transaksi setoran menjadi lebih mudah dengan langkah-langkah yang simpel dan memastikan saldo selalu diperbarui dengan tepat.

Penjelasan Transaction.java:
Kelas abstrak Transaction berperan sebagai fondasi untuk berbagai transaksi dalam aplikasi ATM. Kelas ini memiliki atribut account yang menggambarkan akun yang terlibat dalam transaksi, yang diatur melalui konstruktor. Metode abstrak execute didefinisikan tanpa implementasi, sehingga kelas turunan harus memberikan logika yang sesuai dengan jenis transaksinya. Kelas ini dibuat untuk mendukung konsep pewarisan dan polimorfisme, sehingga memungkinkan pengembangan berbagai transaksi seperti setoran, penarikan, atau transfer dengan cara yang terstruktur dan konsisten.

Penjelasan Transfer.java:
Kelas Transfer merupakan turunan dari kelas abstrak Transaction yang mengatur proses pemindahan uang antar akun di aplikasi ATM. Kelas ini memiliki atribut tambahan bernama targetAccount yang menunjukkan akun tujuan transfer, dan diatur melalui konstruktor. Dalam metode execute, pengguna diminta untuk memasukkan jumlah yang ingin ditransfer menggunakan Scanner. Jika saldo akun mencukupi, jumlah tersebut akan dikurangi dari akun sumber dengan metode debit dan ditambahkan ke akun tujuan menggunakan metode credit. Setelah transfer berhasil, saldo terbaru dari akun sumber akan ditampilkan. Jika saldo tidak mencukupi, akan muncul pesan kesalahan. Kelas ini dibuat untuk memudahkan transfer antar akun dengan pengecekan saldo yang memastikan keamanan transaksi.

Penjelasan Withdrawal.java:
Kelas Withdrawal merupakan turunan dari kelas abstrak Transaction yang dibuat untuk mengelola proses penarikan uang dari akun di aplikasi ATM. Di dalam metode execute, pengguna diminta untuk memasukkan jumlah yang ingin ditarik melalui input dengan Scanner. Sistem akan memeriksa apakah jumlah penarikan lebih dari nol dan memastikan bahwa saldo yang tersisa setelah penarikan tidak kurang dari batas saldo minimum yang ditetapkan oleh Account.MINIMUM_BALANCE. Jika semua syarat terpenuhi, saldo akan dikurangi menggunakan metode debit, dan saldo terbaru akan ditampilkan. Namun, jika saldo tidak mencukupi atau melanggar batas minimum, pengguna akan menerima pesan kesalahan. Kelas ini menjamin bahwa penarikan dilakukan dengan aman sesuai dengan ketentuan saldo minimum.

Penjelasan ATM.java:
Kelas ATM adalah bagian utama dari aplikasi ATM yang bertugas untuk mengatur interaksi antara pengguna dan sistem. Kelas ini memanfaatkan Map untuk menyimpan akun-akun, di mana nomor akun berfungsi sebagai kunci dan objek Account sebagai nilainya. Metode start memulai proses dengan meminta pengguna untuk memasukkan nomor akun dan PIN agar bisa melakukan autentikasi lewat metode authenticateUser. Jika autentikasi berhasil, pengguna akan diarahkan ke metode showMenu, yang menampilkan berbagai pilihan transaksi seperti penarikan, deposit, transfer, pengecekan saldo, pengubahan PIN, dan keluar. Untuk melakukan transaksi, objek turunan dari Transaction seperti Withdrawal, Deposit, atau Transfer akan dibuat, dan masing-masing akan menjalankan logika transaksi yang sesuai. Dengan adanya validasi input dan penanganan pesan kesalahan, kelas ini memastikan pengalaman pengguna yang aman dan interaktif.

Hasil Running:
![alt text](<Screenshot 2024-12-08 142814.png>)
![alt text](<Screenshot 2024-12-08 142825.png>)
![alt text](<Screenshot 2024-12-08 142838.png>)