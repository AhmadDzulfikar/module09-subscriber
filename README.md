### a. What is amqp?
AMQP (Advanced Message Queuing Protocol) adalah sebuah protokol komunikasi yang digunakan untuk pengiriman pesan antar aplikasi atau sistem secara asinkron. AMQP memungkinkan aplikasi untuk berkomunikasi dengan cara mengirimkan pesan melalui antrian (queues) yang dapat diproses secara terpisah dan terpisah waktunya.

AMQP mendukung komunikasi antara aplikasi yang menggunakan berbagai teknologi dan bahasa pemrograman yang berbeda, dan sering digunakan bersama dengan message broker seperti RabbitMQ yang mendukung protokol ini.

### b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for?
Pada string guest:guest@localhost:5672, bagian-bagiannya dapat dijelaskan sebagai berikut:
- guest (pertama): Ini adalah username yang digunakan untuk mengakses server RabbitMQ (atau broker AMQP lainnya). Dalam hal ini, "guest" adalah nama pengguna yang disediakan secara default oleh RabbitMQ.
- guest (kedua): Ini adalah password yang terkait dengan username "guest". Jadi, pengguna dengan nama "guest" harus menggunakan kata sandi "guest" untuk mengakses server.

Secara keseluruhan, guest:guest@localhost:5672 berarti aplikasi Anda akan menghubungkan ke server RabbitMQ yang berjalan di mesin lokal (localhost), menggunakan username dan password "guest" untuk melakukan autentikasi, dan berkomunikasi melalui port 5672.

### Simulation slow subscriber
![image](https://github.com/user-attachments/assets/91ed9529-6436-4c40-882f-5e08d78ed201)
![image](https://github.com/user-attachments/assets/0ad7faf9-5655-4fb6-80da-7155473e500c)

Dilihat dari grafik RabbitMQ di atas, jumlah pesan yang berada dalam antrean (queued messages) mencapai 11. Hal ini terjadi karena saya menjalankan perintah cargo run pada publisher sebanyak 4 kali berturut-turut. Setiap kali publisher dijalankan, mengirimkan 5 pesan sekaligus. Dengan adanya jeda waktu menggunakan thread::sleep(ten_millis);, 


### Simulation Many Subscriber

![image](https://github.com/user-attachments/assets/64446583-ed78-4c18-b515-dab74d1441a4)

![image](https://github.com/user-attachments/assets/e14974d0-77ed-4869-a203-50d881a4cc01)

Jika kita lihat disini message queue lebih cepat dari sebelumnya yang mana sebelumnya itu 10, tapi sekarang hanya 2. Terjadi karena penerbitan pesan secara bertubi-tubi oleh publisher sementara beberapa subscriber sedang memproses pesan. Publisher dan subscriber sama-sama aktif dalam waktu hampir bersamaan, namun kecepatan pengiriman pesan dari publisher melebihi kemampuan pemrosesan subscriber.
