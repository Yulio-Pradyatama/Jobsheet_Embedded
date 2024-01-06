# PWM (Pulse Width Modulation)
Merupakan metode perubahan lebar pulsa untuk menghasilkan nilai tegangan analog yang diinginkan. Pin yang difungsikan sebagai PWM analog
output akan mengeluarkan sinyal pulsa digital dengan frekuensi 5000 Hz yang mana nilai tegangan analog diperoleh dengan mengubah duty cycle atau perbandingan lamanya pulsa HIGH terhadap periode (T) dari sinyal digital tersebut.

Terdapat 2 percobaan yang dilakukan :

## 1. Membuat efek fade pada LED Berkedip dengan menggunakan PWM
**Alat dan Bahan**
- ESP32 (1 buah)
- LED (1 buah)
- Resistor 220 Ohm (1 buah)
- Kabel Jumper (secukupnya)

**Skema Rangkaian**

![Skematik (Job 1-B)](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/3f0760d2-d9eb-4aab-a234-b688ef62fd7e)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/B%20(PWM)/PWM1/PWM1.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/1326d238-dcec-474a-b6df-41129977a31f)

**Flowchart**

![Flowchart Job1 B-1](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/dfffb900-8fdf-4bb0-8a5a-53239ca34066)

**Hasil dan Pembahasan**

![Job 1B_1](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/9364bc58-fb14-49c2-b333-051d0a8ef9af)

Program ini memiliki hasil untuk mengontrol kecerahan cahaya LED. Menggunakan dua kondisi `for()`, dimana dalam setiap `for()` terdapat variabel `dutyCycle` untuk mengontrol kecerahan LED dari nilai 0 sampai 255. Frekuensi yang digunakan yaitu 5000 Hz dengan nilai resolusi 8 bit, dimana semakin tinggi nilai resolusinya perubahan tingkat kecerahan akan semakin halus.

**Kesimpulan**

Program ini menghasilkan tingkat kecerahan LED dari rendah ke tinggi sampai kembali ke rendah lagi.

## 2. Mengendalikan 3 buah LED dengan menggunakan PWM
**Alat dan Bahan**

- ESP32 (1 buah)
- LED (3 buah)
- Resistor 220 Ohm (3 buah)
- Kabel Jumper (secukupnya)

**Skema Rangkaian**

![Skematik (Job 1-B)](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/a0b4743d-f632-4af1-8a28-5b65060eacbb)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/B%20(PWM)/PWM2/PWM2.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/bae3c01b-7cb2-4c14-8680-7968bc11bbae)

**Flowchart**

![Flowchart Job1 B-2](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/369cf872-dd94-4084-8ce0-409afbe29897)

**Hasil dan Pembahasan**

![Job 1B_2](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/2bd4008b-b1fa-4960-8ae7-ec75085a26d2)

Program ini sebenarnya memiliki konsep yang sama dengan program sebelumnya, dengan menambahkan 2 LED untuk diimplementasikan pada program ini. Kemudian tambahkan variabel untuk identitas pin masing-masing LED tambahan, selaint itu pada fungsi `setup()` tambahkan perintah `ledAttachPin()` untuk mengaktifkan konfigurasi PWM pada dua pin GPIO (LED 2 dan LED 3).

*Kesimpulan**

Program ini menghasilkan tingkat kecerahan 3 LED hanya dengan menggunakan satu saluran PWM.
