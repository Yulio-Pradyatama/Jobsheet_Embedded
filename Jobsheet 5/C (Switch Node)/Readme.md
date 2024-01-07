# Switch Node
Pada percobaan ini kita akan menggunakan `switch node` untuk memproses suatu data yang akan dikirimkan.

### Alat dan Bahan

Software :

- Ubuntu Virtual Machine
- Node-red

Node :
- Inject (2 buah)
- Debug (2 buah)
- Switch (1 buah)

### Program 
<a href="https://github.com/cakjung/Jobsheet-Embedded/blob/main/Jobsheet%205/C%20(Switch%20Node)/flows%20(Job%205-C).json">(File flows.json)</a>

![image](https://github.com/cakjung/Jobsheet-Embedded/assets/128274951/eebc83b6-18fe-4ca4-b4cb-3445791de972)

### Flowchart

![Flowchart Job 5-C](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/2a26a24e-40fb-4037-b618-1ee982f6efac)

### Hasil dan Pembahasan

![Job 5-C](https://github.com/Yulio-Pradyatama/Jobsheet_Embedded/assets/153850000/1bee3c26-df9b-4c32-a351-d7bd40a711ab)

Inject Node memiliki payload dengan isi berupa angka 30 dan 27. Pesan tadi akan dikirimkan ke Switch Node yang berfungsi sebagai percabangan berdasarkan kondisi yang sudah diatur. Dalam Switch Node, pesan dengan angka 30 akan dikirimkan ke Debug Node dengan nama ">28", sedangkan untuk nilai 27 akan dikirimkan ke Debug Node dengan nama "<=28". Kemudian di Debug Node pesan tersebut akan ditampilkan pada konsol debug sesuai dengan kondisi yang sudah di atur di Switch Node.

**Kesimpulan**

Penggunaan Switch Node untuk membagi alur berdasarkan nilai payload yang dikirim oleh Inject Node dan fungsi Debug Node untuk menampilkan hasilnya pada konsol debug.
