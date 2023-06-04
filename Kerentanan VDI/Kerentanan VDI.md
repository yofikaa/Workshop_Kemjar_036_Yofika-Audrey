<h1>Praktikum Keamanan Jaringan 
Kerentanan VDI</h1>

<img src="img/logo_pens.png">

Oleh :
Yofika Audrey Tisnawati
3122640036
LJ D4 Teknik Informatika B

<h2><b> Mengambil Data dari Database Menggunakan SQLMap </b></h2>
1. Atur network VDI menjadi bridged adapter
<img src="img/1.png">
<img src="img/2.png">

2. Cek inet menggunakan ifconfig. Setelah itu masukkan inet yang telah didapat ke command ipcalc
<img src="img/3.png">

3. Langkah selanjutnya kita lakukan scanning network dengan menggunakan NMap untuk mendapatkan ip target yang akan kita serang dengan menggunakan ip network yang kita dapatkan dari menjalankan command ipcalc
<img src="img/4.png">

4. Buka IP tersebut pada browser
<img src="img/5.png">

5. Mencari halaman yang memerlukan ID, seperti halaman detail artikel. Kemudian masukkan url 192.168.0.9/index.php?tampil=artikel_detail&id=85. Setelahnya jalankan SQLMap dengan perintah sqlmap -u "http://192.168.0.9/index.php?tampil=artikel_detail&id=85" --dbs
<img src="img/6.png">

6. Melihat tabel yang ada pada database dengan menjalankan perintah sqlmap -u "http://192.168.0.9/index.php?tampil=artikel_detail&id=85" -D vulnweb --tables
<img src="img/7.png">
Database vulnweb memiliki 7 tabel, yaitu user, artikel, galeri, halaman, komentar, menu, dan pesan

<h2><b>  Mencari Tahu Password Root Menggunakan NMap </b></h2>

1. Melakukan bruteforce dengan nmap 
<img src="img/8.png">
Pada percobaan ini tidak ditemukan password dan username yang sesuai
