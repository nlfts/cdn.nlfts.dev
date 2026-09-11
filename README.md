# cdn.nlfts.dev

CDN gambar statis berbasis GitHub Pages. Semua file di dalam `public/` dipublikasikan langsung sebagai URL.

## URL asset

Format URL:

```text
https://cdn.nlfts.dev/<user>/<nama-file>
```

Contoh:

```text
https://cdn.nlfts.dev/user/yudha.png
https://cdn.nlfts.dev/user/tokita.png
```

File contoh tersebut berada di `public/user/yudha.png` dan `public/user/tokita.png`.

## Menambah gambar user

Simpan gambar user langsung di folder `public/user/`:

```text
public/
└── user/
    ├── yudha.png
    ├── tokita.png
    └── images.png
```

Dengan struktur itu, file `public/user/images.png` tersedia di:

```text
https://cdn.nlfts.dev/user/images.png
```

Gunakan nama file huruf kecil, tanpa spasi, dan lebih baik memakai tanda hubung. Hindari menimpa nama file yang sudah dipakai karena browser dan CDN dapat menyimpan cache lama.

## Deploy ke GitHub Pages

Workflow [`.github/workflows/pages.yml`](.github/workflows/pages.yml) akan deploy otomatis setiap push ke branch `main`.

Pengaturan satu kali di GitHub:

1. Buka **Settings > Pages**.
2. Pada **Build and deployment > Source**, pilih **GitHub Actions**.
3. Pastikan DNS domain `cdn.nlfts.dev` mengarah ke GitHub Pages.
4. Custom domain akan dibaca dari [`public/CNAME`](public/CNAME).

Setelah workflow selesai, file dapat diakses melalui `https://cdn.nlfts.dev/`.

## Pengembangan lokal

Jalankan server statis dari root repository:

```bash
python -m http.server 8080 --directory public
```

Lalu buka `http://localhost:8080/user/yudha.png`.

## Format gambar

- Gunakan `webp` atau `avif` untuk gambar dengan ukuran lebih kecil.
- Gunakan `png` untuk transparansi atau kebutuhan kompatibilitas.
- Jangan menyimpan secret, data pribadi, atau file yang bukan untuk publik.
