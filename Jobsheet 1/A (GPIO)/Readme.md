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

![Skematik (Job 1-A)](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/66c26000-428d-4d83-95aa-9acc5118c28d)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/tree/main/Jobsheet%201/A%20(GPIO)/1._Langkah_2.ino/1._Langkah_2.ino.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/6fdb5909-513d-4e39-92b7-99230cfb9cc6)

**Flowchart**

![Flowchart Job1 A-2](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/cde437ea-2f4a-4ac4-a70b-d957d6386fb9)


**Hasil dan Pembahasan**

![Job 1A_2](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/f2d83b66-ab0b-4652-923e-cf0927875a22)

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

![Skematik (Job 1-A)](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/66c26000-428d-4d83-95aa-9acc5118c28d)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/A%20(GPIO)/1._Langkah_3.ino/1._Langkah_3.ino.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/8c5b6f6a-76ef-4e4e-a3d5-bf5fa6002ee1)


**Flowchart**

![Flowchart Job1 A-3](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/8881fd0b-b384-4144-86a7-54ffc5afdbee)

**Hasil dan Pembahasan**

![Job 1A_3](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/26d0fab2-db22-4e74-8843-61296125cf6d)

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

![Skematik (Job 1-A 4)](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/e328903d-42a6-41aa-88fd-4aa85b0f4d53)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/A%20(GPIO)/1._Langkah_4.ino/1._Langkah_4.ino.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/c62988bb-b9e0-49b8-a084-a6ad83eccb2a)

**Flowchart**

![Flowchart Job1 A-4](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/babf0559-e508-4dbb-adc7-f2d19848528a)

**Hasil dan Pembahasan**

![Job 1A_4](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/3ec1ab7c-023f-425a-a32d-bdd115286f46)

Program ini merupakan lanjutan dari percobaan sebelumnya, dimana terdapat tambahan 1 buah LED dan 1 buah push button. Untuk itu kita harus memulai dengan mendeklarasikan pin GPIO untuk dua push button (`buttonPin1` dan `buttonPin2`) serta dua LED (`ledPin1` dan `ledPin2`).

Dalam fungsi `setup()`, pin-pin diatur sesuai dengan fungsinya, yaitu push button sebagai input dan LED sebagai output.

Dalam fungsi `loop()`, status dari kedua push button dibaca dan dicetak ke Serial Monitor. Selanjutnya, terdapat sebuah fungsi yang mengatur perilaku LED berdasarkan status push button:

   - Jika `buttonState2` (status dari push button kedua) adalah HIGH, maka LED akan berkedip bergantian dengan interval 0.5 sekon atau 500 ms.
   - Jika `buttonState1` (status dari push button pertama) adalah HIGH, maka kedua LED akan menyala bersamaan.
   - Jika keduanya tidak ditekan, kedua LED dimatikan.

Program ini secara umum memahami input dari push button dan mengendalikan LED sesuai dengan kondisi push button tersebut. 

**Kesimpulan**

Program ini berfungsi menghasilkan efek LED berkedip hanya ketika button ke-2 ditekan, dan hanya menyalakan (tidak berkedip) kedua LED ketika button ke-1 ditekan. Selain itu, kondisi dari setiap button juga tercatat pada serial monitor.

## 4. Membuat Running LED saat penekanan button
**Alat dan Bahan**
- ESP32 (1 buah)
- LED (3 buah)
- Resistor 220 Ohm (3 buah)
- Resistor 10 kOhm (3 buah)
- Push Button (3 buah)
- Kabel Jumper (secukupnya)

**Skema Rangkaian**

![Skematik (Job 1-A 5)](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/8491d78c-4a90-47d6-b3db-aebf0a23ed17)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/A%20(GPIO)/1._Langkah_5.ino/1._Langkah_5.ino.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/31b5430e-3301-4ad6-8060-00b7a55ce519)

**Flowchart**

![Flowchart Job1 A-5](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/31e30171-5ef0-4212-a99e-9f98bda54f54)

**Hasil dan Pembahasan**

![Job 1A_5](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/dba1458c-f8e8-429f-a66c-c3fba2d6dd6d)

Running LED merupakan beberapa lampu LED yang menyala bergantian dengan rapi (kiri ke kanan atau sebaliknya), maka setidaknya dibutuhkan 3 lampu LED untuk menerapkannya. Sama seperti sebelumnya, kita hanya menambahkan satu buah push button sekali lagi dan juga setidaknya 1 buah LED. Agar program kita terlihat lebih efisien, kita bisa menggunakan function `for()`. `For()` merupakan suatu fungsi berupa proses pengulangan tugas/kegiatan pada suatu statement atau lebih secara berulang ulang-ulang selama yang dijadikan acuan tersebut terpenuhi dengan baik.

Setelah itu kita deklarasikan beberapa pin GPIO untuk push button (`buttonPin1`, `buttonPin2`, dan `buttonPin3`) dan LED (`ledPin1`, `ledPin2`, dan `ledPin3`).

Berbeda dari sebelumnya yang langsung menggunakan digitalWrite(HIGH dan LOW) pada LED PIN, kali ini kita memanfaatkann fungsi for untuk mengulang programnya. Untuk itu kita harus membuat sebuah array bernama `pinLED` yang nantinya digunakan untuk menyimpan pin dari tiga LED. Kita hanya memasukkan saja nomor pin dari semua `pinLED` ke array tersebut secara urut (karena saya menginginkan LED menyala dari kiri ke kanan, maka disini saya mengurutkan dari ledPin1 hingga ledPin 3), setelah itu kita outputkan menggunakan fungsi `for()`.

Dalam fungsi `setup()`, pin-pin diatur sesuai dengan fungsinya, yaitu push button sebagai input dan LED sebagai output. Sedangkan fungsi `for()` saya gunakan untuk mengatur semua isi array `pinLED` menjadi output.

Dalam fungsi `loop()`, status dari ketiga push button dibaca dan dicetak ke Serial Monitor. Selanjutnya, terdapat kondisional yang mengatur perilaku LED berdasarkan status push button:

   - Jika `buttonState1` (status dari push button pertama) adalah HIGH, maka ketiga LED akan menyala bersamaan.
   - Jika `buttonState2` (status dari push button kedua) adalah HIGH, maka LED 1 dan LED 2 akan berkedip bergantian dengan interval waktu 500 ms.
   - Jika `buttonState3` (status dari push button ketiga) adalah HIGH, maka ketiga LED akan berkedip secara bergantian. Masing-masing LED akan menyala dan mati dengan interval waktu 500 ms yang dijalankan menggunakan `for()`.

**Kesimpulan**

Program ini menunjukkan implementasi yang baik dalam mengendalikan beberapa LED dengan beberapa push button. Ketika push button pertama ditekan, ketiga LED akan menyala secara bersamaan. Jika push button kedua ditekan, LED pertama akan menyala, kemudian mati, diikuti oleh LED kedua yang menyala dan mati. Sedangkan saat push button ketiga ditekan, ketiga LED akan berkedip bergantian. Kita juga dapat memanfaatkan penggunaan fungi `for()` untuk membuat running LED.
