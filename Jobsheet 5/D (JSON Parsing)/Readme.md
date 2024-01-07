# JSON Parsing
Pada percobaan ini kita akan menggunakan `JSON Parser` untuk memproses suatu data yang memiliki tipe data JSON.

### Alat dan Bahan

Software :

- Ubuntu Virtual Machine
- Node-red

Node :
- Inject (1 buah)
- Debug (1 buah)
- Function (1 buah)
- Json Parser (1 buah)

### Program 
<a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%205/D%20(JSON%20Parsing)/flows%20(Job%205-D).json">(File flows.json)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/cb634b7a-fec3-433a-9788-41ad0c7ab590)

### Flowchart

![Flowchart Job 5-D](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/2a9cd7c0-0f21-4bda-b934-7ce57348bec5)

### Hasil dan Pembahasan

![Job 5-D](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/dddf8fe7-afae-4826-aa63-ef2fcf7749d0)

Program ini memiliki alur kerja:
- Inject Node mengirimkan payload JSON ke topik `/sensor`.
- JSON Node akan mengkonversi payload JSON menjadi objek JSON yang kemudian dikirimkan ke Fuction Node.
- Fuction Node akan mengekstrak nilai suhu dari onjek tadi dan akan mengaturnya menjadi payload baru.
- isi payload baru akan ditampilkan di konsol debug.

**Kesimpulan**

Program ini dapat digunakan untuk mensimulasikan pengolahan data dari sensor suhu.
