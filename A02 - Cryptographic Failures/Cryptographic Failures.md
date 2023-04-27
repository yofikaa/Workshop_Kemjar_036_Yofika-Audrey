<h1>Praktikum Keamanan Jaringan 
A2 Cryptogaphic Failures (OWASP 10 Juice Shop)</h1>

<img src="img/logo_pens.png">

Oleh :
Yofika Audrey Tisnawati
3122640036
LJ D4 Teknik Informatika B

<b>POLITEKNIK ELEKTRONIKA NEGERI SURABAYA
TAHUN AJARAN 2022/2023</b>

<h2><b>A. Nested Easter Egg</b></h2>
Challenge nested easter egg bertujuan untuk menemukan pesan tersembunyi yang telah disisipkan kedalam website
1. Buka aplikasi juice shop lalu menuju navbar, klik halaman github yang tersedia

<img src="img/1.png">
<img src="img/2.png">

2. Setelah itu cari folder ftp dan masuk ke file eastre.gg

<img src="img/3.png">

3. Pada file tersebut terdapat kode "L2d1ci9xcmlmL25lci9mYi9zaGFhbC9ndXJsL3V2cS9uYS9ybmZncmUvcnR0L2p2Z3V2YS9ndXIvcm5mZ3JlL3J0dA==", copy code tersebut

<img src="img/4.png">

4. Buka website cyberchef

<img src="img/5.png">

5. Tambahkan From Base64 dan ROT13 pada operation

<img src="img/6.png">

6. Masukkan code yang di dapat dari pada file eastre.gg. Akan muncul alamat pada output, copy alamat tersebut.
<img src="img/7.png">

7. Buka alamat tersebut pada aplikasi juice shop maka akan muncul seperti ini. Challenge Nested Easter Egg berhasil dipecahkan

<img src="img/8.png">


<h2><b>B. Weird Crypto</b></h2>
Challenge weird crypto bertujuan untuk memberi tahu aplikasi tentang algoritma atau library enkripsi yang seharusnya tidak digunakan.
1. Buka halaman customer feedback pada aplikasi juice shop yang terdapat di navbar

<img src="img/9.png">
<img src="img/10.png">

2. Masukkan MD5 pada kolom komentar lalu beri rating dan isi captcha setelah itu submit maka challenge weird crypto akan selesai

<img src="img/11.png">

Tujuan dari challange Weird Crypto ini adalah kita sudah harus tau algoritma atau library enkripsi apa yang sebaiknya kita gunakan dan yang sudah harus kita tinggalkan. Salah satu contoh algoritma yang sebaiknya sudah ditinggalkan adalah MD5.
