# Modul 11 — DHCP (Dynamic Host Configuration Protocol)
### Mekanisme Pengalamatan Dinamis menggunakan Wireshark

---

## Dasar Teori (Proses DORA)
Dynamic Host Configuration Protocol (DHCP) adalah protokol yang digunakan untuk memberikan konfigurasi jaringan secara otomatis kepada perangkat yang terhubung ke jaringan. Konfigurasi tersebut meliputi alamat IP, subnet mask, default gateway, dan DNS server.

Proses pemberian alamat IP dilakukan melalui empat tahapan utama yang dikenal sebagai DORA (Discover, Offer, Request, Acknowledgement):

1. DHCP Discover
Client mengirimkan pesan broadcast untuk mencari server DHCP yang tersedia di jaringan.
2. DHCP Offer
Server DHCP merespons dengan menawarkan alamat IP beserta informasi konfigurasi jaringan lainnya.
3. DHCP Request
Client memilih dan meminta secara resmi alamat IP yang ditawarkan oleh server.
4. DHCP ACK (Acknowledgement)
Server mengonfirmasi bahwa alamat IP tersebut telah diberikan kepada client dan dapat digunakan selama masa sewa (lease time) tertentu.

---

## Langkah Praktikum
1. Jalankan Wireshark, pilih interface jaringan yang aktif.
2. Terapkan filter `dhcp` atau `bootp`.
3. Buka Terminal/CMD sebagai Administrator.
4. Jalankan `ipconfig /release` untuk melepas IP yang sedang dipakai.
<img width="716" height="546" alt="image" src="https://github.com/user-attachments/assets/02f0b266-89d9-412a-b75a-2d48f3403639" />
5. Mulai capture di Wireshark.
6. Jalankan `ipconfig /renew` untuk meminta IP baru dari server DHCP.
<img width="693" height="591" alt="image" src="https://github.com/user-attachments/assets/b759f422-f723-4708-b095-8fc7e25a20fc" />
7. Setelah beberapa detik, hentikan capture.
<img width="712" height="386" alt="image" src="https://github.com/user-attachments/assets/02930a29-81df-408c-824f-9e3f15ed40a6" />

---

## Analisis Paket DHCP

### 1. Lapisan Transport
DHCP bekerja pada lapisan aplikasi dan menggunakan protokol UDP (User Datagram Protocol) sebagai media transportasinya karena tidak memerlukan pembentukan koneksi terlebih dahulu.

Informasi port yang digunakan:
Source Port: 68 (DHCP Client)
Destination Port: 67 (DHCP Server)

Penggunaan UDP memungkinkan proses konfigurasi jaringan berlangsung lebih cepat dan efisien.
### 2. Identifikasi Pesan DORA
| Tipe Pesan | Source IP | Destination IP | Keterangan |
|---|---|---|---|
| Discover | `0.0.0.0` | `255.255.255.255` | Broadcast mencari server |
| Offer | `10.218.0.253` | `10.218.2.21` | Tawaran IP dari server |
| Request | `0.0.0.0` | `255.255.255.255` | Permintaan resmi dari client |
| ACK | `10.218.0.253` | `10.218.2.21` | Konfirmasi dari server |

### 3. Field Penting pada Header DHCP
* **Transaction ID** — angka unik (contoh: `0xbc42c45e`) yang dipakai untuk mencocokkan request client dengan response server yang sesuai, terutama saat ada beberapa proses DORA berjalan hampir bersamaan.
* **Client IP Address** — alamat IP yang ditawarkan server kepada client.

---

## Kesimpulan
Berdasarkan hasil pengamatan menggunakan Wireshark, dapat disimpulkan bahwa DHCP bekerja melalui mekanisme DORA (Discover, Offer, Request, ACK) untuk memberikan alamat IP secara otomatis kepada client. Seluruh komunikasi berlangsung menggunakan protokol UDP pada port 67 dan 68.
Penggunaan alamat broadcast 255.255.255.255 pada tahap awal diperlukan karena client belum memiliki alamat IP yang valid. Selain itu, Transaction ID berperan penting dalam memastikan setiap respons server dapat dicocokkan dengan permintaan client yang sesuai.
Dengan adanya DHCP, proses konfigurasi jaringan menjadi lebih cepat, efisien, dan mengurangi kemungkinan kesalahan konfigurasi IP secara manual.
