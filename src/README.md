#### Nama: Febrian Irvansyah
#### NPM: 2206083584
#### Kelas: Pemrograman Lanjut C

## Commit 1 Reflection notes
handle_connection menerima parameter TcpStream dengan variabel 'stream' yang menghubungkan antara local dan sebuah remote socket. Terdapat variabel 'buf_reader' sebagai BufReader yang berfungsi untuk membaca barisan informasi yang diberikan oleh stream hingga menemukan empty line. Pembacaan line tersebut akan dimasukkan ke dalam vector http_request. Terakhir dilakukan print pada http request yang diterima.