#### Nama: Febrian Irvansyah
#### NPM: 2206083584
#### Kelas: Pemrograman Lanjut C

## Commit 1 Reflection notes
handle_connection menerima parameter TcpStream dengan variabel 'stream' yang menghubungkan antara local dan sebuah remote socket. Terdapat variabel 'buf_reader' sebagai BufReader yang berfungsi untuk membaca barisan informasi yang diberikan oleh stream hingga menemukan empty line. Pembacaan line tersebut akan dimasukkan ke dalam vector http_request. Terakhir dilakukan print pada http request yang diterima.

## Commit 2 Reflection notes
Pada kode baru ini terdapat status_line yang menunjukkan response HTTP yang sukses (200). Terdapat penggunaan module 'fs' yang di import agar kode dapat berinteraksi dengan filesystem yang dalam kasus ini adalah hello.html. Lalu terdapat Content-Length yang dimasukkan kedalam response pada klien terkait ukuran konten yang dikirim dalam bytes.

![Commit 2 screen capture](/assets/images/commit2.png)

## Commit 3 Reflection notes
Cara melakukan pemisahan pada response adalah dengan melakukan conditionals terhadap request_line. request_line akan me dicek untuk melakukan penentuan terhadap status_line dan juga file html yang digunakan. Pada kode commit ke-3 ini juga request_line dipersingkat sehingga hanya melakukan read pada line pertama request dan bukan keseluruhan line seperti sebelumnya. Refactoring perlu dilakukan pada conditionals karena terdapat redundansi yang sangat jelas antar kedua kondisi. Oleh karena itu command yang sama dikeluarkan dari conditionals. 

![Commit 3 screen capture](/assets/images/commit3.png)

## Commit 4 Reflection notes
127.0.0.1/sleep akan lebih lambat dibandingkan 127.0.0.1 karena ada pemanggilan thread::sleep(Duration::from_secs(5)). Pemanggilan tersebut akan memerintahkan server untuk inactive selama 5 detik. Inactive ini menunjukkan blocking operations yang mengganngu khususnya dalam situasi terdapat konkurensi dalam koneksi.

## Commit 5 Reflection notes
ThreadPool diimplementasikan untuk dapat menerima request secara konkurensi. ThreadPool bisa diinisialisasi dengan keyword new dan size yang ditentukan oleh programmer. Pada ThreadPool terdapat worker thread yang terus berjalan dalam loop. Loop tersebut berfungsi untuk menerima job. Terjadilah konkurensi dimana setiap worker akan mengambil job selama tersedia. Pada kasus commit ini worker dibatasi menjadi 4 hal tersebut dilakukan agar menghindari terjadinya spawning unlimited threads. Maka akan terjadi antrean dari request yang datang dan dikerjakan oleh worker tersebut sesuai urutan dan jika worker tersedia kembali setelah melakukan pekerjaan.