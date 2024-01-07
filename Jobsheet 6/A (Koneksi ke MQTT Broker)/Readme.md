# Koneksi ke MQTT Broker
Pada percobaan ini kita akan mempelajari bagaimana cara mengkoneksikan publisher dan subscriber pada node-red menggunakan `Mosquitto`, yang merupakan MQTT Broker yang akan digunakan. Mosquitto akan kita gunakan dalam jobsheet 6 ini.

### Alat dan Bahan

Software :

- Ubuntu Virtual Machine
- Node-red
- Mosquitto Broker

Node :
- Inject (1 buah)
- Debug (1 buah)
- MQTT Out (1 buah)
- MQTT In (1 buah)

### Program 
<a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%206/A%20(Koneksi%20ke%20MQTT%20Broker)/flows%20(Job%206-A).json">(File flows.json)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/e6cab948-c83b-4306-9988-645e83bebae5)

### Flowchart

![Flowchart Job 6-A](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/2cc09e97-134f-438e-be9d-7b89629a3658)

### Hasil dan Pembahasan

![Job 6-A](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/52f8c3c7-997e-46cb-baa3-49dfffa4f35c)

Untuk menjalankan program ini, diperlukan untuk menginstal broker terlebih dahulu.Broker ini berfungsi untuk menghubungkan antara node MQTT out dan in agar memiliki topik yang sama. Alur kerja program ini:
- Inject Node mengirimkan pesan dengan topic "livingroom/sensors" dan payload "28" (suhu ruangan).
- MQTT Out mengirimkan data suhu ke topik "livingroom/sensors" dengan menggunakan protokol MQTT.
- MQTT Broker Node berguna untuk menyediakan konfigurasi untuk mengkoneksikan MQTT ke broker lokal.
- MQTT In menerima data yang dikirim dan kemudian akan menruskannya ke Debug Node.
- Debug Node menerima data suhu dan akan menampilkannya ke konsol.

**Kesimpulan**

Program ini mendeteksi suhu di ruang tamu dan mengirimkannya melalui MQTT ke topik "livingroom/sensors" dan kemudian akan ditampilkan pada konsol debug.
