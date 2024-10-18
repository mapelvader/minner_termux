# CCMiner yang telah dikompilasi sebelumnya untuk Termux:
Ini adalah repo WIP untuk biner ccminer yang telah dikompilasi sebelumnya dengan Termux terbaru (v0.118.0) dan Clang terbaru (v17.0.6).
# **`Disclaimer: Saya tidak menerima jaminan atau kewajiban apa pun atas repo ini. Lakukan dengan risiko Anda sendiri!!!
# **`Ini untuk semua perangkat ARMv8`**

# **`Ini untuk semua perangkat ARMv8 Jika apk Termux tidak terinstal dilakukan dengan sengaja, apk yang disediakan ini hanya akan bekerja pada sistem operasi arm 64-bit yang pada gilirannya membutuhkan perangkat keras arm 64-bit hal ini untuk menghindari hilangnya waktu bagi pengguna dan saya sendiri. (Menambang pada perangkat 32-bit tidak menguntungkan)`**

# Installasi:
1. Unduh & instal arm64-v8a [Termux](https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk): atau Download di Google drive [termux-v0.79-offline-bootstraps](https://drive.google.com/file/d/1ooLjBo6okz6IUDO9U5xxyjiq57ZLXhDx/view?usp=drivesdk):
```
https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk
```
2. Buka Termux :
- Ketik ylalu enter pada perintah apa pun!
```
yes | pkg update && pkg upgrade
yes | pkg install libjansson wget nano
```
3. Unduh ccminer, konfigurasi, mulai :
```
mkdir ccminer && cd ccminer
wget https://raw.githubusercontent.com/mapelvader/CCminer/generic/ccminer
wget https://raw.githubusercontent.com/mapelvader/CCminer/generic/config.json
wget https://raw.githubusercontent.com/mapelvader/CCminer/generic/start.sh
chmod +x ccminer start.sh
```
# Penggunaan:

1. Edit kumpulan, alamat, nama pekerja Anda:
- Pool menggunakan `"disabled"` fitur so `1` = Mati (tidak digunakan) while `0` = Aktif (akan menggunakan pool ini)
- Alamat & nama pekerja ada di dekat bagian bawah config.json dalam format `address here.worker name here`
- Secara opsional dapat menggunakan api ccminer untuk pemantauan
```
nano config.json
```
2. Mulai ccminer dengan:
```
~/ccminer/start.sh
```
3. Tutup ccminer dengan:
```
CTRL + c
```
# Tips & Trik:
- Jika Termux tidak dapat menyelesaikan pembaruan & peningkatan, silakan hapus cache dan data aplikasi.
- Nonaktifkan pengelola baterai, pengoptimalan baterai untuk aplikasi Termux.
- Jika Anda memiliki opsi "lindungi baterai" untuk menghentikan pengisian daya pada 85% atau serupa, aktifkan untuk membantu menjaga kesehatan baterai.
- Jika Anda menekan lama di mana saja dalam Termux lalu mengklik `More`di sana akan muncul opsi untuk `Keep screen on`.
- Alternatifnya Anda dapat menarik laci notifikasi dan memperluas notifikasi Termux ke `Acquire wakelock` ini yang akan memungkinkan Anda untuk menambang dengan layar  **(CATATAN! tidak semua perangkat mematuhi aturan ini, bisa jadi berhasil atau gagal)** 
- Gunakan kolam dengan latensi rendah ke lokasi/internet Anda.
- Berikan waktu kepada penambang/stratum untuk menstabilkan hashrate (~30 menit-1 jam).
