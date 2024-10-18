# CCMiner yang telah dikompilasi sebelumnya untuk Termux:
Ini adalah repo WIP untuk biner ccminer yang telah dikompilasi sebelumnya dengan Termux terbaru (v0.118.0) dan Clang terbaru (v17.0.6).
# **`Disclaimer: Saya tidak menerima jaminan atau kewajiban apa pun atas repo ini. Lakukan dengan risiko Anda sendiri!!!
# **`Ini untuk semua perangkat ARMv8`**

# **`Ini untuk semua perangkat ARMv8 Jika apk Termux tidak terinstal dilakukan dengan sengaja, apk yang disediakan ini hanya akan bekerja pada sistem operasi arm 64-bit yang pada gilirannya membutuhkan perangkat keras arm 64-bit hal ini untuk menghindari hilangnya waktu bagi pengguna dan saya sendiri. (Menambang pada perangkat 32-bit tidak menguntungkan)`**

# Installation:
1. Download & install latest arm64-v8a [Termux](https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk):
```
https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk
```
2. Get Termux ready:
- Type `y` then enter key in any prompts!
```
yes | pkg update && pkg upgrade
yes | pkg install libjansson wget nano
```
3. Download ccminer, config, start:
```
mkdir ccminer && cd ccminer
wget https://raw.githubusercontent.com/Darktron/pre-compiled/generic/ccminer
wget https://raw.githubusercontent.com/Darktron/pre-compiled/generic/config.json
wget https://raw.githubusercontent.com/Darktron/pre-compiled/generic/start.sh
chmod +x ccminer start.sh
```
# Usage:

1. Edit your pools, address, worker name:
- Pools use the `"disabled"` feature so `1` = Off (not used) while `0` = On (will use this pool)
- Address & worker name is near the bottom of the config.json in format `address here.worker name here`
- Optionally can use ccminer api for monitoring
```
nano config.json
```
2. Start ccminer with:
```
~/ccminer/start.sh
```
3. Close ccminer with:
```
CTRL + c
```
# Tips & Tricks:
- If Termux can't complete update & upgrade please clear app cache and data.
- Disable battery manager, battery optimization for Termux app.
- If you have a "protect battery" option to stop charge at 85% or similar enable it to help preserve battery health.
- If you long press anywhere within Termux then click `More` there is an option to `Keep screen on`.
- Alternatively you can pull down the notification drawer and expand Termux notification to `Acquire wakelock` this will enable you to mine with the screen off **(NOTE! not all devices obey this rule is a hit or miss)**
- Use a pool with low latency to your location/internet.
- Give the miner/stratum time to stabilize hashrate(~30m-1h).
