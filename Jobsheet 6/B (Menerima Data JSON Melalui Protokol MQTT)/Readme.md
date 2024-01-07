# Menerima Data JSON Melalui Protokol MQTT
Pada percobaan ini kita akan melakukan ujicoba pengiriman data yang berupa JSON. Terdapat 2 percobaan, yaitu:

## 1. Pengiriman 1 Topik Pesan
### Alat dan Bahan

Software :

- Ubuntu Virtual Machine
- Node-red
- Mosquitto Broker

Node :
- Inject (1 buah)
- MQTT Out (1 buah)
- MQTT In (1 buah)
- JSON Parser (1 buah)
- Function (1 buah)
- Debug (1 buah)

### Program 
<a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%206/B%20(Menerima%20Data%20JSON%20Melalui%20Protokol%20MQTT)/flows%20(Job%206-B1).json">(File flows.json)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/47021956-41d2-43d5-891b-2f2cab50cad9)

### Flowchart

![Flowchart Job 6-B1](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/edb42b17-6dd9-4d6b-98ad-a7ede2695e19)

### Hasil dan Pembahasan

![Job 6-B1](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/5a14b906-fb17-4e3e-8549-2be14e3049dc)

Alur kerja dari program ini:
- Inject Node mengirimkan pesan payload dengan type JSON (`{"temp":24,"humi":30,"light":10}`).
- MQTT Out Node mengirimkan data suhu, kelembaban, dan intensitas cahaya ke topik "livingroom/sensors" menggunakan protokol MQTT.
- MQTT In Node menerima data suhu, kelembaban, dan intensitas cahaya dari topik "livingroom/sensors" melalui protokol MQTT.
- JSON Node mengkonversi payload dari format JSON ke objek JavaScript.
- Function Node mengambil nilai kelembaban (humi) dari objek dan mengirimkannya ke Node "Debug".
- Debug Node menampilkan nilai kelembaban pada konsol debug.

Program ini juga menggunakan MQTT Broker Node yang berfungsi untuk menyediakan konfigurasi yang bisa mengkoneksikan MQTT dengan broker lokal.

**Kesimpulan**

Program ini menghasilkan data suhu,kelembapan, dan intensitas cahaya dari ruang tamu dan akan dikirimkan dalam bentuk objek JSON melalui MQTT.

## 2. Pengiriman 2 Topik Pesan
### Alat dan Bahan

Software :

- Ubuntu Virtual Machine
- Node-red
- Mosquitto Broker

Node :
- Inject (2 buah)
- MQTT Out (2 buah)
- MQTT In (2 buah)
- JSON Parser (2 buah)
- Function (8 buah)
- Debug (7 buah)

### Program 
<a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%206/B%20(Menerima%20Data%20JSON%20Melalui%20Protokol%20MQTT)/flows%20(Job%206-B2).json">(File flows.json)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/96fab167-0274-47fc-a1ce-9c04ec702b46)

### Flowchart

![Flowchart Job 6-B2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/900e2e6e-d742-4910-8ba2-31c3bf3491c9)

### Hasil dan Pembahasan

![Job 6-B2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/d1431df0-3cd3-4008-a2f7-d2639775e5f9)

Program ini digunakan untuk mengontrol dan memonitor data dari semua sensor yang ada di ruang tamu dan dapur dengan menghubungkannya melalui MQTT. Data dari ruang tamu dan dapur akan dipisahkan dan kemudian akan dikirimkan dan diperiksa menggunakan berbagai Function Node dan akan ditampilkan pada konsol debug.

**Kesimpulan**

Dengan menggunakan protokol MQTT kita juga dapat mengirimkan data dengan topik yang berbeda dan juga nilai yang berbeda tanpa khawatir tertukar nilai antar topik.
