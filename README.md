### a. How many data your publisher program will send to the message broker in one run?

Dalam kode yang diberikan, program pengirim menggunakan instance CrosstownBus untuk mempublikasikan pesan. Dari kode tersebut, ada lima kali pemanggilan fungsi publish_event, yang masing-masing mempublikasikan satu pesan ke broker. Setiap pemanggilan mengirim satu UserCreatedEventMessage yang memiliki user_id dan user_name yang berbeda. Jadi, dalam satu kali jalan (execution) program ini, jumlah total data yang dikirim adalah lima pesan.

### b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
URL "amqp://guest:guest@localhost:5672" yang sama yang digunakan baik dalam program pengirim (publisher) maupun penerima (subscriber) menunjukkan bahwa kedua program tersebut terhubung ke broker pesan yang sama. URL tersebut mencakup kredensial akses, yaitu "guest" untuk username dan password, yang merupakan konfigurasi default umum untuk RabbitMQ ketika dijalankan secara lokal. Alamat "localhost" dengan port "5672" menandakan bahwa broker pesan beroperasi pada mesin lokal yang sama dengan aplikasi pengirim dan penerima, menggunakan port yang standar untuk protokol AMQP pada RabbitMQ. Dengan menggunakan URL yang sama, kedua bagian aplikasi ini dapat berkomunikasi secara efektif melalui antrian yang sama, yang dalam kasus ini adalah antrian "user_created". Hal ini memungkinkan pesan yang dipublikasikan oleh pengirim dapat diterima oleh penerima melalui broker pesan.

![rabbit mq](image.png)
![sending](image-1.png)