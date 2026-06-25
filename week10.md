# Modul 10 — IP (Internet Protocol)

### Datagram IPv4 dan IPv6 menggunakan Wireshark

---

## Alat yang Perlu Disiapkan
Beberapa perangkat lunak yang digunakan pada praktikum ini antara lain:
Wireshark — digunakan untuk menangkap (capture) dan menganalisis paket yang melintas di jaringan.
Terminal/CMD — digunakan untuk menjalankan perintah seperti ping dan traceroute/tracert.
Browser — digunakan untuk menghasilkan trafik jaringan tambahan yang dapat diamati melalui Wireshark.

---

## Hasil Analisis IPv4
Capture dilakukan sambil menjalankan `tracert gaia.cs.umass.edu`. Berikut analisis header IPv4 pada paket ICMP Echo Request yang dikirim:
| Field | Nilai | Keterangan |
|---|---|---|
| Source Address | `192.168.56.1` | Alamat IP pengirim |
| Destination Address | `128.119.245.12` | Alamat IP server tujuan |
| Protocol | `ICMP (1)` | Protokol lapisan atas yang dibawa |
| Header Length | `20 byte` | Ukuran header standar tanpa opsi tambahan |
| Total Length | `92 byte` | Total ukuran header + payload |

<img width="1011" height="540" alt="image" src="https://github.com/user-attachments/assets/9f895808-632d-4829-ba7c-d045d2a9d457" />

### Analisis Time to Live (TTL)
Field Time To Live (TTL) berfungsi untuk membatasi umur paket saat berada di jaringan. Setiap kali paket melewati sebuah router atau hop, nilai TTL akan berkurang satu. Dengan mengamati nilai TTL pada paket balasan dari setiap hop, kita dapat memperkirakan seberapa jauh posisi router tersebut dari host pengirim.
Apabila nilai TTL mencapai angka 0, router akan menghentikan perjalanan paket dan mengirimkan pesan ICMP Time Exceeded kembali ke pengirim. Mekanisme inilah yang dimanfaatkan oleh utilitas traceroute/tracert untuk mengetahui jalur yang dilewati paket dari sumber menuju tujuan.
<img width="1013" height="540" alt="image" src="https://github.com/user-attachments/assets/6c097427-6f52-4b2a-9c29-0bc37ccf6d5a" />

---

## Investigasi IPv6
Dibandingkan IPv4, datagram IPvBaik IPv4 maupun IPv6 memiliki fungsi utama yang sama, yaitu menyediakan mekanisme pengalamatan dan pengiriman paket data dari sumber menuju tujuan melalui jaringan. Selain itu, header IP juga memuat informasi penting yang mendukung proses routing dan pengendalian lalu lintas jaringan, seperti penggunaan TTL pada IPv4 untuk mencegah paket beredar tanpa batas akibat routing loop. Meskipun memiliki tujuan yang sama, IPv6 menawarkan ruang alamat yang jauh lebih besar serta struktur header yang lebih sederhana sehingga mampu memberikan efisiensi dan skalabilitas yang lebih baik dibandingkan IPv4.6 punya beberapa perbedaan mendasar:
* **Alamat IPv6** memakai format 128-bit, jauh lebih panjang dari IPv4 yang hanya 32-bit, sehingga ruang alamatnya jauh lebih luas.
* **Header IPv6** dibuat lebih sederhana dengan ukuran tetap 40 byte. Field-field seperti *Checksum* dan *Fragmentation* yang ada di IPv4 dihilangkan dari header utama IPv6 supaya proses di router menjadi lebih cepat.
* **IPv6** juga menyediakan field *Flow Label* yang bisa dimanfaatkan untuk keperluan Quality of Service (QoS), sesuatu yang tidak ada secara native pada header IPv4.

## Kesimpulan
Baik IPv4 maupun IPv6 memiliki fungsi utama yang sama, yaitu menyediakan mekanisme pengalamatan dan pengiriman paket data dari sumber menuju tujuan melalui jaringan. Selain itu, header IP juga memuat informasi penting yang mendukung proses routing dan pengendalian lalu lintas jaringan, seperti penggunaan TTL pada IPv4 untuk mencegah paket beredar tanpa batas akibat routing loop. Meskipun memiliki tujuan yang sama, IPv6 menawarkan ruang alamat yang jauh lebih besar serta struktur header yang lebih sederhana sehingga mampu memberikan efisiensi dan skalabilitas yang lebih baik dibandingkan IPv4.
