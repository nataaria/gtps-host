# GTPS Hosts untuk Vercel

Project statis sederhana untuk menyajikan daftar hosts GTPS melalui HTTPS Vercel.

## Isi
- `public/hosts.txt` — daftar hosts yang disalin dari link GTPS Cloud.
- `vercel.json` — header MIME `text/plain` dan cache singkat 60 detik.

## Deploy melalui GitHub + Vercel
1. Ekstrak ZIP ini.
2. Buat repository GitHub baru, lalu upload isi folder project ini (folder `public` dan `vercel.json` harus berada di root repository).
3. Di Vercel pilih **Add New → Project**, import repository tersebut.
4. Framework Preset: **Other**. Build Command dan Output Directory biarkan kosong/default; tidak perlu build.
5. Tekan **Deploy**.
6. Setelah berhasil, buka `https://NAMA-PROJECT.vercel.app/hosts.txt`.
7. Pastikan halaman menampilkan empat baris IP/domain, bukan halaman 404 atau HTML.

## PowerTunnel
Tempel URL HTTPS hasil deploy (`https://NAMA-PROJECT.vercel.app/hosts.txt`) ke kolom Host List URL / Remote Hosts URL yang memang mendukung daftar hosts plain-text. Lalu refresh/update daftar dan aktifkan PowerTunnel.

## Memperbarui IP
Edit `public/hosts.txt`, commit/push ke GitHub, lalu tunggu deployment Vercel selesai. Cache disetel 60 detik.

## Catatan penting
- URL `dash.gtps.cloud/android/1773` saat dibuatkan paket ini mengembalikan empat baris hosts dengan IP `91.134.85.13`.
- Ini hanya menyalin daftar hosts menjadi file teks yang di-host di Vercel. Vercel tidak menjadi server game, tidak meneruskan koneksi TCP/UDP Growtopia, dan tidak mengubah IP tujuan.
- HTTPS hanya melindungi pengunduhan file hosts dari Vercel. Koneksi game tetap menuju IP yang tercantum.
- Gunakan hanya untuk server yang kamu miliki atau punya izin untuk diakses. Jika penyedia GTPS mengganti IP, perbarui file sebelum digunakan.
