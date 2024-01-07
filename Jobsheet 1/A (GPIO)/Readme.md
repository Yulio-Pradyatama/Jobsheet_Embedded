# GPIO (General Purpose Input/Output)
Merupakan pin yang dapat digunakan untuk berbagai tujuan, baik sebagai pin input untuk membaca data dari sensor atau tombol, maupun sebagai pin output untuk mengontrol perangkat seperti LED atau motor.

Percobaan ini ditujukan agar dapat memahami penggunaan pin GPIO pada ESP32. Terdapat 4 percobaan yang berbeda :
## 1. Membuat Blink LED menggunakan millis()
**Alat dan Bahan**
- ESP32 (1 buah)
- LED (1 buah)
- Resistor 220 Ohm (1 buah)
- Resistor 10 kOhm (1 buah)
- Push Button (1 buah)
- Kabel Jumper (secukupnya)

**Skema Rangkaian**

![Skematik (Job 1-A)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/19bba8ae-ba03-437e-9c34-4b071b8749a3)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/tree/main/Jobsheet%201/A%20(GPIO)/1._Langkah_2.ino/1._Langkah_2.ino.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/6fdb5909-513d-4e39-92b7-99230cfb9cc6)

**Flowchart**

![Flowchart Job1 A-2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/d5131b0f-2f0e-4d8d-affa-30907a45a79d)

**Hasil dan Pembahasan**

![Job 1A_2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/ffe26eac-7e17-490a-8611-9d934e4e4355)

Program ini dibuat untuk menghasilkan lampu LED berkedip setiap 1 detik.Untuk mengatur kedipan LED memerlukan penggunaan variabel yang membuat tindakan yang terkait dengan waktu, seperti:

- `currentMillis`:menampilkan waktu yang telah berlalu sejak program dijalankan.
- `previousMillis`:menyimpan waktu kondisi terakhir.
- `interval` :mengatur interval waktu kedipan LED.

perintah `millis()` mencatat waktu sejak program dijalankan, kemudian program akan membandingkan selisih waktu sekarang (`currentMillis`) dengan waktu terakhir (`previousMillis`) dan jika hasil selisihnya lebih besar atau bahkan sama dengan nilai interval yang ditentukan (1 detik), maka perintah pada kondisi `if()` akan dijalankan dan nilai variabel `previousMillis` diupdate dengan waktu sekarang (`currentMillis`).

**Kesimpulan**

Program ini menggunakan variabel dengan fungsi `millis()` dan variabel `interval` yang digunakan untuk membuat tindakan yang terkait dengan waktu, sehingga dapat menghasilkan LED berkedip setiap 1 detik.

## 2. Membuat Blink LED saat penekanan button
**Alat dan Bahan**
- ESP32 (1 buah)
- LED (1 buah)
- Resistor 220 Ohm (1 buah)
- Resistor 10 kOhm (1 buah)
- Push Button (1 buah)
- Kabel Jumper (secukupnya)

**Skema Rangkaian**

![Skematik (Job 1-A)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/0eb37a65-8c5a-47e4-8159-11b88f11fef3)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/A%20(GPIO)/1._Langkah_3.ino/1._Langkah_3.ino.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/8c5b6f6a-76ef-4e4e-a3d5-bf5fa6002ee1)


**Flowchart**

![Flowchart Job1 A-3](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/3ade36bf-da67-4572-beb4-762fee4e4d9f)

**Hasil dan Pembahasan**

![Job 1A_3](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/0b540240-1a83-4d2f-acf9-58f05f451d02)

Program ini menggunakan button sebagai variabel input dan LED sebagai variabel output. Program ini bekerja sesuai dengan nilai `buttonState` saat membaca adanya tindakan pada variabel `buttonPin` (terjadi penekanan pada button), hal itu akan membuat program menjalankan perintah pada kondisi `if()`. Jika nilai `buttonState` sama dengan HIGH (ada penekanan), maka program akan melakukan tindakan pada variabel `ledPin` (menyalakan LED) dan begitu juga sebaliknya. Nilai dari `buttonState` akan dicetak ke Serial Monitor melalui perintah `Serial.println(buttonState)`.

**Kesimpulan**

