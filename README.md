### a. What is amqp?
AMQP (Advanced Message Queuing Protocol) adalah sebuah protokol komunikasi yang digunakan untuk pengiriman pesan antar aplikasi atau sistem secara asinkron. AMQP memungkinkan aplikasi untuk berkomunikasi dengan cara mengirimkan pesan melalui antrian (queues) yang dapat diproses secara terpisah dan terpisah waktunya.

AMQP mendukung komunikasi antara aplikasi yang menggunakan berbagai teknologi dan bahasa pemrograman yang berbeda, dan sering digunakan bersama dengan message broker seperti RabbitMQ yang mendukung protokol ini.

b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for?
Pada string guest:guest@localhost:5672, bagian-bagiannya dapat dijelaskan sebagai berikut:
- guest (pertama): Ini adalah username yang digunakan untuk mengakses server RabbitMQ (atau broker AMQP lainnya). Dalam hal ini, "guest" adalah nama pengguna yang disediakan secara default oleh RabbitMQ.
- guest (kedua): Ini adalah password yang terkait dengan username "guest". Jadi, pengguna dengan nama "guest" harus menggunakan kata sandi "guest" untuk mengakses server.

Secara keseluruhan, guest:guest@localhost:5672 berarti aplikasi Anda akan menghubungkan ke server RabbitMQ yang berjalan di mesin lokal (localhost), menggunakan username dan password "guest" untuk melakukan autentikasi, dan berkomunikasi melalui port 5672.
