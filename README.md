# Silsilah Keluarga Pacitan — pembungkus GitHub Pages

Halaman ini membuka aplikasi Google Apps Script "Silsilah Keluarga Pacitan" dalam satu layar penuh,
dengan ikon sendiri, dan bisa dipasang di layar utama HP seperti aplikasi.

## Isi folder
| File | Fungsi |
|---|---|
| `index.html` | Halaman pembuka + aplikasi (alamat Apps Script ada di baris `APP_URL`) |
| `manifest.json` | Nama, warna, dan ikon aplikasi untuk dipasang di HP |
| `sw.js` | Service worker agar bisa dipasang di layar utama |
| `icons/` | Ikon aplikasi (192, 512, maskable, Apple, favicon) dan sumber `icon.svg` |

## Cara memasang di GitHub Pages
1. Masuk ke **github.com** → klik **+ → New repository**.
   Nama: `silsilah-pacitan`, pilih **Public**, lalu **Create repository**.
2. Klik **uploading an existing file**, lalu seret **semua isi folder ini**
   (`index.html`, `manifest.json`, `sw.js`, `README.md`, dan folder `icons`). Klik **Commit changes**.
3. Buka **Settings → Pages**. Di **Source** pilih **Deploy from a branch**,
   Branch **main**, folder **/ (root)**, lalu **Save**.
4. Tunggu 1–2 menit. Alamatnya akan muncul:
   `https://NAMA-AKUN-ANDA.github.io/silsilah-pacitan/`

## Pasang di HP
- **Android (Chrome):** buka alamat di atas → menu ⋮ → **Instal aplikasi** / **Tambahkan ke layar utama**.
- **iPhone (Safari):** buka alamat → tombol **Bagikan** → **Tambah ke Layar Utama**.

## Bila URL Apps Script berubah
Buka `index.html` di GitHub → ikon pensil → ganti teks di baris `const APP_URL = '…'` → **Commit changes**.
(Kalau memakai **Kelola deployment → Versi baru**, URL tetap sama dan tidak perlu diubah.)

## Catatan
- Data tetap tersimpan di Google Sheet; GitHub hanya menampung halaman pembungkus dan ikon.
- Apps Script sudah mengizinkan ditampilkan di halaman lain (`setXFrameOptionsMode(ALLOWALL)` di `Code.gs`).
- Bila deployment diatur **"Hanya saya"**, sebagian browser HP tidak bisa membuka aplikasi di dalam pembungkus
  karena aturan cookie. Tombol **Buka langsung** akan muncul sebagai jalan pintas.