Program ini akan bekerja saat ada penekanan pada tombol button yang akan memberikan tindakan untuk menyalakan LED.

## 3. Membuat Blink LED berdurasi 500ms saat penekanan button
**Alat dan Bahan**
- ESP32 (1 buah)
- LED (2 buah)
- Resistor 220 Ohm (2 buah)
- Resistor 10 kOhm (2 buah)
- Push Button (2 buah)
- Kabel Jumper (secukupnya)

**Skema Rangkaian**

![Skematik (Job 1-A 4)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/94db2d19-d123-4cc5-b552-82e9022976b2)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/A%20(GPIO)/1._Langkah_4.ino/1._Langkah_4.ino.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/c62988bb-b9e0-49b8-a084-a6ad83eccb2a)

**Flowchart**

![Flowchart Job1 A-4](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/3ce6b592-110c-41be-b105-fbd0afb3fda9)

**Hasil dan Pembahasan**

![Job 1A_4](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/1dd36927-64e6-4973-b328-9315b3d02b65)

Program ini menggunakan 2 button dan 2 LED, dimana button sebagai variabel input (`buttonPin1` dan `buttonPin2`) dan LED sebagai variabel output (`ledPin1` Kuning dan `ledPin2` Merah). Program ini menghasilkan keluaran 3 kondisi, dimana:

- `buttonState1` sama dengan HIGH (ada penekanan) akan memberikan tindakan untuk menyalakan kedua LED secara bersamaan.
- `buttonState2` sama dengan HIGH (ada penekanan) akan memberikan tindakan untuk menyalakan LED secara bergantian atau secara `blink` dengan interval menyala setiap 0,5 detik yang diatur dari variabel `delay`.
- Kedua button tidak ada penekanan, kedua LED akan memiliki nilai LOW atau mati.

*Kesimpulan**

Program ini menghasilkan keluaran kedua LED menyala bersamaan saat button ke 1 ditekan dan menghasilkan LED menyala secara bergantian atau blink saat button ke 2 ditekan.

## 4. Membuat Running LED saat penekanan button
**Alat dan Bahan**
- ESP32 (1 buah)
- LED (3 buah)
- Resistor 220 Ohm (3 buah)
- Resistor 10 kOhm (3 buah)
- Push Button (3 buah)
- Kabel Jumper (secukupnya)

**Skema Rangkaian**

![Skematik (Job 1-A 5)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/3bf1381c-2ec5-486e-9f85-84393dd2bbaf)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/A%20(GPIO)/1._Langkah_5.ino/1._Langkah_5.ino.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/31b5430e-3301-4ad6-8060-00b7a55ce519)

**Flowchart**

![Flowchart Job1 A-5](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/0d3cc857-d58b-41b8-ac1c-e74c75c38106)

**Hasil dan Pembahasan**

![Job 1A_5](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/6ae289d0-41e9-46e7-9eba-98a0278a4c22)

Program ini menggunakan 3 variabel input dan 3 variabel output, dimana variabel input (`buttonPin1`, `buttonPin2`, dan `buttonPin3`) dan untuk variabel output (`ledPin1`, `ledPin2`, dan `ledPin3`).Program ini menghasilkan keluaran 4 kondisi:
- LED menyala secara bersamaan, kondisi dimana saat `buttonState1` bernilai HIGH (button 1 ditekan).
- LED 1 dan 2 menyala secara blink dengan interval 0,5 detik, kondisi saat `buttonState2` bernilai HIGH (button 2 ditekan).
- LED menyala secara bergantian dengan interval 0,5 detik, kondisi saat `buttonState3` bernilai HIGH (button 3 ditekan).Pada kondisi ini memerlukan fungsi `loop()` yang berguna mengulang program yang di dalamnya terdapat variabel `pinLED` sebagai array untuk `ledPin1` sampai `ledPin3`.
- LED mati, kondisi dimana saat ketiga button tidak ditekan.

**Kesimpulan**

Program ini memiliki keluaran dimana jika button 1 ditekan akan menghasilkan LED menyala semua, jika button 2 ditekan akan menghasilkan LED 1 dan LED 2 menyala, jika button 3 ditekan akan menghasilkan LED menyala secara bergantian.
