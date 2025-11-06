# 🌐 Praktikum Jaringan Komputer — Konfigurasi Router dan Switch

---

## 📘 Deskripsi
Proyek ini merupakan implementasi **praktikum konfigurasi jaringan komputer** menggunakan perangkat Cisco (Router ISR4331, Switch 2960, dan dua PC). Tujuan dari kegiatan ini adalah agar mahasiswa memahami proses pengaturan IP address, routing, serta pengujian konektivitas antar subnet menggunakan perintah *ping*.

---

## 🎥 Video Penjelasan
[Tonton di YouTube](https://youtu.be/19tv6ZDVHyA)

---

## 📷 Hasil Praktikum dan Penjelasan

### 1. Topologi Awal Jaringan (Sebelum Konfigurasi Router dan Switch)
![Topologi Awal](./Hasil%20Screenshoot/Screenshot%202025-11-06%20105728.png)

Pada tahap ini ditampilkan rancangan topologi jaringan yang terdiri dari **PC-A, Switch 2960, Router ISR4331, dan PC-B**. Masing-masing perangkat sudah terhubung menggunakan kabel ethernet dan telah diberikan alamat IP sesuai tabel addressing. Namun, karena router dan switch belum dikonfigurasi, komunikasi antar subnet belum dapat dilakukan. Router yang berfungsi sebagai penghubung antar jaringan belum mengaktifkan interface maupun routing, sehingga paket data dari PC-A tidak dapat diteruskan ke PC-B dan sebaliknya.

---

### 2. Hasil Ping dari PC-A (Ping Belum Berhasil ke PC-B)
![Ping PC-A](./Hasil%20Screenshoot/Screenshot%202025-11-06%20105904.png)

PC-A mencoba melakukan *ping* ke alamat IP **192.168.0.3 (PC-B)**, namun seluruh permintaan berakhir dengan *Request timed out*. Hal ini terjadi karena router belum dikonfigurasi dan belum memiliki alamat IP pada interface yang menghubungkan kedua jaringan. Ping ke **192.168.1.3 (IP lokal PC-A)** berhasil, menandakan konfigurasi IP PC-A benar, hanya saja komunikasi antar jaringan belum aktif.

---

### 3. Hasil Ping dari PC-B (Ping Belum Berhasil ke PC-A)
![Ping PC-B](./Hasil%20Screenshoot/Screenshot%202025-11-06%20110309.png)

Hasil pengujian dari sisi PC-B menunjukkan bahwa ping ke 192.168.1.3 (alamat PC-A) maupun ke 192.168.0.3 (alamat sendiri) mengalami Request timed out. Kondisi ini terjadi karena router yang seharusnya berfungsi sebagai gateway antar jaringan belum diaktifkan dan belum dikonfigurasi IP address. Selain itu, PC-B juga belum memiliki default gateway yang mengarahkan paket keluar dari jaringan lokal. Akibatnya, paket ICMP dari PC-B tidak dapat mencapai jaringan 192.168.1.0 dan gagal berkomunikasi dengan PC-A.

---

### 4. Topologi Jaringan Setelah Konfigurasi Router dan Switch
![Topologi Setelah Konfigurasi](./Hasil%20Screenshoot/Screenshot%202025-11-06%20082809.png)

Topologi ini menunjukkan jaringan yang sudah dikonfigurasi sepenuhnya, dengan router ISR4331 berfungsi sebagai penghubung antara dua subnet, yaitu 192.168.1.0/24 dan 192.168.0.0/24. Setiap perangkat telah diatur dengan alamat IP yang sesuai dan gateway default diarahkan ke interface router. Indikator berwarna hijau pada setiap koneksi menandakan bahwa seluruh perangkat telah aktif dan saling terhubung secara fisik maupun logis.

---

### 5. Hasil Ping dari PC-A (Ping Berhasil ke Seluruh Perangkat)
![Ping Sukses PC-A](./Hasil%20Screenshoot/Screenshot%202025-11-06%20110542.png)

Pada gambar ini, PC-A melakukan pengujian konektivitas ke berbagai alamat IP, termasuk 192.168.0.3 (PC-B), 192.168.1.3 (alamat sendiri), 192.168.1.2 (switch), dan 192.168.0.1 (router). Hasilnya menunjukkan bahwa seluruh permintaan ping telah mendapat balasan (Reply from...), menandakan jaringan telah berfungsi dengan baik. Hal ini terjadi karena router sudah diaktifkan dan dikonfigurasi dengan benar pada interface G0/0/0 dan G0/0/1, serta fitur IPv4 routing sudah dijalankan. Dengan konfigurasi tersebut, paket data dari PC-A dapat dikirim dan diterima lintas jaringan melalui router sebagai gateway.

---

### 6. Hasil Ping dari PC-B (Ping Berhasil ke PC-A dan Perangkat Lainnya)
![Ping Sukses PC-B](./Hasil%20Screenshoot/Screenshot%202025-11-06%20110654.png)

Hasil pengujian dari PC-B menunjukkan bahwa ping ke 192.168.1.3 (PC-A), 192.168.1.2 (switch), dan 192.168.0.1 (router) berhasil dengan waktu respon yang stabil dan tanpa kehilangan paket. Hal ini menandakan komunikasi dua arah antar subnet telah berfungsi sempurna. Router kini mampu meneruskan paket ICMP dari jaringan 192.168.0.0 menuju 192.168.1.0 melalui interface yang terhubung. Dengan demikian, konfigurasi IP, gateway, dan routing sudah berjalan sesuai rancangan jaringan yang diinginkan.

---

## 🧠 Kesimpulan
Praktikum ini membuktikan bahwa **konfigurasi router dan switch** berperan penting dalam membangun komunikasi antar subnet. Setelah router diaktifkan dan diatur dengan IP address serta routing yang benar:
- Komunikasi antar perangkat dalam subnet maupun antar subnet berhasil dilakukan.
- Proses *ping* dari kedua PC menunjukkan hasil *Reply from* tanpa error.
- Semua perangkat aktif dan terhubung sesuai rancangan topologi.

Dengan demikian, jaringan telah berfungsi optimal dan konfigurasi berjalan sesuai dengan tujuan praktikum.

---

📌 **Disusun oleh:**  
**Nadjwa Tasya Safira (2315061024)**  
Fakultas Teknik – Universitas Lampung  
Tahun Akademik 2025