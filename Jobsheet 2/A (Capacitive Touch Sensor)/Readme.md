# ESP32 Capacitive Touch Sensor
Melakukan ujicoba kontrol LED pada ESP32 menggunakan input berupa sentuhan. Terdapat 5 percobaan yang dilakukan, diantaranya:

## 1. Membaca data input yang berupa sentuhan

### Alat dan Bahan
- ESP32 (1 buah)
- Kabel jumper (secukupnya)

### Skema Rangkaian

![image](https://github.com/alfan459/Embedded-System/assets/54757609/f172e71d-7663-476e-b929-b32ce02d00b5)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/tree/main/Jobsheet%202/A%20(Capacitive%20Touch%20Sensor)/Job%202-A_1/Job_2-A_1.ino"> File .ino </a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/1450a2ac-7aea-4e1e-9ffd-c59da7d0bd37)

### Flowchart

![Flowchart Job 2-A 1](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/6e549d6e-be9d-49d4-bd70-7e5236a04f59)

### Hasil dan Pembahasan

![Job-2-A_1](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/00dd0ecd-e43b-4f3e-909d-f6e0fc4cb13c)

Program ini dibuat untuk menguji kemampuan sentuhan pada pin sentuh yang terletak di GPIO 4. Cara kerja program, nilai dari pin sentuh yang dibaca dengan fungsi `touchRead(4)` akan ditampilkan ke serial monitor menggunakan `Serial.println` dengan delay baca selama 1 detik. Nilai yang ditampilkan merupakan nilai analog yang memiliki kisaran dari 0 sampai 4095, dimana 4095 menunjukan nilai sentuhan maksimum.

**Kesimpulan**

Nilai sentuh akan terbaca dengan rentang dari 0 sampai 4095, sesuai tingkat sentuhan. Semakin tinggi tingkat sentuhan, maka semakin tinggi nilai yang terbaca oleh pin GPIO 4 dan akan ditampilkan pada serial monitor.

## 2. Menyalakan LED dengan sensor sentuh

### Alat dan Bahan
- ESP32 (1 buah)
- Kabel jumper (secukupnya)
- Resistor 220 Ohm (1 buah)
- Lampu LED (1 buah)

### Skema Rangkaian

![image](https://github.com/alfan459/Embedded-System/assets/54757609/f172e71d-7663-476e-b929-b32ce02d00b5)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%202/A%20(Capacitive%20Touch%20Sensor)/Job%202-A_2/Capacitive_Touch_Sensor/Capacitive_Touch_Sensor.ino"> File .ino </a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/26630fd3-0d41-4456-b54c-63b9c148660d)

### Flowchart

![Flowchart Job 2-A 2](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/54eb4735-b853-46e7-bff4-e5295cafd7af)

### Hasil dan Pembahasan

![Job-2-A_2](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/176d258e-1789-458f-9c60-0adb591cf1d3)

Program ini merupakan perkembangan sebelumnya, dimana pada program ini menggunakan LED yang dipasang pada pin 16 (`ledPin`). Nilai sentuhan dari pin GPIO 4 akan terbaca menggunakan `touchRead` dan nilai tersebut akan menjadi nilai `touchValue` yang akan ditampilkan pada serial monitor dengan memiliki delay cetak setiap 0,5 detik. Jika mengalami sentuhan, nilai `ledPin` menjadi HIGH (dinyalakan) dan begitu juga sebaliknya jika tidak ada sentuhan, nilai `ledPin` akan menjadi LOW (mati).

**Kesimpulan**

nilai sentuh pada pin GPIO 4 akan menjadi nilai `touchValue` yang akan dicetak ke serial monitor dan nilai ini akan menjadi nilai output untuk memberikan respon pada LED yang terpasang pada pin 16.

## 3. Membuat Blink LED dengan sensor sentuh

### Alat dan Bahan
- ESP32 (1 buah)
- Kabel jumper (secukupnya)
- Resistor 220 Ohm (1 buah)
- Lampu LED (1 buah)

### Skema Rangkaian

![image](https://github.com/alfan459/Embedded-System/assets/54757609/f172e71d-7663-476e-b929-b32ce02d00b5)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%202/A%20(Capacitive%20Touch%20Sensor)/Job%202-A_3/Capacitive_Touch_Sensor_Blink/Capacitive_Touch_Sensor_Blink.ino"> File .ino </a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/5ff4f955-c982-48e3-aff1-dc90ad5be468)

### Flowchart

![Flowchart Job 2-A 3](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/c9655e7d-6d3a-439c-9891-d4c11d35deaa)

### Hasil dan Pembahasan

![Job-2-A_3](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/493fea73-d2a5-411c-ad73-985dc987927c)

Program ini memiliki variabel input (`touchPin`) yang dipasang pada pin GPIO 4 dan memiliki variabel output (`ledPin`) yang dipasang pada pin 16. Cara kerja program ini, nilai sentuh akan dicetak ke srial monitor setiap 0,5 detik dengan menggunakan `touchRead(4)`. Jika nilai sentuh tersebut kurang dari atau sama dengan 30, maka akan memberikan respon pada LED dengan durasi nyala selama 1 detik dan akan kembali mati setelah 1 detik. Pada program ini terdapat juga fungsi `delay()` untuk memberikan jeda sebelum iterasi berikutnya dimulai.

**Kesimpulan**
 
Program ini memiliki respon yang cepat, dikarenakan memiliki nilai acuan sentuh dibawah kurang dari atau sama dengan 30 untuk memberikan respon pada LED.

## 4. Menghitung jumlah sentuhan

### Alat dan Bahan
- ESP32 (1 buah)
- Kabel jumper (secukupnya)
- Resistor 220 Ohm (1 buah)
- Lampu LED (1 buah)

### Skema Rangkaian

![image](https://github.com/alfan459/Embedded-System/assets/54757609/f172e71d-7663-476e-b929-b32ce02d00b5)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%202/A%20(Capacitive%20Touch%20Sensor)/Job%202-A_4/Capacitive_Touch_Sensor_disentuh_bertambah/Capacitive_Touch_Sensor_disentuh_bertambah.ino"> File .ino </a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/698086dc-f4c7-4154-8fa7-b50c692ca044)

### Flowchart

![Flowchart Job 2-A 4](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/a203cd8b-64c2-438c-a985-56fd5ffba281)

### Hasil dan Pembahasan

![Job-2-A_4](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/84294871-20f8-4c7f-ac81-aa0a3085b327)

Program ini memiliki cara kerja:

- program akan memeriksa apakah nilai yang terbaca dari sensor sentuhan memiliki nilai kurang dari atau sama dengan 30. Jika iya, maka nilai `touchValue` akan bertambah satu dan program akan memberikan respon pada LED yang akan dinyalakan selama 1 detik dan kemudian akan dimatikan kembali.
- nilai `touchValue` akan dicetak pada serial monitor setiap 0,5 detik.
- LED akan tetap mati, jika tidak ada sentuhan pada sensor sentuh.

**Kesimpulan**

nilai `touchValue` akan selalu bertambah satu karena terdapat program counter `touchValue++`.

## 5. Menyalakan running LED dengan sentuhan

### Alat dan Bahan
- ESP32 (1 buah)
- Kabel jumper (secukupnya)
- Resistor 220 Ohm (3 buah)
- Lampu LED (3 buah)

### Skema Rangkaian

![Skematik (Job 2-A 5)](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/16075eb2-dfc3-4437-9e54-4e57ba034ec5)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/tree/main/Jobsheet%202/A%20(Capacitive%20Touch%20Sensor)/Job%202-A_5/Capacitive_Touch_Sensor_RunLED"> File .ino </a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/0e56b801-2c24-4425-a824-d41976fae866)

### Flowchart

![Flowchart Job 2-A 5](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/4f75bd93-e8c4-4c68-8830-534bc274abb4)

### Hasil dan Pembahasan

![Job-2-A_5](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/14dbfb6f-f935-42c5-8eb1-2c887cab333b)

Program ini menggunakan 3 LED yang dipasang pada pin 16,17,dan 18. Ketiga pin tersebut diatur sebagai output melalui perintah `pinMode`. Terdapat variabel array `pinLED` yang di dalamnya terdapat ketiga pin LED yang memungkinkan program dapat mengontrol ketiga LED secara bersamaan. Program akan menghasilkan respon LED menyala bergantian dengan waktu interval 0,5 detik, jika nilai sentuhan dari `touchPin` yang dibaca menggunakan fungsi `touchRead` kurang dari atau sama dengan 30. Hal itu juga akan menambah nilai `touchValue` yang akan dicetak pada serial monitor setiap 0,5 detik. Sedangkan saat nilai sentuh lebih dari 30, maka semua LED akan tetap mati.

**Kesimpulan**

Adanya variabel array membuat program dapat mengontrol ketiga LED secara bersamaan, sehingga dapat memberikan respon LED menyala secara bergantian atau running.
