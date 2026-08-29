SETUP PEMBAYARAN + DISCORD

1. Upload file ke hosting PHP + MySQL dan import database.sql.
2. Edit api/config.php:
   - database
   - midtrans_server_key
   - midtrans_client_key
   - discord_webhook_url
3. Di index.html ganti ISI_CLIENT_KEY_MIDTRANS dengan Client Key yang sama.
4. Untuk produksi, ubah $midtrans_production=true dan gunakan script Snap produksi:
   https://app.midtrans.com/snap/snap.js
5. Di dashboard Midtrans, set Payment Notification URL:
   https://DOMAIN-KAMU/api/notification.php
   Gunakan HTTPS.
6. Aktifkan metode pembayaran yang kamu perlukan di akun Midtrans; checkout Snap akan menampilkan metode yang tersedia/diaktifkan.
7. Discord: buat webhook pada channel Discord tujuan, lalu masukkan URL webhook ke config.php.
8. Admin tetap login di /admin/login.php.

PENTING:
- Jangan pernah memasukkan Server Key Midtrans ke JavaScript/front-end.
- Payment status yang mengubah order menjadi paid dilakukan oleh notification backend setelah signature diverifikasi.
- Test dulu di Sandbox sebelum produksi.
