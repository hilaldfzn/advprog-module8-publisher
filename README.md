# **Rust Tutorial & Exercise**
**Muhammad Hilal Darul Fauzan**<br/>
**2206830542**<br/>
**Pemrograman Lanjut C**<br/>

## **Tutorial Modul 8: Software Architecture**

a. How many data your publlsher program will send to the message broker in one run?
- Publisher program akan mengirimkan 5 message ke message broken dalam satu kali run. Hal ini karena dalam main function, method `publish_event` dengan `UserCreatedEventMessage` dipanggil sebanyak 5 kali.

b. The url of: `“amqp://guest:guest@localhost:5672”` is the same as in the subscriber program, what does it mean?
- Url `amqp://guest:guest@localhost:5672` yang sama pada kedua program menunjukkan bahwa kedua program tersebut terhubung ke message broker yang sama. Url ini digunakan untuk membuat publisher yang akan mengirim message ke queue. Di sisi lain, dalam subscriber program, url ini digunakan untuk membuat listener yang akan mengambil data dari message queue.

Lampiran Running RabbitMQ

![Running RabbitMQ](images/image1.jpeg)

Lampiran screen show console

![Sending and processing event](images/image2.jpeg)

Setelah Publisher di-run, Publisher akan mengirim data-data yang sudah di-*hard code* ke *message queue*. Kemudian, Subscriber akan menerima data ini dari *message queue* dan menampilkan pesannya di console seperti yang ada pada tampilan di atas.

Lampiran *monitoring chart based on publisher*

![Monitoring chart based on publisher](images/image3.jpeg)

Berdasarkan lampiran di atas, terdapat spike yang menandakan bahwa adanya peningkatan *message rate* yang terjadi pada interval tertentu, yang disebabkan oleh dilakukannya *cargo run* berulang pada Publisher. Hal ini menunjukkan bahwa setiap kali *cargo run* dijalankan, maka akan terjadi peningkatan *message rate* di RabbitMQ yang berfungsi sebagai *message queue*.