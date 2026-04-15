#### Nama : Ardian Hoart
#### NIM : 103072400098
#### Kelas : IF-04-04
# Pertanyaan
1. Pilih satu paket UDP yang terdapat pada trace Anda. Dari paket tersebut, berapa banyak 
“field” yang terdapat pada header UDP? Sebutkan nama-nama field yang Anda temukan! 
2. Perhatikan informasi “content field” pada paket yang Anda pilih di pertanyaan 1. Berapa 
panjang (dalam satuan byte) masing-masing “field” yang terdapat pada header UDP? 
3. Nilai yang tertera pada ”Length” menyatakan nilai apa? Verfikasi jawaban Anda melalui 
paket UDP pada trace. 
4. Berapa jumlah maksimum byte yang dapat disertakan dalam payload UDP? (Petunjuk: 
jawaban untuk pertanyaan ini dapat ditentukan dari jawaban Anda untuk pertanyaan 2) 
5. Berapa nomor port terbesar yang dapat menjadi port sumber? (Petunjuk: lihat petunjuk 
pada pertanyaan 4) 
6. Berapa nomor protokol untuk UDP? Berikan jawaban Anda dalam notasi heksadesimal dan 
desimal. Untuk menjawab pertanyaan ini, Anda harus melihat ke bagian ”Protocol” pada 
datagram IP yang mengandung segmen UDP. 
7. Periksa pasangan paket UDP di mana host Anda mengirimkan paket UDP pertama dan paket 
UDP kedua merupakan balasan dari paket UDP yang pertama. (Petunjuk: agar paket kedua merupakan balasan dari paket pertama, pengirim paket pertama harus menjadi tujuan dari 
paket kedua). Jelaskan hubungan antara nomor port pada kedua paket tersebut!
# Jawaban :
1. Jumlah dan Nama Field pada Header UDP
Header pada protokol UDP memiliki 4 field utama, yaitu:

- Source Port → Menunjukkan port pengirim
- Destination Port → Menunjukkan port tujuan
- Length → Menunjukkan panjang total segmen UDP
- Checksum → Digunakan untuk pengecekan error data
<img width="1267" height="713" alt="image" src="https://github.com/user-attachments/assets/cab70169-ad1b-4cc5-a05b-54a5a5e86991" />

---

2. Panjang Masing-Masing Field
Setiap field pada header UDP memiliki ukuran yang sama, yaitu:

- Source Port = 2 byte
- Destination Port = 2 byte
- Length = 2 byte
- Checksum = 2 byte
Total panjang header UDP = 8 byte
<img width="1264" height="714" alt="image" src="https://github.com/user-attachments/assets/88191b1a-9874-4159-975f-ccf7fe28ea2d" />

---

3. Nilai yang tertera pada field “Length” menunjukkan total panjang segmen UDP, yang mencakup keseluruhan header UDP dan data (payload) yang dikirimkan.
Sebagai contoh, jika nilai Length = 58 byte, maka nilai tersebut terdiri dari:

- 8 byte untuk header UDP
- 50 byte untuk payload (data)

Dengan demikian, dapat disimpulkan bahwa:
Length = ukuran header + ukuran payload
<img width="1269" height="715" alt="image" src="https://github.com/user-attachments/assets/2afb2723-d116-4c12-a3af-eb4700e01346" />

---

4. Langkah-langkah:
Maksimum Payload UDP
Diketahui:
Field Length = 2 byte = 16 bit
Nilai maksimum = 2¹⁶ - 1 = 65.535 byte

Rumus:
Payload maksimum = 65.535 – 8

Hasil:
Payload maksimum = 65.527 byte (~64 KB)
<img width="1264" height="710" alt="image" src="https://github.com/user-attachments/assets/6eea8a61-5b23-4826-bd2e-99c5507b8f10" />

---

5. Nomor Port Maksimum
Karena port menggunakan 16 bit, maka:
Nilai maksimum = 2¹⁶ - 1 = 65.535

---

6. Nomor Protokol UDP
Pada header IP, UDP memiliki nilai:
Desimal: 17
Heksadesimal: 0x11
Field ini dapat ditemukan pada bagian “Protocol” di datagram IP.
<img width="1266" height="656" alt="image" src="https://github.com/user-attachments/assets/76fad434-69ca-4092-ab5d-4e1c7c164489" />

---

7. Hubungan Nomor Port pada Paket UDP
Dalam komunikasi UDP antara dua host:
Paket pertama (request):
Source Port = A
Destination Port = B
Paket kedua (reply):
Source Port = B
Destination Port = A
<img width="1268" height="715" alt="image" src="https://github.com/user-attachments/assets/481d3dd8-10c3-4570-8c86-4f90f4db8671" />
<img width="1267" height="716" alt="image" src="https://github.com/user-attachments/assets/939dc0c2-65e1-4b1e-bda5-630037694184" />
