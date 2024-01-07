# Mengakses Sensor DHT11
Melakukan ujicoba menggunakan sensor suhu dan kelembaban (DHT11) pada ESP32. Terdapat 2 percobaan yang dilakukan, diantaranya:

## 1. Membaca data suhu dan kelembaban ruangan

### Alat dan Bahan
- ESP32 (1 buah)
- Kabel jumper (secukupnya)
- DHT11 (1 buah)
- Resistor 10 kOhm (1 buah)

### Skema Rangkaian

![Skematik (Job 2-B)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/4a20267c-cff4-4b0c-a5f2-55d833f123a2)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%202/B%20(DHT)/Job%202-B_1/DHT/DHT.ino"> File .ino </a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/c5d9111e-5124-40b5-bc62-d842e82be43c)

### Flowchart

![Flowchart Job 2-B 1](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/c238194e-8f7b-487b-9608-e0a9a0ea037c)

### Hasil dan Pembahasan

![Job-2-B_1](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/0ffedd7d-f2c3-4748-b388-bdfc541708e9)

Program ini menggunakan sensor DHT11 yang dipasang di pin digital 4 sebagai variabel input. Program ini digunakan untuk mengukur data kelembapan (`h`), suhu dalam celcius (`t`), dan suhu dalam fahrenheit (`f`). Program akan menghitung indeks panas dalam fahrenheit (`hif`) dan celcius (`hic`) dengan menggunakan metode `computeHeatIndex`. Hasil data-data tadi akan dicetak pada serial monitor dengan memiliki delay 2 detik antara setiap pengukuran. Jika terjadi error pada pembacaan sensor, maka akan muncul pesan teks pada serial monitor.

**Kesimpulan**

Program ini dibuat untuk mengukur dan menampilkan data suhu, kelembapan, dan indeks panas dari sensor DHT11. Semua data akan dicetak pada serial monitor, begitu pula saat terjadinya error pada sensor akan teridentifikasi.

## 2. Menyalakan LED dan Buzzer menggunakan DHT11

### Alat dan Bahan
- ESP32 (1 buah)
- Kabel jumper (secukupnya)
- Resistor 10 kOhm (1 buah)
- DHT11 (1 buah)
- Resistor 220 Ohm (1 buah)
- Lampu LED (1 buah)

### Skema Rangkaian

![Skematik (Job 2-B 2)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/7d3d66fe-b4a6-48c0-a68b-9a5acb5c6a54)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%202/B%20(DHT)/Job%202-B_2/DHT_BUZZER/DHT_BUZZER.ino"> File .ino </a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/0e6b95c1-9eaa-4d8d-b84d-482f8d7b8349)

### Flowchart

![Flowchart Job 2-B 2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/481d7285-1e30-42a5-ba3e-a3895c673f52)

### Hasil dan Pembahasan

![Job-2-B_2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/f4e32320-a9cc-4758-9eef-7a4e60622b3a)
Program ini merupakan hasil pengembangan dari program selanjutnya, dimana terdapat penggunaan LED dan buzzer sebagai variabel output. Program akan membaca sensor suhu DHT dengan menggunakan `dht.readTemperrature()` dan akan mencetak nilai suhu pada serial monitor. Jika nilai suhu melebihi atau sama dengan 30 derajat celcius, maka akan menyalakan LED dan buzzer yang disetting dengan frekuensi 1000Hz selama 100ms (beep). Sebaliknya jika nilai suhu lebih kecil dari 30 derajat celcius, maka LED dan buzzer tidak akan merespon (mati).

**Kesimpulan**

Dengan menggunakan sensor DHT11 dan modul ESP32 dapat membuat mekanisme pendeteksi kebakaran yang memiliki output respon LED dan buzzer.
