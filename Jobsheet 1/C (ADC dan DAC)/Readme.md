# ADC dan DAC
Merupakan `Converter` atau pengubah sinyal dari analog ke digital atau sebaliknya yang ada pada pin mikrocontroller, salah satunya ESP32. ESP32 mampu membaca input channel ADC hingga resolusi 12 bit. Hal tersebut berarti bahwa ESP32 mampu membaca input analog mulai dari 0 hingga 4095, di mana 0 sesuai dengan 0V dan 4095 hingga 3.3V. Resolusi channel ADC tersebut dapat dikonversi juga menjadi lebih kecil menggunakan kode dan rentang ADC pada program.

Terdapat 2 percobaan yang dilakukan :

## 1. Membaca nilai potensiometer
**Alat dan Bahan**

- ESP32 (1 buah)
- Potensiometer 10 kOhm (1 buah)
- Kabel Jumper (secukupnya)

**Skema Rangkaian**

![Skematik (Job 1-C)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/a1b81e08-e3c7-4359-b14e-d9b68908242d)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/C%20(ADC%20dan%20DAC)/ADC/ADC.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/ffdb1e7d-1637-4247-a33b-fa523157af9c)

**Flowchart**

![Flowchart Job1 C-1 (ADC)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/c44c0102-e0db-4515-b104-6ce64b8893bf)

**Hasil dan Pembahasan**

![Job 1C_1](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/6d973f93-6083-454d-8db4-2e9659e882db)

Program ini menggunakan potensiometer yang dipasang pada pin 34. Nantinya program ini akan menampilkan nilai yang terbaca pada potensiometer untuk ditampilkan ke serial monitor dengan menggunakan perintah `serial.println(potValue)` dengan perubahan nilai setiap 0,5 detik.

**Kesimpulan**

Program ini menampilkan pembacaan nilai Analog pada potensiometer dan menampilkannya ke serial monitor dalam bentuk digital.

## 2. Mengendalikan LED menggunakan potensiometer
**Alat dan Bahan**

- ESP32 (1 buah)
- Potensiometer 10 kOhm (1 buah)
- Lampu LED (1 buah)
- Resistor 220 Ohm (1 buah)
- Kabel Jumper (secukupnya)

**Skema Rangkaian**

![Skematik Job1 C-2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/ace8183d-017a-4aa6-9d1e-6aa3c1171ab3)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/C%20(ADC%20dan%20DAC)/DAC/DAC.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/ff78d7f3-ac32-48f8-89d8-933b36991498)

**Flowchart**

![Flowchart Job1 C-2 (DAC)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/0dadc48c-f76b-496a-8775-bc5fec8ea184)

**Hasil dan Pembahasan**

![Job 1C_2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/f2ff1c2c-378b-4efb-988a-086ab8b5a073)

Program ini memiliki cara kerja:
- Nilai analog yng terbaca dari potensiometer akan disimpan dalam variabel `sensorValue`.
- fungsi `map()` akan mengkonversi nilai analog menjadi nilai digital.
- Nilai hasil konversi tadi akan ditampilkan ke serial monitor dan akan digunakan sebagai output untuk menghidupkan LED.

**Kesimpulan**

Program ini menghasilkan perubahan tingkat kecerahan LED sesuai dengan nilai hasil konversi dari nilai analog potensiometer yang dikonversi ke digital dengan menggunakan fungsi `map()`.
