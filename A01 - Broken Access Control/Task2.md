**Laporan Praktikum Keamanan Jaringan** 

**BROKEN ACCESS CONTROL** 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.001.png)

**Oleh :** 

Yofika Audrey Tisnawati 3122640036 

LJ D4 Teknik Informatika B 

**POLITEKNIK ELEKTRONIKA NEGERI SURABAYA TAHUN AJARAN 2022/2023** 

Access Control menetapkan sebuah peraturan yang dimana user tidak dapat melakukan sebuah aksi diluar permission yang diberikan. Kegagalan atas hal ini dapat mengakibatkan pengeluaran informasi yang tidak diizinkan, modifikasi, atau penghancuran dari semua data atau pemberlakuan sebuah fungsi bisnis di luar limit sebuah user.  

Access control yang bermasalah memungkinkan hacker untuk melewati proses autorisasi serta melakukan hal-hal yang biasanya hanya dapat dilakukan oleh admin. 

1. Install burpsuite 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.002.png)

2. Buka aplikasi burpsuite 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.003.jpeg)

3. Jalankan aplikasi juice shop 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.004.jpeg)

4. Masuk ke burpsuite dan buka browser dari burpsuite. Jangan lupa untuk mematikan intercept terlebih dahulu lalu buka halaman juice shop. 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.005.jpeg)

5. Login ke akun juice shop dan tambahkan beberapa product ke basket 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.006.jpeg)

6. Buka kembali burpsuite lalu buka http history untuk tracing http requestnya. Karena tujuan dari tracing http request ini adalah untuk melihat keranjang milik user id lain, kita akan melihat terlebih dahulu data apa yang dikirimkan ketika user menambahkan product ke keranjangnya dan pada response kitab isa melihat barang apa saja yang ada di basket user kita (akun yang sedang login) 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.007.jpeg)

7. Untuk melihat keranjang user lain disini saya menyalin request yang dikirimkan oleh user 6 dan akan terlihat response yang diberikan adalah keranjang milik user 6 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.008.jpeg)

8. Ketika get requestnya diubah menjadi basket/2 ternyata id user yang diberikan adalah id user 2 dan sebenarnya pada burpsuite pun kita sudah bisa melihat isi keranjang dari user id 2 yaitu raspberry juice 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.009.jpeg)

9. Namun untuk menampilkannya pada website kita perlu mengubah script yang ada pada intercept dan mengubah basketnya menjadi 2 lalu forward dalam kondisi intercept on  

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.010.jpeg)

10. Setelah itu muat kembali aplikasi juice shop dan akan tampil isi dari keranjang user 2 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.011.jpeg)

11. Untuk memanipulasi keranjang milik user id lain, saya akan coba untuk menambah isi dari keranjang 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.012.jpeg)

**BROKEN ACCESS CONTROL ADMIN SECTION** 

1. Sebelum masuk menggunakan akun admin, kita perlu mengetahui email user id yang memiliki role admin. Pada review product tertera email admin yang bisa kita gunakan untuk masuk sebagai admin. 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.013.jpeg)

2. Selanjutnya buka burpsuite lalu pada target tambahkan target scope dan masukkan url juice shop yaitu localhost:3000 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.014.jpeg)

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.015.jpeg)

3. Setelah itu pada option intercept client request enable URL  

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.016.jpeg)

4. Lalu nyalakan kembali intercept dan masuk ke halaman login juice shop menggunakan email admin. Akan tampil pada intercept email dan password yang telah kita masukkan di halaman login sebelumnya. 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.017.jpeg)

5. Send to intruder 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.018.png)

6. Setting intruder terlebih dahulu. Pada target masukkan target hostnya yaity localhost:3000 dan portnya 8080 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.019.png)

7. Setelah itu pada position clear symbol kecuali pada password  

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.020.jpeg)

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.021.jpeg)

8. Lalu pada payload option load dataset password yang telah disiapkan  

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.022.jpeg)

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.023.jpeg)

9. Setelah itu akan muncul password yang sesuai dengan email tersebut dan kita akan bisa masuk dengan menggunakan password tersebut. 

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.024.png)

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.025.jpeg)

![](Aspose.Words.c206cde6-6acf-4022-874f-d7fb0048454d.026.png)
