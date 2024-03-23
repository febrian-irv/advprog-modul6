#### Nama: Febrian Irvansyah
#### NPM: 2206083584
#### Kelas: Pemrograman Lanjut C

## Commit 1 Reflection notes
handle_connection menerima parameter TcpStream dengan variabel 'stream' yang menghubungkan antara local dan sebuah remote socket. Terdapat variabel 'buf_reader' sebagai BufReader yang berfungsi untuk membaca barisan informasi yang diberikan oleh stream hingga menemukan empty line. Pembacaan line tersebut akan dimasukkan ke dalam vector http_request. Terakhir dilakukan print pada http request yang diterima.

## Commit 2 Reflection notes
Pada kode baru ini terdapat status_line yang menunjukkan response HTTP yang sukses (200). Terdapat penggunaan module 'fs' yang di import agar kode dapat berinteraksi dengan filesystem yang dalam kasus ini adalah hello.html. Lalu terdapat Content-Length yang dimasukkan kedalam response pada klien terkait ukuran konten yang dikirim dalam bytes.

![Commit 2 screen capture](/assets/images/commit2.png)