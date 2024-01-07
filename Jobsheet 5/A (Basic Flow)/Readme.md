# Basic Flow
Simulasi awal menggunakan Node-RED : melakukan pengujian pengiriman pada node `input` dan menampilkannya pada node `output`

**Alat dan Bahan**

Software :

- Ubuntu Virtual Machine
- Node-red

Node :

- Inject (1 buah)
- Debug (1 buah)

**Program** <a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%205/A%20(Basic%20Flow)/flows%20(Job%205-A).json">(File flows.json)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/a07741c5-707b-4588-bf9f-f6d1d3c45e24)

**Flowchart**

![Flowchart Job 5-A](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/29937c10-3207-4ae2-9cba-50caa01af562)

**Hasil dan Pembahasan**

![Job 5-A](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/b2f5c23c-3b04-45eb-b8c8-bcc27f12929a)

Program Node-RED ini terdiri dari dua elemen, yaitu `Inject Node` dan `Debug Dode`.
Konfigurasi Inject Node:
- payload : berguna untuk menentukan yang akan dikirimkan, dalam program "Hello World".
- topic : menentukan topik untuk pesan yang akan dihasilkan, dalam program "test".
- once delay : menunda eksekusi node selama 0,1 detik setelah program dijalankan.

Konfigurasi Debug Node:
- active : True, menandakan bahwa node ini aktif.
- complete : payload, menandakan output debug akan menampilkan pesan dari payload.
- target type : msg, menandakan hanya payload yang akan ditampilkan pada outputan.

**Kesimpulan**

Program ini secara otomatis akan mengirimkan pesan payload "Hello World" ke program setiap kali dimulai dan nantinya pesan tersebut akan ditampilkan dalam output debug.
