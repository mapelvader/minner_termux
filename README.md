
# ccminer yang telah dikompilasi sebelumnya untuk Termux:
Ini adalah repo WIP untuk biner ccminer yang telah dikompilasi sebelumnya dengan Termux terbaru (v0.118.0) dan Clang terbaru (v17.0.6).
# **`Disclaimer: Saya tidak menerima jaminan atau kewajiban apa pun atas repo ini.Lakukan dengan risiko Anda sendiri!!!
# **`Ini untuk semua perangkat ARMv8`**

# **`Ini untuk semua perangkat ARMv8 Jika apk Termux tidak terinstal dilakukan dengan sengaja, apk yang disediakan ini hanya akan bekerja pada sistem operasi arm 64-bit yang pada gilirannya membutuhkan perangkat keras arm 64-bit hal ini untuk menghindari hilangnya waktu bagi pengguna dan saya sendiri. (Menambang pada perangkat 32-bit tidak menguntungkan)`**

# Installasi:
1. Unduh & instal arm64-v8a [Termux](https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk):
```
https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk
```
2. Buka Termux :
- Ketik ylalu enter pada perintah apa pun!
```
termux-setup-storage
```
```
pkg install root-repo pkg install x11-repo
```
```
yes | pkg update && pkg upgrade
yes | pkg install libjansson wget nano
```
3. Unduh ccminer, konfigurasi, mulai :
```
mkdir ccminer && cd ccminer
wget https://raw.githubusercontent.com/mapelvader/ccminer/minning/ccminer
wget https://raw.githubusercontent.com/mapelvader/ccminer/minning/config.json
wget https://raw.githubusercontent.com/mapelvader/ccminer/minning/start.sh
chmod +x ccminer start.sh
```
# Penggunaan:

1. Edit kumpulan, alamat,pekerja :
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
 # **Lanjut setting wallet dll**

4. cara setting autorun:
  ``` 
 cd && cd && cd && nano ../usr/etc/bash.bashrc
```
5. Copykan ini kebaris paling bawah,lalu ctrl X, simpan pilih Y enter cd ccminer/&&./start.sh

Cara setting auto start : Download Termux Boot lalu instal Buka termux
- cd ccminer
  ```
  mkdir ~/.termux/boot cd ~/.termux/boot nano termux.sh  
  ```
6. copy script dibawah ini lalu ctrl X, simpan pilih Y enter lalu reboot hp
 ```
#!/data/data/com.termux/files/usr/bin/sh termux-wake-lock ~/ccminer/start.sh >> ~/miner.log 2>&1
```
# Tips & Trik:
- Jika Termux tidak dapat menyelesaikan pembaruan & peningkatan, silakan hapus cache dan data aplikasi.
- Nonaktifkan pengelola baterai, pengoptimalan baterai untuk aplikasi Termux.
- Jika Anda memiliki opsi "lindungi baterai" untuk menghentikan pengisian daya pada 85% atau serupa, aktifkan untuk membantu menjaga kesehatan baterai.
- Jika Anda menekan lama di mana saja dalam Termux lalu mengklik `More`di sana akan muncul opsi untuk `Keep screen on`.
- Alternatifnya Anda dapat menarik laci notifikasi dan memperluas notifikasi Termux ke `Acquire wakelock` ini yang akan memungkinkan Anda untuk menambang dengan layar  **(CATATAN! tidak semua perangkat mematuhi aturan ini, bisa jadi berhasil atau gagal)** 
- Gunakan kolam dengan latensi rendah ke lokasi/internet Anda.
- Berikan waktu kepada penambang/stratum untuk menstabilkan hashrate (~30 menit-1 jam).
