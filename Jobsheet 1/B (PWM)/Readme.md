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

![Skematik (Job 1-B)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/1659a3ed-0f9d-45ee-929f-0654043d95d2)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/B%20(PWM)/PWM1/PWM1.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/1326d238-dcec-474a-b6df-41129977a31f)

**Flowchart**

![Flowchart Job1 B-1](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/b46e03ec-f391-446a-9a10-54c6e4910ed3)

**Hasil dan Pembahasan**

![Job 1B_1](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/ffde0713-f004-4584-8a31-2ac2ebff1d74)

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

![Skematik (Job 1-B)](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/1659a3ed-0f9d-45ee-929f-0654043d95d2)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%201/B%20(PWM)/PWM2/PWM2.ino">(File .ino)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/bae3c01b-7cb2-4c14-8680-7968bc11bbae)

**Flowchart**

![Flowchart Job1 B-2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/2c06826e-8d49-4ab7-9bed-09c9c8f46dc9)

**Hasil dan Pembahasan**

![Job 1B_2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/e976ce8a-b5cc-41a4-b000-52449cb9aa79)

Program ini sebenarnya memiliki konsep yang sama dengan program sebelumnya, dengan menambahkan 2 LED untuk diimplementasikan pada program ini. Kemudian tambahkan variabel untuk identitas pin masing-masing LED tambahan, selaint itu pada fungsi `setup()` tambahkan perintah `ledAttachPin()` untuk mengaktifkan konfigurasi PWM pada dua pin GPIO (LED 2 dan LED 3).

*Kesimpulan**

Program ini menghasilkan tingkat kecerahan 3 LED hanya dengan menggunakan satu saluran PWM.
