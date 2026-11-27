# Aplikasi Nonton TV untuk GitHub Pages

Aplikasi web sederhana untuk memutar siaran dari tautan embed resmi. Tidak memakai API key, server, atau layanan berbayar. GitHub Pages hanya menayangkan halaman aplikasi; video tetap disediakan oleh pemilik siaran.

## Cara menjalankan di komputer

Buka `index.html` dengan browser. Masukkan nama saluran dan URL embed HTTPS resmi, lalu klik **Simpan & putar**. Saluran yang dimasukkan melalui formulir tersimpan di browser/perangkat tersebut saja.

## Cara mengunggah ke GitHub Pages

1. Buat repositori GitHub baru.
2. Unggah `index.html` ke bagian paling atas (root) repositori. README boleh ikut diunggah.
3. Buka **Settings → Pages**.
4. Di **Build and deployment**, pilih **Deploy from a branch**.
5. Pilih branch `main` dan folder `/(root)`, lalu klik **Save**.
6. Tunggu proses penerbitan. Alamat situs ditampilkan di bagian Pages.

## Menampilkan daftar saluran untuk semua pengunjung

Di `index.html`, cari bagian berikut:

```js
const DEFAULT_CHANNELS = [];
```

Masukkan satu atau beberapa sumber embed yang resmi dan mengizinkan penyematan. Contoh format:

```js
const DEFAULT_CHANNELS = [
  { name: "Nama saluran", url: "https://alamat-embed-resmi" },
  { name: "Saluran kedua", url: "https://alamat-embed-resmi-lain" }
];
```

Simpan perubahan lalu unggah kembali `index.html` ke repositori GitHub. Daftar bawaan tersebut akan terlihat oleh semua pengunjung. Pastikan URL merupakan tautan pemutar/embed, bukan hanya alamat halaman utama stasiun TV. Beberapa penyedia memblokir pemutaran di situs lain; dalam keadaan itu, gunakan pemutar atau aplikasi resmi penyedia.

## Catatan

- Gunakan hanya siaran dan tautan yang resmi serta diizinkan untuk disematkan.
- Saluran yang ditambahkan melalui formulir disimpan di `localStorage` browser; saluran itu tidak otomatis muncul di perangkat pengunjung lain.
- GitHub Pages menerbitkan situs ke internet. Jangan unggah kata sandi, data pribadi, atau materi yang tidak boleh dipublikasikan.
