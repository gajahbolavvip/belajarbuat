My Stock Portfolio — PLTR & INTC
Dashboard Next.js dengan tema gelap seperti referensi, grafik harga dan perubahan harian yang diambil dari Finnhub.
1. Persiapan
Install Node.js versi LTS: https://nodejs.org/
Buat akun/API key Finnhub: https://finnhub.io/
Extract ZIP lalu buka folder proyek di VS Code.
2. Jalankan di komputer
Salin `.env.example` menjadi `.env.local`, lalu isi:
```env
FINNHUB_API_KEY=API_KEY_KAMU
```
Kemudian jalankan di terminal:
```bash
npm install
npm run dev
```
Buka http://localhost:3000
3. Pasang background Boruto
Masukkan gambar yang kamu punya dan boleh kamu gunakan ke folder `public/` dengan nama:
`boruto-bg.jpg` — background utama halaman.
`boruto-quote.jpg` — gambar kecil di kartu kutipan.
Pastikan nama file persis sama. Gambar pada screenshot referensi bukan file background terpisah, jadi proyek ini tidak bisa mengambil gambar Boruto dari screenshot secara otomatis.
4. Deploy ke Vercel
Upload proyek ke repository GitHub.
Import repository itu di https://vercel.com/
Pada Project Settings → Environment Variables, tambahkan `FINNHUB_API_KEY` dengan API key kamu.
Deploy / redeploy proyek.
Jangan masukkan API key ke kode frontend atau commit ke GitHub.
5. Sesuaikan kepemilikan saham
Di `app/page.tsx`, cari:
```ts
const holdings = { PLTR: { shares: 48, avg: 130 }, INTC: { shares: 160, avg: 28 } };
```
Angka itu hanya contoh. Ubah `shares` menjadi jumlah lembar saham yang kamu miliki dan `avg` menjadi harga beli rata-rata kamu.
Catatan data
Harga diperbarui otomatis sekitar setiap 60 detik selama halaman terbuka.
Pembaruan dan keterlambatan data bergantung pada paket, kuota, dan kebijakan Finnhub. Data real-time bursa AS mungkin memerlukan paket berbayar.
Endpoint quote Finnhub menyediakan high/low quote harian, bukan high/low 52 minggu. Label di kartu diberi catatan supaya tidak disalahartikan.
Portofolio awal memakai angka kepemilikan contoh; ubah sebelum menggunakan nilai keuntungan/kerugian.
Dashboard ini untuk pemantauan, bukan nasihat investasi.
