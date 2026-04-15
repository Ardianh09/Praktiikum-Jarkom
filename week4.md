#### NIM : 103072400098
#### Kelas : IF-04-04
# SOAL 1
# Pertanyaan
1. Cari pesan permintaan DNS dan balasannya. Apakah pesan tersebut dikirimkan melalui UDP 
atau TCP? 
2. Apa port tujuan pada pesan permintaan DNS? Apa port sumber pada pesan balasannya? 
3. Pada pesan permintaan DNS, apa alamat IP tujuannya? Apa alamat IP server DNS lokal anda 
(gunakan ipconfig untuk mencari tahu)? Apakah kedua alamat IP tersebut sama? 
4. Periksa pesan permintaan DNS. Apa “jenis” atau ”type” dari pesan tersebut? Apakah pesan 
permintaan tersebut mengandung ”jawaban” atau ”answers”? 
5. Periksa pesan balasan DNS. Berapa banyak ”jawaban” atau ”answers” yang terdapat di 
dalamnya? Apa saja isi yang terkandung dalam setiap jawaban tersebut? 
6. Perhatikan paket TCP SYN yang selanjutnya dikirimkan oleh host Anda. Apakah alamat IP 
pada paket tersebut sesuai dengan alamat IP yang tertera pada pesan balasan DNS? 
7. Halaman web yang sebelumnya anda akses (http://www.ietf.org) memuat beberapa 
gambar. Apakah host Anda perlu mengirimkan pesan permintaan DNS baru setiap kali ingin 
mengakses suatu gambar?

# Jawaban : 

1. 
<img width="1263" height="720" alt="image" src="https://github.com/user-attachments/assets/7a0aad6c-35f7-4ed9-9c02-ae86f71f7273" />
<img width="1269" height="724" alt="image" src="https://github.com/user-attachments/assets/1042970d-2345-46d7-a253-1f396b5e7fe0" />
Protokol yang digunakan pada DNS
Pesan permintaan (query) dan balasan (response) DNS pada umumnya dikirimkan menggunakan UDP (User Datagram Protocol).
Hal ini karena UDP lebih cepat dan ringan dibandingkan TCP, sehingga cocok untuk proses pencarian alamat IP yang membutuhkan respon cepat.

---

2. 
<img width="1267" height="724" alt="image" src="https://github.com/user-attachments/assets/685b75e4-6637-4ebe-9d31-606d35bc4ee4" />
<img width="1271" height="723" alt="image" src="https://github.com/user-attachments/assets/cfde992a-0b44-4d2d-b6ec-debb19590da2" />

Port yang digunakan
Port tujuan pada permintaan DNS: 53
Port sumber pada balasan DNS: 53
Port 53 merupakan port standar yang digunakan oleh layanan DNS baik untuk permintaan maupun balasan.

---

3. 
<img width="1273" height="727" alt="image" src="https://github.com/user-attachments/assets/6cb8dd9a-662f-4198-b4b7-b391c799b192" />
<img width="1508" height="688" alt="ss" src="https://github.com/user-attachments/assets/c8b46c0e-d6a7-40dc-ac91-ce8bb7691fbd" />
Alamat IP tujuan dan DNS lokal
Alamat IP tujuan pada pesan permintaan DNS adalah alamat IP server DNS (biasanya DNS lokal dari ISP atau jaringan).
Alamat IP DNS lokal dapat dilihat menggunakan perintah ipconfig pada komputer.

---

4. 
<img width="1266" height="726" alt="image" src="https://github.com/user-attachments/assets/8403aeff-1319-44c0-902a-f227625703ec" />
Jenis (Type) pesan DNS
Jenis pesan pada permintaan DNS adalah Type A (Host Address), yang digunakan untuk menerjemahkan nama domain menjadi alamat IP (IPv4).
Pesan permintaan DNS tidak mengandung jawaban (answers), karena hanya berisi permintaan informasi.

---

5. 
<img width="1273" height="720" alt="image" src="https://github.com/user-attachments/assets/a698a030-ad33-43a0-a5a0-a6ac77a8dd45" />
Isi pesan balasan DNS
Pada pesan balasan DNS terdapat 2 buah jawaban (answers).
Setiap jawaban biasanya berisi:
Nama domain (misalnya: www.ietf.org
)
Tipe record (A)
Alamat IP hasil resolusi
Time To Live (TTL)

---

6.
Kesesuaian IP pada paket TCP SYN
Alamat IP yang terdapat pada paket TCP SYN sesuai dengan alamat IP yang diberikan pada pesan balasan DNS.
Artinya, setelah mendapatkan IP dari DNS, host langsung menggunakan IP tersebut untuk melakukan koneksi ke server tujuan.

---

7. 
Apakah perlu DNS request untuk setiap gambar?
Tidak. Host tidak perlu mengirimkan permintaan DNS baru setiap kali mengakses gambar pada halaman yang sama (misalnya dari IETF).
Hal ini karena:
Alamat IP sudah diketahui dari hasil DNS sebelumnya
Browser menyimpan cache DNS
Gambar biasanya berada pada domain/server yang sama

---
---

# SOAL 2

# Pertanyaan
## Perintah nslookup www.mit.edu
1. Apa port tujuan pada pesan permintaan DNS? Apa port sumber pada pesan balasan DNS? 
2. Ke alamat IP manakah pesan permintaan DNS dikirimkan? Apakah alamat IP tersebut 
merupakan default alamat IP server DNS lokal Anda? 
3. Periksa pesan permintaan DNS. Apa ”jenis” atau ”type” dari pesan tersebut? Apakah pesan 
tersebut mengandung ”jawaban” atau ”answers”? 
4. Periksa pesan balasan DNS. Berapa banyak ”jawaban” atau “answers” yang terdapat di 
dalamnya. Apa saja isi yang terkandung dalam setiap jawaban tersebut? 
# Jawaban : 

1. 
<img width="858" height="489" alt="image" src="https://github.com/user-attachments/assets/db46ae1d-f396-4c8a-b65f-0706d1f0ecb4" />
<img width="858" height="488" alt="image" src="https://github.com/user-attachments/assets/05d8524a-a864-4178-9b2f-451ceb37ea93" />
Port tujuan pada pesan permintaan DNS adalah 53, karena DNS menggunakan port tersebut sebagai standar komunikasi. Sedangkan port sumber pada pesan balasan DNS juga 53, yang menandakan bahwa balasan berasal dari server DNS.

---

2. 
<img width="862" height="492" alt="image" src="https://github.com/user-attachments/assets/84d7832b-33c4-4058-9414-8f59c96f1860" />
<img width="859" height="505" alt="image" src="https://github.com/user-attachments/assets/976a572f-4e23-452d-b590-c36a03ecdb88" />
Pesan permintaan DNS dikirimkan ke alamat IP 10.221.193.2. Alamat IP tersebut merupakan default DNS server lokal yang digunakan oleh perangkat saya, sehingga semua permintaan resolusi domain pertama kali dikirim ke server tersebut.

---

3.
<img width="863" height="497" alt="image" src="https://github.com/user-attachments/assets/73fd1b86-8c74-42c0-b139-b8d4401746d0" />
Jenis (type) dari pesan permintaan DNS adalah AAAA, yang berarti permintaan ditujukan untuk memperoleh alamat IPv6 dari suatu domain. Pesan permintaan ini tidak mengandung jawaban (answers) karena hanya berfungsi sebagai query atau permintaan ke server DNS.

---

4.
<img width="860" height="483" alt="image" src="https://github.com/user-attachments/assets/63b9d1aa-b609-4bce-a99c-59ec5c93bf10" />
Pada pesan balasan DNS, terdapat 4 jawaban (answers). Setiap jawaban berisi informasi sebagai berikut:

1. Nama domain yang diminta
2. Tipe record (AAAA)
3. Alamat IP versi 6 (IPv6) dari domain tersebut
4. TTL (Time To Live) yang menunjukkan lama data dapat disimpan dalam cache
