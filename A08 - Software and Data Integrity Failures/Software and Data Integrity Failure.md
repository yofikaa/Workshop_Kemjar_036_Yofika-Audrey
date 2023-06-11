<h1>Praktikum Keamanan Jaringan 
A8 Software and Data Integrity Failures</h1>

<img src="img/logo_pens.png">

Oleh :
Yofika Audrey Tisnawati
3122640036
LJ D4 Teknik Informatika B

Pada percobaan ini akan menunjukan mengunduh kode tanpa pemeriksaan integritas.

1. Buka Aplikasi Juice Shop.

<img src="img/1.png">


2. Tambahkan /ftp pada URL Juice Shop kita menjadi http://localhost:3000/ftp

<img src="img/2.png">


3. Klik package.json.bak, maka akan muncul tampilan sebagai berikut

<img src="img/3.png">


4. ubah URL pakcage.json.bak menjadi sebagai berikut localhost:3000/ftp/package.json.bak%2500.md lalu jalankan, maka kita akan mendownload file package.json tersebut seperti pada gambar berikut

<img src="img/4.png">


5. ubah URL pakcage.json.bak menjadi sebagai berikut localhost:3000/ftp/package.json.bak%2500.md lalu jalankan, maka kita akan mendownload file package.json tersebut seperti pada gambar berikut

<img src="img/4-1.png">
<img src="img/4-2.png">


    Berikut adalah isi dari file package.json yang berhasil terdownload

