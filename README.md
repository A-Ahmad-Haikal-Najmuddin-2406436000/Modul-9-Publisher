## Publisher Reflection
a. How much data your publisher program will send to the message broker in one run?
    Dalam satu kali program ini dijalankan (cargo run), program Anda akan mengirimkan 5 buah pesan ke protokol.

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
    Sama karena url tersebut merupakan titik temu tempat kedua program tersebut berinteraksi. URL tersebut memerlihatkan server yang sama, port yang sama, dan kredensial yang sama.

### Running RabbitMQ
![Publisher broker image](publisher_broker.png)

### Send and Processing Event
![send_and_processing](send_and_processing.png)
Hal yang terjadi adalah:
Publisher membuat UserCreatedEventMessage, dan mengirimkannya ke "Queue" spesifik di RabbitMQ. RabbitMQ mencari yang "subscribed" ke queue tadi. Subscriber diberi notifikasi, mengambil datanya, dan memrosesnya dengan menampilkan di terminal.

### Monitoring chart based on publisher.
![monitoring_chart](chart_spike.png)
Spike ungu adalah indikator vital yang menunjukkan bahwa pesan yang dikirimkan publisher tidak hanya "terkirim" ke RabbitMQ, tapi juga diterima dan diproses oleh subscriber.