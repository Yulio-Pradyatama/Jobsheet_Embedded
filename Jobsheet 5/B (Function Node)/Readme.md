# Function Node
Pada percobaan ini kita akan menggunakan `function node` untuk memproses suatu data yang akan dikirimkan. Terdapat 2 percobaan yang akan dilakukan:

## 1. Function Node Bawaan (Tanpa Pemrograman)
**Alat dan Bahan**

Software :

- Ubuntu Virtual Machine
- Node-red

Node :

- Inject (1 buah)
- Debug (1 buah)
- Function (1 buah)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%205/B%20(Function%20Node)/flows%20(Job%205-B1).json">(File flows.json)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/7b2a31d3-51fb-4eb8-b0d2-b5f438482c8a)

**Flowchart**

![Flowchart Job 5-B1](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/89f767d6-b05a-488e-8623-f829f7bb33c3)

**Hasil dan Pembahasan**

![Job 5-B1](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/1f54e6ea-3dc4-4b2b-92e8-43eeb30415c0)

Program Node-RED ini memiliki alur kerja sebagai berkut:
- Inject Node akan mengirimkan pesan dengan topik `test1` dan pesan payload `Hello World`.
- Function Node sebagai perantara untuk meneruskan pesan dari Inject Node ke Debug.
- Debug Node akan menampilkan pesan dari Inject Node ke konsol debug.

**Kesimpulan**

Program ini berguna untuk memberikan pemahaman mengenai Node-RED yang dapat membuat alur kerja yang terdiri dari penerimaan, pemrosesan, dan penampilan data.

## 2. Memprogram Function Node
**Alat dan Bahan**

Software :

- Ubuntu Virtual Machine
- Node-red

Node :

- Inject (2 buah)
- Debug (1 buah)
- Function (2 buah)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%205/B%20(Function%20Node)/flows%20(Job%205-B2).json">(File flows.json)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/361f4432-2625-4127-b7a3-978ac97ac9d8)

**Flowchart**

![Flowchart Job 5-B2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/8080d230-13e5-4543-a2df-8dd8c040f05f)

**Hasil dan Pembahasan**

![Job 5-B2](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/2a666e97-a35d-43a3-8607-c5e62731f4bb)

Program ini memiliki 2 Inject Node, 1 Function Node, dan 2 Debug Node. Dimana isi dari konfigurasi Inject Node :
- `Input1` mengirimkan pesan dengan topik `test1` dan payload `Hello World`.
- `Input2` mengirimkan pesan dengan topik `test2` dan payload `Expeliarmus`.

Function Node akan menerima kedua pesan dari Inject Node dan akan mengirimkan kedua pesan tadi ke Debug Node sesuai dengan nilai topik yang sudah di atur di Inject Node, yaitu topik `test1` akan diarahkan ke `outpu1` dan begitu juga dengan topik `test2` akan diarahkan ke `output2`.

Pada Debug Node, `output1` akan menampilkan pesan berisi "Hello World" dan `output2` akan menampilkan pesan yang berisi "Expeliarmus".

**Kesimpulan**

Program ini dapat memberikan pemahaman bahwa penggunaan Node-RED dapat mengarahkan pesan berdasarkan nilai topik yang sudah diatur.
