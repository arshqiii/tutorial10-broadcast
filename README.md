# Tutorial 10 - Broadcast

## 2.1. Original code of broadcast chat
![alt text](image.png)

Hasil diatas diperoleh oleh saya dengan menjalankan cargo run server pada satu terminal lalu membuka 3 terminal lain yang menjalankan cargo run client. Ketika menjalankan server, server akan listen kepada request yang masuk ke port 2000 dan setiap kali ada client yang connect server akan menampilkan pesan `New connection from...` pada console server. Ketika salah satu client mengetik pesan pada terminal misal "Hello", maka server akan print `From Client... "hello"` lalu pada tiap client lain yang terbuka akan ditampilkan `From server: Hello`. Server akan keep track connection dengan setiap clientnnya, kemudian jika ada pesan dari suatu client, maka semua client yang connected juga akan mendapatkan pesan tersebut.

## 2.2. Modifying port
![alt text](image-1.png)

Hasil diatas kurang lebih sama seperti hasil sebelumnya dimana server dapat menerima koneksi dari 3 client yang berbeda. Namun ketika saya coba mengubah port pada kode server, lalu menjalankan run client kembali terjadi error "access is denied". ini terjadi karena server keep track connections dari client di suatu port, sedangkan jika port berbeda maka client mengirimkan request ke port lain sehingga akses tidak terpenuhi dan terjadi error. Ini menunjukkan bahwa Client dan Server hanya dapat berinteraksi dengan lancar jika terhubung ke titik koneksi port yang sama.