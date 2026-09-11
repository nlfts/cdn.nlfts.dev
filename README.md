# cdn.nlfts.dev



## Getting started

To make it easy for you to get started with GitLab, here's a list of recommended next steps.

Already a pro? Just edit this README.md and make it your own. Want to make it easy? [Use the template at the bottom](#editing-this-readme)!

## Add your files

* [Create](https://docs.gitlab.com/user/project/repository/web_editor/#create-a-file) or [upload](https://docs.gitlab.com/user/project/repository/web_editor/#upload-a-file) files
* [Add files using the command line](https://docs.gitlab.com/topics/git/add_files/#add-files-to-a-git-repository) or push an existing Git repository with the following command:

```
cd existing_repo
git remote add origin https://gitlab.com/davingm/cdn.nlfts.dev.git
git branch -M main
git push -uf origin main
```

## Integrate with your tools

* [Set up project integrations](https://gitlab.com/davingm/cdn.nlfts.dev/-/settings/integrations)

## Collaborate with your team

* [Invite team members and collaborators](https://docs.gitlab.com/user/project/members/)
* [Create a new merge request](https://docs.gitlab.com/user/project/merge_requests/creating_merge_requests/)
* [Automatically close issues from merge requests](https://docs.gitlab.com/user/project/issues/managing_issues/#closing-issues-automatically)
* [Enable merge request approvals](https://docs.gitlab.com/user/project/merge_requests/approvals/)
* [Set auto-merge](https://docs.gitlab.com/user/project/merge_requests/auto_merge/)

## Test and Deploy

Use the built-in continuous integration in GitLab.

* [Get started with GitLab CI/CD](https://docs.gitlab.com/ci/quick_start/)
* [Analyze your code for known vulnerabilities with Static Application Security Testing (SAST)](https://docs.gitlab.com/user/application_security/sast/)
* [Deploy to Kubernetes, Amazon EC2, or Amazon ECS using Auto Deploy](https://docs.gitlab.com/topics/autodevops/requirements/)
* [Use pull-based deployments for improved Kubernetes management](https://docs.gitlab.com/user/clusters/agent/)
* [Set up protected environments](https://docs.gitlab.com/ci/environments/protected_environments/)

***

# Editing this README

When you're ready to make this README your own, just edit this file and use the handy template below (or feel free to structure it however you want - this is just a starting point!). Thanks to [makeareadme.com](https://www.makeareadme.com/) for this template.

## Suggestions for a good README

Every project is different, so consider which of these sections apply to yours. The sections used in the template are suggestions for most open source projects. Also keep in mind that while a README can be too long and detailed, too long is better than too short. If you think your README is too long, consider utilizing another form of documentation rather than cutting out information.

## Name
Choose a self-explaining name for your project.
# cdn.nlfts.dev

Repository asset statis untuk gambar, ikon, dan font yang didistribusikan melalui GitLab Pages.

## Struktur

```text
public/
├── images/
│   ├── brand/       # Logo dan identitas visual
│   ├── content/     # Gambar artikel atau halaman
│   └── ui/          # Gambar untuk komponen antarmuka
├── icons/           # Favicon dan ikon
└── fonts/           # Font web, bila diperlukan
```

Hanya isi `public/` yang dipublikasikan. Folder di luar `public/` dipakai untuk konfigurasi dan dokumentasi.

## Cara memakai

1. Tambahkan file ke kategori yang sesuai di dalam `public/`.
2. Gunakan nama file huruf kecil dengan tanda hubung, misalnya `hero-home.webp`.
3. Buat merge request ke branch `main`.
4. Setelah pipeline berhasil, file tersedia di:

```text
https://cdn.nlfts.dev/images/content/hero-home.webp
```

Untuk sementara, URL GitLab Pages bawaan juga bisa digunakan dari menu **Deploy > Pages** pada project GitLab.

## Format yang disarankan

- Gunakan `webp` atau `avif` untuk foto dan gambar besar.
- Gunakan `svg` untuk logo atau ikon yang perlu tetap tajam.
- Sediakan `png` atau `jpg` hanya jika kompatibilitas lama diperlukan.
- Hindari spasi, huruf kapital, dan nama file generik seperti `image1.png`.
- Jangan menyimpan secret, data pribadi, atau file yang bukan untuk publik.

## Deploy GitLab Pages

Pipeline di [`.gitlab-ci.yml`](.gitlab-ci.yml) menerbitkan `public/` secara otomatis setiap ada perubahan di `main`. Atur domain `cdn.nlfts.dev` pada **Deploy > Pages > New Domain**, lalu tambahkan DNS sesuai instruksi GitLab.

Perubahan pada asset yang sudah dipakai sebaiknya menggunakan nama file baru atau folder versi, contohnya `images/content/v2/hero-home.webp`, agar cache browser dan CDN tidak menyajikan file lama.

## Pengembangan lokal

Tidak ada dependency aplikasi. Untuk melihat asset secara lokal, jalankan server statis dari root repository:

```bash
python -m http.server 8080 --directory public
```

Kemudian buka `http://localhost:8080`.
